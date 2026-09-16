<template>
  <main class="portfolio">

    <!-- Animated background -->
    <FrameAvatar />

    <!-- Navigation -->
    <Navbar />

    <!-- Page content -->
    <div class="page-content">

      <!-- ================= HERO ================= -->
      <section class="hero reveal">

        <div class="hero-content">

          <p class="eyebrow">
            COMPUTER ENGINEERING
          </p>

          <h1>
            Gayan
            <span>Viduranga</span>
          </h1>

          <p class="description">
            Computer Engineering undergraduate building
            intelligent, interactive and practical technology.
          </p>

          <div class="specialties">
            <span>AI / ML</span>
            <span>•</span>
            <span>EMBEDDED SYSTEMS</span>
            <span>•</span>
            <span>SOFTWARE DEVELOPMENT</span>
          </div>

          <div class="hero-actions">

            <a
              href="#projects"
              class="primary-button"
            >
              View My Work
              <span>→</span>
            </a>

            <a
              href="#contact"
              class="secondary-button"
            >
              Contact Me
            </a>

          </div>

        </div>

        <div class="hero-meta">

          <div class="meta-item">
            <span class="number">01</span>
            <span class="meta-label">STUDENT</span>
          </div>

          <div class="meta-item">
            <span class="number">02</span>
            <span class="meta-label">DEVELOPER</span>
          </div>

          <div class="meta-item">
            <span class="number">03</span>
            <span class="meta-label">PROBLEM SOLVER</span>
          </div>

          <div class="meta-item">
            <span class="number">04</span>
            <span class="meta-label">LIFELONG LEARNER</span>
          </div>

        </div>

        <div class="scroll-indicator">

          <span class="scroll-line"></span>

          <span>
            SCROLL TO EXPLORE
          </span>

        </div>

      </section>


      <!-- ================= ABOUT ================= -->
      <section
        id="about"
        class="page-section about-section reveal"
      >

        <div class="section-inner">

          <p class="section-label">
            01 — ABOUT ME
          </p>

          <h2>
            Engineer.
            <br />
            <span>Builder.</span>
            <br />
            <span>Learner.</span>
          </h2>

          <div class="about-grid">

            <div class="about-text">

              <p class="lead">
                I'm a Computer Engineering undergraduate
                interested in building intelligent systems,
                practical software, and technology that connects
                hardware with software.
              </p>

              <p>
                My current interests include artificial
                intelligence, machine learning, embedded systems,
                and modern web development. I enjoy turning ideas
                into working prototypes and learning through
                real projects.
              </p>

            </div>


            <div class="focus-list">

              <div class="focus-item">

                <span>01</span>

                <div>
                  <h3>AI / ML</h3>

                  <p>
                    Intelligent systems, machine learning,
                    computer vision, and AI-powered applications.
                  </p>
                </div>

              </div>


              <div class="focus-item">

                <span>02</span>

                <div>
                  <h3>Embedded Systems</h3>

                  <p>
                    Sensors, electronics, device logic,
                    and real-world hardware systems.
                  </p>
                </div>

              </div>


              <div class="focus-item">

                <span>03</span>

                <div>
                  <h3>Software Engineering</h3>

                  <p>
                    Applications, APIs, databases,
                    and modern interfaces.
                  </p>
                </div>

              </div>

            </div>

          </div>

        </div>

      </section>


      <!-- ================= SKILLS ================= -->
      <section
        id="skills"
        class="page-section reveal"
      >

        <div class="section-inner">

          <p class="section-label">
            02 — CORE SKILLS
          </p>

          <h2>
            What I Build
          </h2>

          <div class="card-grid">

            <article class="glass-card">

              <span>01</span>

              <h3>
                Programming
              </h3>

              <p>
                Python · C · C++ · Java · JavaScript
              </p>

            </article>


            <article class="glass-card">

              <span>02</span>

              <h3>
                AI / ML
              </h3>

              <p>
                Machine learning · Computer vision · AI systems
              </p>

            </article>


            <article class="glass-card">

              <span>03</span>

              <h3>
                Embedded
              </h3>

              <p>
                Arduino · Sensors · C/C++ · IoT
              </p>

            </article>


            <article class="glass-card">

              <span>04</span>

              <h3>
                Web Development
              </h3>

              <p>
                Vue · Vite · HTML · CSS · REST APIs
              </p>

            </article>


            <article class="glass-card">

              <span>05</span>

              <h3>
                Databases
              </h3>

              <p>
                SQL · MySQL · Database design
              </p>

            </article>


            <article class="glass-card">

              <span>06</span>

              <h3>
                Tools
              </h3>

              <p>
                Git · GitHub · VS Code · Linux · WSL
              </p>

            </article>

          </div>

        </div>

      </section>


      <!-- ================= PROJECTS ================= -->
        <section
  id="projects"
      class="page-section projects-section reveal"
