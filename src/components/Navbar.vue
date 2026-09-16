<template>
  <header class="navbar">
    <a href="#about" class="logo">
      GV.
    </a>

    <nav class="nav-links">
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#experience">Experience</a>
      <a href="#contact">Contact</a>
    </nav>

    <a href="/cv.pdf" class="resume-button">
      Resume
      <span>↗</span>
    </a>
  </header>
</template>

<style scoped>
.navbar {
  position: fixed;

  top: 0;
  left: 0;
  right: 0;

  min-height: 76px;

  z-index: 20;

  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 0.9rem 4vw;

  background: rgba(5, 7, 13, 0.92);

  backdrop-filter: blur(14px);
  -webkit-backdrop-filter: blur(14px);

  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.logo {
  font-size: 1.35rem;
  font-weight: 600;

  letter-spacing: -0.06em;

  text-decoration: none;

  color: #f5f7fb;
}

.nav-links {
  display: flex;
  align-items: center;

  gap: 2rem;
}

.nav-links a,
.resume-button {
  font-size: 0.72rem;

  text-transform: uppercase;
  letter-spacing: 0.18em;

  text-decoration: none;

  color: rgba(245, 247, 251, 0.62);

  transition:
    color 0.25s ease,
    border-color 0.25s ease;
}

.nav-links a:hover {
  color: #d8b24c;
}

.resume-button {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;

  padding: 0.65rem 1rem;

  border: 1px solid rgba(216, 178, 76, 0.34);

  border-radius: 999px;
}

.resume-button:hover {
  color: #d8b24c;

  border-color: rgba(216, 178, 76, 0.82);
}

@media (max-width: 800px) {
  .nav-links {
    display: none;
  }

  .navbar {
    min-height: 72px;
    padding: 0.8rem 5vw;
  }

  .resume-button {
    padding: 0.55rem 0.85rem;
    font-size: 0.68rem;
  }
}
</style>