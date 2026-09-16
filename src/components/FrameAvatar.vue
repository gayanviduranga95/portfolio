<template>
  <div class="avatar-background">
    <img
      :src="currentFrame"
      alt=""
      class="avatar-frame"
      :style="avatarStyle"
      draggable="false"
    />

    <div
      class="left-shade"
      :style="leftShadeStyle"
    ></div>

    <div class="vignette"></div>
  </div>
</template>

<script setup>
import { computed, onBeforeUnmount, onMounted, ref } from 'vue'

/*
|--------------------------------------------------------------------------
| Configuration
|--------------------------------------------------------------------------
*/

const TOTAL_FRAMES = 97
const CENTER_FRAME = 49
const MIN_FRAME = 1

const AUTO_IDLE_DELAY = 2800
const AUTO_ROTATE_RANGE = 42
const AUTO_ROTATE_SPEED = 0.018
const AUTO_ROTATE_MAX_SPEED = 0.05
const TILT_RANGE = 5
const PARALLAX_RANGE = 12

// Smoothness of frame movement
const DAMPING = 0.12

/*
|--------------------------------------------------------------------------
| Frame state
|--------------------------------------------------------------------------
*/

const targetFrame = ref(CENTER_FRAME)
const displayedFrame = ref(CENTER_FRAME)
const mouseProgress = ref(0.5)
const mouseTiltX = ref(0)
const mouseTiltY = ref(0)
const lastPointerMoveAt = ref(Date.now())
const isPointerInside = ref(true)
const autoPhase = ref(0)

/*
|--------------------------------------------------------------------------
| Scroll state
|--------------------------------------------------------------------------
*/

const scrollProgress = ref(0)

/*
|--------------------------------------------------------------------------
| Animation
|--------------------------------------------------------------------------
*/

let animationFrameId = null

/*
|--------------------------------------------------------------------------
| Current frame
|--------------------------------------------------------------------------
*/

const currentFrame = computed(() => {
  const frame = Math.max(
    MIN_FRAME,
    Math.min(
      TOTAL_FRAMES,
      Math.round(displayedFrame.value)
    )
  )

  return `/frames/avatar-${String(frame).padStart(3, '0')}.webp`
})

const leftShadeStyle = computed(() => {
  const leftStrength = 0.16 + (1 - mouseProgress.value) * 0.12
  const midStrength = 0.1 + (1 - mouseProgress.value) * 0.08
  const edgeStrength = 0.02 + (1 - mouseProgress.value) * 0.03

  return {
    background: `linear-gradient(
      90deg,
      rgba(0, 0, 0, ${leftStrength}) 0%,
      rgba(0, 0, 0, ${midStrength}) 28%,
      rgba(0, 0, 0, 0.03) 58%,
      rgba(0, 0, 0, ${edgeStrength}) 100%
    )`
  }
})

/*
|--------------------------------------------------------------------------
| Scroll-based visual effect
|--------------------------------------------------------------------------
*/

const avatarStyle = computed(() => {
  const moveY = scrollProgress.value * -80
  const scale = 1 + scrollProgress.value * 0.08
  const opacity = 1 - scrollProgress.value * 0.25
  const parallaxX = mouseTiltX.value * PARALLAX_RANGE
  const parallaxY = mouseTiltY.value * PARALLAX_RANGE
  const rotateX = mouseTiltY.value * -TILT_RANGE
  const rotateY = mouseTiltX.value * TILT_RANGE

  return {
    transform: `translate3d(${parallaxX}px, ${moveY + parallaxY}px, 0) scale(${scale}) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`,
    opacity
  }
})

function clamp(value, min, max) {
  return Math.max(min, Math.min(max, value))
}

function mapProgressToFrame(progress) {
  if (progress >= 0.5) {
    const t = (progress - 0.5) / 0.5

    return CENTER_FRAME - t * (CENTER_FRAME - MIN_FRAME)
  }

  const t = progress / 0.5

  return CENTER_FRAME + (1 - t) * (TOTAL_FRAMES - CENTER_FRAME)
}

function handlePointerMove(event) {
  const progress = clamp(
    event.clientX / window.innerWidth,
    0,
    1
  )

  const tiltX = (event.clientX / window.innerWidth - 0.5) * 2
  const tiltY = (event.clientY / window.innerHeight - 0.5) * 2

  lastPointerMoveAt.value = Date.now()
  mouseProgress.value = progress
  mouseTiltX.value = clamp(tiltX, -1, 1)
  mouseTiltY.value = clamp(tiltY, -1, 1)

  targetFrame.value = mapProgressToFrame(progress)
}

function handlePointerLeave() {
  isPointerInside.value = false
}

function handlePointerEnter() {
  isPointerInside.value = true
  lastPointerMoveAt.value = Date.now()
}