>
  <div class="section-inner">

    <p class="section-label">
      03 — SELECTED WORK
    </p>

    <h2>
      Projects
    </h2>

    <MedoraAIProject />

  </div>
</section>


      <!-- ================= CONTACT ================= -->
      <section
        id="contact"
        class="page-section contact-section reveal"
      >

        <div class="section-inner">

          <p class="section-label">
            04 — CONTACT
          </p>

          <h2>
            Let's build
            <span>something.</span>
          </h2>

          <p class="contact-text">
            I'm interested in internships, engineering projects,
            AI/ML, embedded systems, and opportunities to learn
            by building real products.
          </p>

          <div class="contact-links">

            <a
              href="mailto:your-email@example.com"
            >
              Email →
            </a>

            <a
              href="https://github.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              GitHub →
            </a>

            <a
              href="https://www.linkedin.com/"
              target="_blank"
              rel="noopener noreferrer"
            >
              LinkedIn →
            </a>

          </div>

        </div>

      </section>

    </div>

  </main>
</template>


<script setup>
import { onBeforeUnmount, onMounted } from 'vue'
import Navbar from './components/Navbar.vue'
import FrameAvatar from './components/FrameAvatar.vue'
import MedoraAIProject from './components/MedoraAIProject.vue'

let revealObserver = null

onMounted(() => {
  const targets = document.querySelectorAll('.reveal')

  revealObserver = new IntersectionObserver(
    entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible')
          revealObserver?.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.2 }
  )

  targets.forEach(target => revealObserver.observe(target))
})

onBeforeUnmount(() => {
  revealObserver?.disconnect()
})
</script>


<style scoped>

/* =========================================
   MAIN
========================================= */

