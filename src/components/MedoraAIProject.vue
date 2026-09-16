<template>
  <article class="medora-card">

    <!-- Top -->
    <div class="top-row">

      <span class="project-number">
        01 / 03
      </span>

      <span class="project-type">
        MULTI-AGENT AI
      </span>

    </div>


    <!-- Main -->
    <div class="main-content">

      <div class="project-info">

        <p class="eyebrow">
          GOAL-DRIVEN HEALTHCARE SYSTEM
        </p>

        <h3>
          MedoraAI
        </h3>

        <p class="description">
          A goal-driven multi-agent healthcare system
          designed for Sri Lankan patients.
        </p>


        <!-- Technology -->
        <div class="tech-list">

          <span>Python</span>
          <span>LangGraph</span>
          <span>Gemini</span>
          <span>Tavily</span>
          <span>Mem0</span>
          <span>Qdrant</span>

        </div>


        <!-- CTA -->
        <a
          href="#"
          class="case-study-link"
        >
          <span>VIEW CASE STUDY</span>
          <span class="arrow">↗</span>
        </a>

      </div>


      <!-- Architecture visual -->
      <div class="architecture-visual">

        <div class="architecture-glow"></div>

        <div class="node node-main">
          MedoraAI
        </div>

        <div class="connection connection-one"></div>
        <div class="connection connection-two"></div>
        <div class="connection connection-three"></div>

        <div class="node node-small node-one">
          Patient
        </div>

        <div class="node node-small node-two">
          Appointment
        </div>

        <div class="node node-small node-three">
          Doctor
        </div>

        <div class="node node-small node-four">
          Report
        </div>

      </div>

    </div>


    <!-- Bottom information -->
    <div class="bottom-row">

      <div class="bottom-item">

        <span class="label">
          ARCHITECTURE
        </span>

        <span class="value">
          Observe → Reason → Execute
        </span>

      </div>


      <div class="bottom-item">

        <span class="label">
          WORKFLOW
        </span>

        <span class="value">
          Appointment Booking
        </span>

      </div>


      <div class="bottom-item">

        <span class="label">
          FOCUS
        </span>

        <span class="value">
          Shared state + agent selection
        </span>

      </div>

    </div>

  </article>
</template>


<style scoped>

/* =====================================================
   CARD
===================================================== */

.medora-card {
  position: relative;

  width: 100%;

  padding: clamp(1.5rem, 4vw, 3rem);

  overflow: hidden;

  border:
    1px solid
    rgba(255, 255, 255, 0.12);

  background:
    linear-gradient(
      135deg,
      rgba(255, 255, 255, 0.075),
      rgba(255, 255, 255, 0.018)
    );

  backdrop-filter: blur(18px);

  transition:
    border-color 0.35s ease,
    transform 0.35s ease;
}


.medora-card:hover {
  border-color:
    rgba(255, 255, 255, 0.25);

  transform:
    translateY(-5px);
}


/* =====================================================
   GRID BACKGROUND
===================================================== */

.medora-card::before {
  content: "";

  position: absolute;

  inset: 0;

  background-image:
    linear-gradient(
      rgba(255, 255, 255, 0.025) 1px,
      transparent 1px
    ),
    linear-gradient(
      90deg,
      rgba(255, 255, 255, 0.025) 1px,
      transparent 1px
    );

  background-size:
    50px 50px;

  opacity: 0.4;

  pointer-events: none;
}


/* =====================================================
   TOP ROW
===================================================== */

.top-row {
  position: relative;

  z-index: 2;

  display: flex;

  align-items: center;

  justify-content: space-between;

  padding-bottom: 1.5rem;

  border-bottom:
    1px solid
    rgba(255, 255, 255, 0.08);
}


.project-number,
.project-type {
  font-size: 0.6rem;

  letter-spacing: 0.22em;

  color:
    rgba(255, 255, 255, 0.42);
}


.project-number {
  color: #ffffff;
}


/* =====================================================
   MAIN CONTENT
===================================================== */

.main-content {
  position: relative;

  z-index: 2;

  display: grid;

  grid-template-columns:
    0.9fr
    1.1fr;

  gap: 4rem;

  padding:
    4rem
    0;
}


.project-info {
  align-self: center;
}


.eyebrow {
  margin: 0 0 1rem;

  font-size: 0.72rem;

  letter-spacing: 0.26em;

  color:
    rgba(255, 255, 255, 0.38);
}


.project-info h3 {
  margin: 0;

  font-size:
    clamp(3.5rem, 7vw, 7rem);

  line-height: 0.85;

  letter-spacing: -0.07em;

  font-weight: 500;
}


.description {
  max-width: 480px;

  margin:
    2rem
    0
    0;

  font-size: 1.05rem;

  line-height: 1.8;

  color:
    rgba(245, 247, 251, 0.76);
}


/* =====================================================
   TECHNOLOGY
===================================================== */

.tech-list {
  display: flex;

  flex-wrap: wrap;

  gap: 0.5rem;

  margin-top: 1.8rem;
}


