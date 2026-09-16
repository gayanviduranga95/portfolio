<template>
  <section id="about" class="about-section">
    <div class="section-header">
      <p class="section-label">01 — ABOUT ME</p>

      <h2>
        Engineer.
        <span>Builder.</span>
        <span>Learner.</span>
      </h2>
    </div>

    <div class="about-content">
      <div class="about-intro">
        <p class="lead">
          I'm a Computer Engineering undergraduate interested in
          building intelligent systems, practical software, and
          technology that connects hardware with software.
        </p>

        <p>
          My current interests include artificial intelligence,
          machine learning, embedded systems, and modern web
          development. I enjoy turning ideas into working
          prototypes and learning through real projects.
        </p>
      </div>

      <div class="about-focus">
        <div class="focus-item">
          <span class="focus-number">01</span>

          <div>
            <h3>AI / ML</h3>
            <p>
              Exploring intelligent systems, machine learning,
              computer vision, and AI-powered applications.
            </p>
          </div>
        </div>

        <div class="focus-item">
          <span class="focus-number">02</span>

          <div>
            <h3>Embedded Systems</h3>
            <p>
              Building systems that connect software,
              electronics, sensors, and real-world devices.
            </p>
          </div>
        </div>

        <div class="focus-item">
          <span class="focus-number">03</span>

          <div>
            <h3>Software Engineering</h3>
            <p>
              Learning to design maintainable applications,
              APIs, databases, and modern user interfaces.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  min-height: 100vh;

  display: flex;
  flex-direction: column;
  justify-content: center;

  padding: 9rem 7vw;

  border-top: 1px solid rgba(255, 255, 255, 0.08);

  background: rgba(0, 0, 0, 0.25);

  backdrop-filter: blur(8px);
}

.section-header {
  max-width: 900px;
}

.section-label {
  margin: 0 0 2rem;

  font-size: 0.65rem;
  letter-spacing: 0.3em;

  color: rgba(255, 255, 255, 0.42);
}

h2 {
  margin: 0;

  font-size: clamp(3.8rem, 8vw, 8rem);
  line-height: 0.88;

  letter-spacing: -0.065em;
  font-weight: 600;
}

h2 span {
  display: block;

  font-weight: 300;

  color: rgba(255, 255, 255, 0.65);
}

.about-content {
  display: grid;

  grid-template-columns:
    minmax(0, 0.9fr)
    minmax(0, 1.1fr);

  gap: 7vw;

  margin-top: 5rem;
}

.about-intro {
  max-width: 550px;
}

.about-intro p {
  margin: 0;

  color: rgba(255, 255, 255, 0.58);

  line-height: 1.8;
}

.about-intro .lead {
  margin-bottom: 1.5rem;

  font-size: 1.15rem;

  color: rgba(255, 255, 255, 0.82);
}

.about-focus {
  display: flex;
  flex-direction: column;
}

.focus-item {
  display: grid;

  grid-template-columns: 50px 1fr;

  gap: 1rem;

  padding: 1.5rem 0;

  border-top:
    1px solid rgba(255, 255, 255, 0.12);
}

.focus-item:last-child {
  border-bottom:
    1px solid rgba(255, 255, 255, 0.12);
}

.focus-number {
  padding-top: 0.2rem;

  font-size: 0.65rem;

  letter-spacing: 0.12em;

  color: rgba(255, 255, 255, 0.38);
}

.focus-item h3 {
  margin: 0;

  font-size: 1.1rem;
  font-weight: 500;
}

.focus-item p {
  margin: 0.6rem 0 0;

  color: rgba(255, 255, 255, 0.5);

  line-height: 1.6;
}

@media (max-width: 800px) {
  .about-section {
    padding: 7rem 6vw;
  }

  .about-content {
    grid-template-columns: 1fr;

    gap: 4rem;

    margin-top: 4rem;
  }

  h2 {
    font-size: clamp(3.5rem, 14vw, 6rem);
  }
}
</style>