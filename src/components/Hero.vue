<template>
  <section class="hero" id="about">
    <div class="hero-content">

      <p class="eyebrow">
        COMPUTER ENGINEERING
      </p>

      <h1>
        Gayan
        <span>Viduranga</span>
      </h1>

      <p class="description">
        Computer Engineering undergraduate building intelligent,
        interactive and practical technology.
      </p>

      <div class="specialties">
        <span>AI / ML</span>
        <span>•</span>
        <span>EMBEDDED SYSTEMS</span>
        <span>•</span>
        <span>SOFTWARE DEVELOPMENT</span>
      </div>

      <div class="hero-actions">
        <a href="#projects" class="primary-button">
          View My Work
          <span>→</span>
        </a>

        <a href="#contact" class="secondary-button">
          Contact Me
        </a>
      </div>

    </div>

    <div class="hero-meta">
      <div>
        <span class="number">01</span>
        <span>STUDENT</span>
      </div>

      <div>
        <span class="number">02</span>
        <span>DEVELOPER</span>
      </div>

      <div>
        <span class="number">03</span>
        <span>PROBLEM SOLVER</span>
      </div>

      <div>
        <span class="number">04</span>
        <span>LIFELONG LEARNER</span>
      </div>
    </div>

    <div class="scroll-indicator">
      <span class="scroll-line"></span>
      <span>SCROLL TO EXPLORE</span>
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  z-index: 5;

  min-height: 100vh;
  width: 100%;

  display: flex;
  align-items: center;

  padding: 7rem 7vw 4rem;
}

.hero-content {
  max-width: 720px;
}

.eyebrow {
  margin: 0 0 1.5rem;

  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.45em;

  color: rgba(255, 255, 255, 0.55);
}

h1 {
  margin: 0;

  font-size: clamp(4.5rem, 9vw, 9rem);
  line-height: 0.82;
  letter-spacing: -0.07em;
  font-weight: 600;
}

h1 span {
  display: block;
  font-weight: 300;
}

.description {
  max-width: 520px;
  margin: 2.5rem 0 0;

  font-size: clamp(1rem, 1.4vw, 1.2rem);
  line-height: 1.65;

  color: rgba(255, 255, 255, 0.68);
}

.specialties {
  display: flex;
  flex-wrap: wrap;
  gap: 0.7rem;

  margin-top: 1.8rem;

  font-size: 0.68rem;
  letter-spacing: 0.2em;

  color: rgba(255, 255, 255, 0.48);
}

.hero-actions {
  display: flex;
  gap: 1rem;

  margin-top: 2.5rem;

  pointer-events: auto;
}

.hero-actions a {
  text-decoration: none;
}

.primary-button,
.secondary-button {
  min-height: 52px;

  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;

  padding: 0 1.5rem;

  font-size: 0.8rem;
  letter-spacing: 0.08em;

  transition:
    transform 0.3s ease,
    background 0.3s ease,
    color 0.3s ease,
    border-color 0.3s ease;
}

.primary-button {
  background: #ffffff;
  color: #000000;
}

.secondary-button {
  border: 1px solid rgba(255, 255, 255, 0.4);
  color: #ffffff;
}

.primary-button:hover,
.secondary-button:hover {
  transform: translateY(-3px);
}

.secondary-button:hover {
  background: #ffffff;
  color: #000000;
}

.hero-meta {
  position: absolute;

  right: 5vw;
  top: 50%;

  display: flex;
  flex-direction: column;
  gap: 1.5rem;

  transform: translateY(-50%);
}

.hero-meta div {
  display: flex;
  flex-direction: column;

  padding-left: 1rem;

  border-left: 1px solid rgba(255, 255, 255, 0.25);
}

.hero-meta span:last-child {
  margin-top: 0.3rem;

  font-size: 0.6rem;
  letter-spacing: 0.22em;

  color: rgba(255, 255, 255, 0.55);
}

.number {
  font-size: 0.65rem;
  letter-spacing: 0.1em;
}

.scroll-indicator {
  position: absolute;

  left: 7vw;
  bottom: 2rem;

  display: flex;
  align-items: center;
  gap: 0.8rem;

  font-size: 0.6rem;
  letter-spacing: 0.28em;

  color: rgba(255, 255, 255, 0.45);
}

.scroll-line {
  display: block;

  width: 1px;
  height: 40px;

  background: rgba(255, 255, 255, 0.6);
}

@media (max-width: 800px) {
  .hero {
    padding: 7rem 6vw 5rem;
  }

  h1 {
    font-size: clamp(3.8rem, 16vw, 6rem);
  }

  .hero-meta {
    display: none;
  }

  .specialties {
    max-width: 400px;
  }
}

@media (max-width: 500px) {
  .hero-actions {
    flex-direction: column;
    align-items: flex-start;
  }

  .primary-button,
  .secondary-button {
    width: 100%;
  }

  .scroll-indicator {
    display: none;
  }
}
</style>