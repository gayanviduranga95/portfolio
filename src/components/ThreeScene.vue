<template>
  <div ref="sceneContainer" class="scene-container"></div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import * as THREE from 'three'
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader.js'

const sceneContainer = ref(null)

let scene
let camera
let renderer
let animationId

const mouse = {
  x: 0,
  y: 0
}
onMounted(() => {
  // 1. Create the 3D world
  scene = new THREE.Scene()
    // Soft overall light
const ambientLight = new THREE.AmbientLight(0xffffff, 2)
scene.add(ambientLight)

// Main light
const keyLight = new THREE.DirectionalLight(0xffffff, 3)
keyLight.position.set(5, 5, 5)
scene.add(keyLight)

// Fill light
const fillLight = new THREE.DirectionalLight(0xffffff, 1.5)
fillLight.position.set(-5, 2, 3)
scene.add(fillLight)

const rimLight = new THREE.PointLight(0xffffff, 4, 10)
rimLight.position.set(3, 3, -2)
scene.add(rimLight)

  // 2. Create the camera
  camera = new THREE.PerspectiveCamera(
    75,
    window.innerWidth / window.innerHeight,
    0.1,
    1000
  )

  camera.position.set(0, 1, 7.5)

  // 3. Create the renderer
  renderer = new THREE.WebGLRenderer({
    antialias: true,
    alpha: true
  })

  renderer.setSize(
  window.innerWidth,
  window.innerHeight
)

renderer.setPixelRatio(
  Math.min(window.devicePixelRatio, 2)
)

  sceneContainer.value.appendChild(renderer.domElement)

  const handleMouseMove = (event) => {
     mouse.x = (event.clientX / window.innerWidth) * 2 - 1
    mouse.y = -(event.clientY / window.innerHeight) * 2 + 1
  }

  window.addEventListener('mousemove', handleMouseMove)

  // 4. Create a test object
  const geometry = new THREE.BoxGeometry(1.8, 1.8, 1.8)

  const material = new THREE.MeshNormalMaterial()

  const cube = new THREE.Mesh(geometry, material)

  //scene.add(cube)
  const loader = new GLTFLoader()

let model = null

loader.load(
  '/models/test-model.glb',
  (gltf) => {
    model = gltf.scene

    model.scale.set(0.85, 0.85, 0.85)
    model.position.set(2.6, -0.8, 0)
    scene.add(model)

    console.log('3D model loaded successfully')
  },
  undefined,
  (error) => {
    console.error('Error loading 3D model:', error)
  }
)
  // 5. Animation loop
  function animate() {
  animationId = requestAnimationFrame(animate)

  if (model) {
    model.rotation.y += 0.005
  }

  renderer.render(scene, camera)
}

  animate()
})

onBeforeUnmount(() => {
  cancelAnimationFrame(animationId)
  renderer?.dispose()
  window.removeEventListener('mousemove', handleMouseMove)
})
</script>

<style scoped>
.scene-container {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>