.portfolio {
  position: relative;

  min-height: 100vh;

  background:
    radial-gradient(circle at 15% 10%, rgba(216, 178, 76, 0.14), transparent 22%),
    radial-gradient(circle at 80% 18%, rgba(255, 255, 255, 0.06), transparent 20%),
    linear-gradient(180deg, #05070d 0%, #05070d 44%, #070a11 100%);

  color: #f5f7fb;
}


/* =========================================
   CONTENT
========================================= */

.page-content {
  position: relative;

  z-index: 5;
}

.reveal {
  opacity: 0;
  transform: translateY(28px);
  transition:
    opacity 0.8s ease,
    transform 0.8s ease;
  will-change: opacity, transform;
}

.reveal.is-visible {
  opacity: 1;
  transform: translateY(0);
}

.hero.reveal {
  transform: translateY(22px);
}

.hero.reveal.is-visible {
  transform: translateY(0);
}

.page-section::before,
.hero::before {
  content: '';

  position: absolute;
  inset: 0;

  pointer-events: none;

  background-image:
    linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
  background-size: 48px 48px;
  opacity: 0.35;
  mask-image: linear-gradient(180deg, rgba(0, 0, 0, 0.7), transparent 95%);
}


/* =========================================
   HERO
========================================= */

.hero {
  position: relative;

  min-height: 100vh;

  display: grid;
  grid-template-columns: minmax(0, 1.2fr) minmax(340px, 0.8fr);
  gap: 4rem;
  align-items: end;

  padding: 8.5rem 7vw 6rem;

  overflow: hidden;
}


.hero-content {
  position: relative;

  z-index: 5;

  max-width: 780px;
  padding-bottom: 2rem;
}


.eyebrow {
  margin:
    0
    0
    1.25rem;

  font-size: 0.78rem;

  font-weight: 500;

  letter-spacing: 0.34em;

  color:
    rgba(245, 247, 251, 0.52);
}


h1 {
  margin: 0;

  font-size:
    clamp(4.8rem, 10vw, 10.5rem);

  line-height: 0.78;

  letter-spacing: -0.09em;

  font-weight: 700;

  text-wrap: balance;
}


h1 span {
  display: block;

  font-weight: 500;

  color:
    rgba(245, 247, 251, 0.92);
}


.description {
  max-width: 520px;

  margin-top: 1.9rem;

  font-size: 1.15rem;

  line-height: 1.9;

  color:
    rgba(245, 247, 251, 0.74);
}


.specialties {
  display: flex;

  flex-wrap: wrap;

  gap: 0.8rem;

  margin-top: 2rem;

  font-size: 0.72rem;

  letter-spacing: 0.22em;

  color:
    rgba(245, 247, 251, 0.58);
}

.specialties span:not(:nth-child(2n)) {
  padding: 0.45rem 0.7rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.03);
}


/* =========================================
   HERO BUTTONS
========================================= */

.hero-actions {
  display: flex;

  gap: 1rem;

  margin-top: 2.3rem;
}


.hero-actions a {
  text-decoration: none;
}


.primary-button,
.secondary-button {
  min-height: 56px;

  display: inline-flex;

  align-items: center;

  justify-content: center;

  gap: 1rem;

  padding: 0 1.5rem;

  font-size: 0.78rem;

  letter-spacing: 0.14em;

  transition:
    transform 0.3s ease,
    background 0.3s ease,
    color 0.3s ease,
    border-color 0.3s ease,
    box-shadow 0.3s ease;
}


.primary-button {
  background: linear-gradient(180deg, #ffffff, #e9e9e9);

  color: #000000;

  box-shadow: 0 18px 32px rgba(0, 0, 0, 0.28);
}


.secondary-button {
  border:
    1px solid
    rgba(255, 255, 255, 0.16);

  color: #f5f7fb;

  background:
    rgba(255, 255, 255, 0.03);
}


.primary-button:hover,
.secondary-button:hover {
  transform:
    translateY(-3px);
}


.secondary-button:hover {
  background: #ffffff;

  color: #000000;

  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.22);
}


/* =========================================
   HERO META
========================================= */

.hero-meta {
  position: relative;

  display: flex;

  flex-direction: column;
  gap: 0.9rem;

  padding: 1.25rem;
  border: 1px solid rgba(255, 255, 255, 0.08);
  background: rgba(255, 255, 255, 0.03);
  backdrop-filter: blur(18px);
  border-radius: 1.25rem;
}


.meta-item {
  display: flex;

  flex-direction: column;

  padding: 1rem 0 1rem 1rem;

  border-left: 1px solid rgba(255, 255, 255, 0.14);
}


.number {
  font-size: 0.82rem;

  letter-spacing: 0.12em;
}


.meta-label {
  margin-top: 0.3rem;

  font-size: 0.72rem;

  letter-spacing: 0.18em;

  color:
    rgba(245, 247, 251, 0.58);
}


/* =========================================
   SCROLL
========================================= */

.scroll-indicator {
  display: flex;

  align-items: center;

  gap: 0.9rem;

  margin-top: 2rem;

  font-size: 0.72rem;

  letter-spacing: 0.26em;

  color:
    rgba(245, 247, 251, 0.54);
}