.tech-list span {
  padding:
    0.45rem
    0.7rem;

  border:
    1px solid
    rgba(255, 255, 255, 0.1);

  border-radius: 999px;

  font-size: 0.68rem;

  letter-spacing: 0.06em;

  color:
    rgba(245, 247, 251, 0.76);

  background:
    rgba(255, 255, 255, 0.02);
}


/* =====================================================
   CASE STUDY LINK
===================================================== */

.case-study-link {
  display: inline-flex;

  align-items: center;

  gap: 1rem;

  margin-top: 2rem;

  padding-bottom: 0.5rem;

  border-bottom:
    1px solid
    rgba(255, 255, 255, 0.35);

  text-decoration: none;

  font-size: 0.74rem;

  letter-spacing: 0.16em;

  color: #ffffff;

  transition:
    gap 0.3s ease,
    border-color 0.3s ease;
}


.case-study-link:hover {
  gap: 1.4rem;

  border-color: #ffffff;
}


.arrow {
  font-size: 1rem;

  letter-spacing: 0;
}


/* =====================================================
   ARCHITECTURE VISUAL
===================================================== */

.architecture-visual {
  position: relative;

  min-height: 420px;

  display: flex;

  align-items: center;

  justify-content: center;

  overflow: hidden;

  border:
    1px solid
    rgba(255, 255, 255, 0.08);

  background:
    radial-gradient(
      circle at center,
      rgba(255, 255, 255, 0.08),
      rgba(255, 255, 255, 0.015) 50%,
      transparent 75%
    );
}


/* Glow */

.architecture-glow {
  position: absolute;

  width: 180px;
  height: 180px;

  border-radius: 50%;

  background:
    rgba(255, 255, 255, 0.09);

  filter: blur(60px);
}


/* Main node */

.node-main {
  position: relative;

  z-index: 3;

  width: 150px;
  height: 150px;

  display: flex;

  align-items: center;

  justify-content: center;

  border:
    1px solid
    rgba(255, 255, 255, 0.35);

  border-radius: 50%;

  background:
    rgba(255, 255, 255, 0.05);

  box-shadow:
    0 0 80px
    rgba(255, 255, 255, 0.08);

  font-size: 1.08rem;

  letter-spacing: 0.05em;
}


/* Small nodes */

.node-small {
  position: absolute;

  z-index: 3;

  padding:
    0.75rem
    1rem;

  border:
    1px solid
    rgba(255, 255, 255, 0.18);

  background:
    rgba(5, 5, 5, 0.7);

  backdrop-filter: blur(8px);

  font-size: 0.7rem;

  letter-spacing: 0.08em;

  color:
    rgba(245, 247, 251, 0.78);
}


.node-one {
  top: 18%;

  left: 10%;
}


.node-two {
  top: 18%;

  right: 10%;
}


.node-three {
  bottom: 18%;

  right: 10%;
}


.node-four {
  bottom: 18%;

  left: 10%;
}


/* =====================================================
   CONNECTIONS
===================================================== */

.connection {
  position: absolute;

  height: 1px;

  background:
    linear-gradient(
      90deg,
      transparent,
      rgba(216, 178, 76, 0.42),
      transparent
    );

  transform-origin: center;
}


.connection-one {
  width: 35%;

  top: 36%;

  left: 17%;

  transform:
    rotate(22deg);
}


.connection-two {
  width: 35%;

  top: 36%;

  right: 17%;

  transform:
    rotate(-22deg);
}


.connection-three {
  width: 35%;

  bottom: 36%;

  right: 17%;

  transform:
    rotate(22deg);
}


/* =====================================================
   BOTTOM ROW
===================================================== */

.bottom-row {
  position: relative;

  z-index: 2;

  display: grid;

  grid-template-columns:
    repeat(3, 1fr);

  border-top:
    1px solid rgba(255, 255, 255, 0.08);
}


.bottom-item {
  display: flex;

  flex-direction: column;

  gap: 0.5rem;

  padding:
    1.15rem 1rem;

  border-right:
    1px solid
    rgba(255, 255, 255, 0.08);
}


.bottom-item:last-child {
  border-right: none;
}


.label {
  font-size: 0.72rem;

  letter-spacing: 0.24em;

  color:
    rgba(245, 247, 251, 0.48);
}


.value {
  font-size: 0.9rem;

  color:
    rgba(245, 247, 251, 0.82);
}


/* =====================================================
   RESPONSIVE
===================================================== */

@media (max-width: 900px) {

  .main-content {
    grid-template-columns: 1fr;

    gap: 2rem;
  }

  .architecture-visual {
    min-height: 320px;
  }

}


@media (max-width: 600px) {

  .medora-card {
    padding: 1.1rem;
  }

  .main-content {
    padding:
      2.25rem 0;
  }

  .architecture-visual {
    min-height: 280px;
  }

  .node-main {
    width: 104px;
    height: 104px;
  }

  .bottom-row {
    grid-template-columns: 1fr;
  }

  .bottom-item {
    border-right: none;

    border-bottom:
      1px solid
      rgba(255, 255, 255, 0.08);
  }

  .bottom-item:last-child {
    border-bottom: none;
  }

}
</style>