function updateAutoRotation(now) {
  if (document.visibilityState === 'hidden') {
    return
  }

  if (isPointerInside.value && now - lastPointerMoveAt.value < AUTO_IDLE_DELAY) {
    return
  }

  const idleTime = now - lastPointerMoveAt.value
  const extraSpeed = clamp((idleTime - AUTO_IDLE_DELAY) / 4000, 0, 1) * (AUTO_ROTATE_MAX_SPEED - AUTO_ROTATE_SPEED)

  autoPhase.value += AUTO_ROTATE_SPEED + extraSpeed

  targetFrame.value =
    CENTER_FRAME + Math.sin(autoPhase.value) * AUTO_ROTATE_RANGE
}

/*
|--------------------------------------------------------------------------
| Scroll handler
|--------------------------------------------------------------------------
*/

function handleScroll() {
  const heroHeight = window.innerHeight

  const progress =
    window.scrollY / heroHeight

  scrollProgress.value = clamp(progress, 0, 1)
}

/*
|--------------------------------------------------------------------------
| Smooth frame movement
|--------------------------------------------------------------------------
*/

function animate(now = performance.now()) {
  updateAutoRotation(now)

  const difference =
    targetFrame.value -
    displayedFrame.value

  displayedFrame.value +=
    difference * DAMPING

  animationFrameId =
    requestAnimationFrame(animate)
}

/*
|--------------------------------------------------------------------------
| Preload all frames
|--------------------------------------------------------------------------
*/

function preloadFrames() {
  for (
    let i = MIN_FRAME; i <= TOTAL_FRAMES; i++
  ) {
    const image = new Image()

    image.src =
      `/frames/avatar-${String(i).padStart(3, '0')}.webp`
  }
}

/*
|--------------------------------------------------------------------------
| Lifecycle
|--------------------------------------------------------------------------
*/

onMounted(() => {
  window.addEventListener(
    'mousemove',
    handlePointerMove,
    { passive: true }
  )

  window.addEventListener(
    'mouseleave',
    handlePointerLeave,
    { passive: true }
  )

  window.addEventListener(
    'mouseenter',
    handlePointerEnter,
    { passive: true }
  )

  window.addEventListener(
    'scroll',
    handleScroll,
    { passive: true }
  )

  preloadFrames()

  animate()
})

onBeforeUnmount(() => {
  window.removeEventListener(
    'mousemove',
    handlePointerMove
  )

  window.removeEventListener(
    'mouseleave',
    handlePointerLeave
  )

  window.removeEventListener(
    'mouseenter',
    handlePointerEnter
  )

  window.removeEventListener(
    'scroll',
    handleScroll
  )

  cancelAnimationFrame(
    animationFrameId
  )
})
</script>

<style scoped>
/*
| Full-screen background
|--------------------------------------------------------------------------
*/

.avatar-background {
  position: fixed;

  top: 72px;
  right: 0;
  bottom: 0;
  left: 0;

  width: auto;
  height: auto;

  z-index: 0;
  overflow: hidden;

  background: #050505;

  pointer-events: none;
}

/*
|--------------------------------------------------------------------------
| Animated frame
|--------------------------------------------------------------------------
*/

.avatar-frame {
  position: absolute;

  top: 0;
  left: 0;

  width: 100%;
  height: 100%;

  object-fit: cover;

  /* Keep more of the upper part of the source image visible */
  object-position: center top;

  user-select: none;
  pointer-events: none;

  filter:
    brightness(0.8)
    contrast(1.05)
    saturate(0.9);

  transition:
    transform 0.08s linear,
    opacity 0.15s linear;

  /*
   * Slight zoom so there are no empty edges.
   * The extra space is cropped from the bottom.
   */
  transform: scale(1.08);
  transform-origin: center top;
}

/*
|--------------------------------------------------------------------------
| Dark gradient for readable text
|--------------------------------------------------------------------------
*/

.left-shade {
  position: absolute;
  inset: 0;

  pointer-events: none;
}
/*
|--------------------------------------------------------------------------
| Cinematic vignette
|--------------------------------------------------------------------------
*/

.vignette {
  position: absolute;

  inset: 0;

  background:
    radial-gradient(
      circle at 60% 48%,
      transparent 30%,
      rgba(0, 0, 0, 0.06) 62%,
      rgba(0, 0, 0, 0.38) 100%
    );

  pointer-events: none;
}

/*
|--------------------------------------------------------------------------
| Mobile
|--------------------------------------------------------------------------
*/

@media (max-width: 650px) {
  .avatar-frame {
    object-position: 60% center;

    filter:
      brightness(0.74)
      contrast(1.08)
      saturate(0.78);
  }
}
</style>