.scroll-line {
  width: 1px;

  height: 28px;

  background: rgba(216, 178, 76, 0.9);
}


/* =========================================
   SECTIONS
========================================= */

.page-section {
  position: relative;

  min-height: auto;

  display: flex;

  align-items: center;

  padding: 7.5rem 7vw;

  border-top:
    1px solid
    rgba(255, 255, 255, 0.08);

  background:
    rgba(255, 255, 255, 0.02);

  backdrop-filter: blur(16px);
}


.section-inner {
  width: 100%;

  max-width: 1240px;

  margin: 0 auto;
}


.section-label {
  margin:
    0
    0
    1.8rem;

  font-size: 0.74rem;

  letter-spacing: 0.34em;

  color:
    rgba(245, 247, 251, 0.42);
}


.page-section h2 {
  margin: 0;

  font-size:
    clamp(3.8rem, 8vw, 8rem);

  line-height: 0.84;

  letter-spacing: -0.08em;

  font-weight: 700;

  text-wrap: balance;
}


.page-section h2 span {
  font-weight: 500;

  color:
    rgba(245, 247, 251, 0.9);
}


/* =========================================
   ABOUT
========================================= */

.about-grid {
  display: grid;

  grid-template-columns:
    1fr
    1fr;

  gap: 3rem;

  margin-top: 4rem;
}


.about-text {
  max-width: 560px;
}


.about-text p {
  margin: 0;

  color:
    rgba(245, 247, 251, 0.62);

  line-height: 1.8;
}


.about-text .lead {
  margin-bottom: 1.4rem;

  font-size: 1.2rem;

  color:
    rgba(245, 247, 251, 0.86);
}


.focus-list {
  display: flex;

  flex-direction: column;
}


.focus-item {
  display: grid;

  grid-template-columns: 56px 1fr;

  gap: 1rem;

  padding:
    1.35rem
    0;

  border-top:
    1px solid
    rgba(255, 255, 255, 0.12);
}


.focus-item:last-child {
  border-bottom:
    1px solid
    rgba(255, 255, 255, 0.12);
}


.focus-item > span {
  font-size: 0.8rem;

  color:
    rgba(245, 247, 251, 0.38);
}


.focus-item h3 {
  margin: 0;

  font-size: 1.25rem;

  font-weight: 500;
}


.focus-item p {
  margin:
    0.6rem
    0
    0;

  line-height: 1.8;

  color:
    rgba(245, 247, 251, 0.56);
}


/* =========================================
   SKILLS
========================================= */

.card-grid {
  display: grid;

  grid-template-columns:
    repeat(2, minmax(0, 1fr));

  gap: 1.1rem;

  margin-top: 3.5rem;
}


.glass-card {
  min-height: 200px;

  padding: 1.65rem;

  border:
    1px solid
    rgba(255, 255, 255, 0.08);

  background:
    rgba(255, 255, 255, 0.03);

  backdrop-filter: blur(14px);

  transition:
    transform 0.3s ease,
    background 0.3s ease,
    border-color 0.3s ease;
}


.glass-card:hover {
  transform:
    translateY(-7px);

  background:
    rgba(255, 255, 255, 0.05);

  border-color:
    rgba(255, 255, 255, 0.25);

  box-shadow: 0 18px 40px rgba(0, 0, 0, 0.25);
}


.glass-card > span {
  font-size: 0.8rem;

  color:
    rgba(245, 247, 251, 0.38);
}


.glass-card h3 {
  margin:
    1.6rem
    0
    0.7rem;

  font-size: 1.35rem;

  font-weight: 500;
}


.glass-card p {
  margin: 0;

  line-height: 1.8;

  color:
    rgba(245, 247, 251, 0.58);
}


/* =========================================
   PROJECTS
========================================= */

.project-grid {
  display: grid;

  grid-template-columns:
    repeat(2, minmax(0, 1fr));

  gap: 1.1rem;

  margin-top: 3.5rem;
}


.project-card {
  min-height: 380px;

  display: flex;

  flex-direction: column;

  justify-content: flex-end;

  padding: 1.85rem;

  border:
    1px solid
    rgba(255, 255, 255, 0.08);

  background:
    linear-gradient(
      145deg,
      rgba(255, 255, 255, 0.06),
      rgba(255, 255, 255, 0.015)
    );

  transition:
    transform 0.35s ease,
    border-color 0.35s ease;
}


.project-card:hover {
  transform:
    translateY(-8px);

  border-color:
    rgba(255, 255, 255, 0.22);

  box-shadow: 0 22px 44px rgba(0, 0, 0, 0.28);
}


.project-number {
  margin-bottom: auto;

  font-size: 0.8rem;

  color:
    rgba(245, 247, 251, 0.4);
}


.project-card h3 {
  margin: 0;

  font-size: 1.7rem;

  font-weight: 500;
}


.project-card p {
  margin:
    0.8rem
    0
    0;

  line-height: 1.85;

  color:
    rgba(245, 247, 251, 0.62);
}


.project-tags {
  display: flex;

  flex-wrap: wrap;

  gap: 0.55rem;

  margin-top: 1.2rem;
}


.project-tags span {
  padding: 0.4rem 0.7rem;

  border:
    1px solid
    rgba(255, 255, 255, 0.12);

  border-radius: 999px;

  font-size: 0.75rem;

  color:
    rgba(245, 247, 251, 0.68);
}


/* =========================================
   CONTACT
========================================= */

.contact-section {
  min-height: auto;
}


.contact-text {
  max-width: 650px;

  margin-top: 2rem;

  font-size: 1.16rem;

  line-height: 1.9;

  color:
    rgba(245, 247, 251, 0.66);
}


.contact-links {
  display: flex;

  flex-wrap: wrap;

  gap: 1rem;

  margin-top: 2.5rem;
}


.contact-links a {
  padding: 1rem 1.3rem;

  border:
    1px solid
    rgba(255, 255, 255, 0.14);

  text-decoration: none;

  color: #ffffff;

  transition:
    background 0.25s ease,
    color 0.25s ease,
    transform 0.25s ease,
    border-color 0.25s ease;
}


.contact-links a:hover {
  background: #ffffff;

  color: #000000;

  transform: translateY(-3px);

  border-color: #ffffff;
}


/* =========================================
   TABLET
========================================= */

@media (max-width: 900px) {

  .hero {
    padding:
      5rem
      6vw;
  }


  .hero-meta {
    display: none;
  }


  .about-grid {
    grid-template-columns: 1fr;

    gap: 4rem;
  }


  .card-grid,
  .project-grid {
    grid-template-columns:
      repeat(2, minmax(0, 1fr));
  }

}


/* =========================================
   MOBILE
========================================= */

@media (max-width: 650px) {

  .hero {
    min-height:
      calc(100vh - 72px);

    align-items: flex-end;

    padding: 4rem 6vw 5rem;
  }


  h1 {
  margin: 0;

  font-size: clamp(5rem, 10vw, 10rem);
  }

.description {
  max-width: 560px;

  margin: 2.5rem 0 0;

  font-size: clamp(1.05rem, 1.4vw, 1.3rem);
}

  .specialties {
    font-size: 0.78rem;
    line-height: 1.8;
  }


  .hero-actions {
    flex-direction: column;

    align-items: stretch;

    width:
      min(100%, 320px);
  }


  .primary-button,
  .secondary-button {
    width: 100%;
  }


  .scroll-indicator {
    display: none;
  }


  .page-section {
    
    padding: 7rem 6vw;
  }


  .card-grid,
  .project-grid {
    grid-template-columns: 1fr;
  }


  .about-grid {
    margin-top: 3rem;
  }

}
</style>