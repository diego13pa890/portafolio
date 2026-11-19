#

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Portafolio personal de Diego Núñez: aprendizaje, programación, Arduino, pixel art y proyectos.">
  <meta name="theme-color" content="#0b0d12">
  <title>Diego Núñez | Portafolio</title>

  <style>
    :root {
      color-scheme: dark;
      --bg: #0b0d12;
      --surface: #11151d;
      --surface-2: #151b25;
      --line: rgba(255,255,255,.09);
      --text: #f2f4f8;
      --muted: #a0a8b7;
      --accent: #ff5364;
      --accent-soft: rgba(255,83,100,.12);
      --max: 1080px;
      --radius: 18px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 90px;
    }

    body {
      min-height: 100vh;
      background:
        radial-gradient(ellipse at 78% 8%, rgba(255,83,100,.10), transparent 32rem),
        var(--bg);
      color: var(--text);
      font-family: Inter, "Segoe UI", system-ui, -apple-system, sans-serif;
      line-height: 1.7;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    a:focus-visible,
    button:focus-visible {
      outline: 3px solid var(--accent);
      outline-offset: 4px;
      border-radius: 6px;
    }

    .container {
      width: min(var(--max), calc(100% - 3rem));
      margin-inline: auto;
    }

    /* NAVEGACIÓN */

    .site-header {
      position: sticky;
      top: 0;
      z-index: 10;
      background: rgba(11,13,18,.82);
      border-bottom: 1px solid var(--line);
      backdrop-filter: blur(16px);
    }

    .nav {
      min-height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1.5rem;
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: .7rem;
      font-weight: 750;
      letter-spacing: .02em;
    }

    .brand-mark {
      width: 11px;
      height: 11px;
      border-radius: 4px;
      background: var(--accent);
      box-shadow: 0 0 20px rgba(255,83,100,.65);
      transform: rotate(45deg);
    }

    .brand span:last-child {
      color: var(--accent);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 1.7rem;
      list-style: none;
    }

    .nav-links a {
      color: var(--muted);
      font-size: .92rem;
      transition: color .2s;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .menu-toggle {
      display: none;
      border: 1px solid var(--line);
      color: var(--text);
      background: var(--surface);
      border-radius: 10px;
      padding: .55rem .8rem;
      font: inherit;
      cursor: pointer;
    }

    /* PRESENTACIÓN */

    .hero {
      padding: clamp(5rem, 12vw, 9rem) 0 6rem;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: .6rem;
      padding: .45rem .8rem;
      margin-bottom: 1.6rem;
      border: 1px solid rgba(255,83,100,.28);
      border-radius: 999px;
      background: var(--accent-soft);
      color: #ff9aa4;
      font-size: .78rem;
      font-weight: 700;
      letter-spacing: .09em;
      text-transform: uppercase;
    }

    .eyebrow::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--accent);
    }

    h1 {
      max-width: 850px;
      font-size: clamp(3.2rem, 9vw, 6.5rem);
      line-height: .98;
      letter-spacing: -.065em;
      font-weight: 800;
    }

    .accent {
      color: var(--accent);
    }

    .hero-copy {
      max-width: 650px;
      margin-top: 1.7rem;
      color: var(--muted);
      font-size: clamp(1.05rem, 2vw, 1.22rem);
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 1rem;
      margin-top: 2.2rem;
    }

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: .6rem;
      min-height: 48px;
      padding: .75rem 1.2rem;
      border-radius: 10px;
      background: var(--accent);
      color: #16090b;
      font-weight: 750;
      transition: transform .2s, box-shadow .2s, background .2s;
    }

    .button:hover {
      transform: translateY(-3px);
      box-shadow: 0 12px 30px rgba(255,83,100,.2);
      background: #ff7180;
    }

    .text-link {
      color: var(--muted);
      font-weight: 650;
      transition: color .2s;
    }

    .text-link:hover {
      color: var(--text);
    }

    /* SECCIONES */

    section {
      padding: 5rem 0;
      border-top: 1px solid var(--line);
    }

    .section-heading {
      margin-bottom: 2rem;
    }

    .section-kicker {
      color: var(--accent);
      font-size: .75rem;
      font-weight: 800;
      letter-spacing: .16em;
      text-transform: uppercase;
    }

    h2 {
      margin-top: .35rem;
      font-size: clamp(1.8rem, 4vw, 2.6rem);
      letter-spacing: -.04em;
    }

    .about-copy {
      max-width: 790px;
      color: #c2c8d2;
    }

    .about-copy p + p {
      margin-top: 1rem;
    }

    .about-copy strong {
      color: var(--text);
    }

    /* HABILIDADES Y PROYECTOS */

    .skills-grid,
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 1rem;
    }

    .card {
      min-width: 0;
      padding: 1.5rem;
      border: 1px solid var(--line);
      border-radius: var(--radius);
      background: linear-gradient(145deg, var(--surface-2), var(--surface));
      transition: transform .22s ease, border-color .22s ease;
    }

    .card:hover {
      transform: translateY(-5px);
      border-color: rgba(255,83,100,.45);
    }

    .card-icon {
      display: grid;
      place-items: center;
      width: 42px;
      height: 42px;
      margin-bottom: 1.1rem;
      border-radius: 12px;
      background: var(--accent-soft);
      color: #ff8793;
      font-size: 1.15rem;
      font-weight: 800;
    }

    .card h3 {
      font-size: 1.05rem;
      margin-bottom: .45rem;
    }

    .card p {
      color: var(--muted);
      font-size: .92rem;
      line-height: 1.65;
    }

    .project-status {
      display: inline-block;
      margin-bottom: 1rem;
      padding: .3rem .65rem;
      border: 1px solid rgba(255,83,100,.28);
      border-radius: 999px;
      color: #ff9aa4;
      background: var(--accent-soft);
      font-size: .7rem;
      font-weight: 750;
      letter-spacing: .08em;
      text-transform: uppercase;
    }

    /* CONTACTO */

    .contact-panel {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 2rem;
      padding: clamp(1.5rem, 5vw, 2.5rem);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      background: var(--surface);
    }

    .contact-panel p {
      max-width: 520px;
      margin-top: .6rem;
      color: var(--muted);
    }

    .contact-links {
      display: flex;
      flex-direction: column;
      gap: .8rem;
      flex-shrink: 0;
    }

    .contact-links a {
      color: var(--text);
      overflow-wrap: anywhere;
    }

    .contact-links a:hover {
      color: var(--accent);
    }

    /* PIE DE PÁGINA */

    footer {
      padding: 2rem 0;
      border-top: 1px solid var(--line);
      color: var(--muted);
      font-size: .85rem;
      text-align: center;
    }

    footer span {
      color: var(--accent);
    }

    /* TABLETS */

    @media (max-width: 800px) {
      .skills-grid,
      .projects-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .contact-panel {
        align-items: flex-start;
        flex-direction: column;
      }
    }

    /* CELULARES */

    @media (max-width: 620px) {
      .container {
        width: min(100% - 2rem, var(--max));
      }

      .nav {
        min-height: 68px;
        flex-wrap: wrap;
        padding-block: .7rem;
      }

      .menu-toggle {
        display: inline-flex;
      }

      .nav-links {
        display: none;
        width: 100%;
        padding: .5rem 0 .8rem;
        flex-direction: column;
        align-items: flex-start;
        gap: .9rem;
      }

      .nav-links.open {
        display: flex;
      }

      .hero {
        padding: 5rem 0 4.5rem;
      }

      section {
        padding: 4rem 0;
      }

      .skills-grid,
      .projects-grid {
        grid-template-columns: 1fr;
      }

      .hero-actions {
        align-items: stretch;
        flex-direction: column;
      }

      .button {
        width: 100%;
      }
    }

    /* ACCESIBILIDAD */

    @media (prefers-reduced-motion: reduce) {
      *,
      *::before,
      *::after {
        scroll-behavior: auto !important;
        transition-duration: .01ms !important;
        animation-duration: .01ms !important;
      }
    }
  </style>
</head>

<body>

  <!-- NAVEGACIÓN -->

  <header class="site-header">
    <nav class="nav container" aria-label="Navegación principal">

      <a class="brand" href="#inicio" aria-label="Ir al inicio">
        <span class="brand-mark" aria-hidden="true"></span>
        <span>PORTAFOLIO</span>
        <span>// DIEGO NÚÑEZ</span>
      </a>

      <button class="menu-toggle" type="button"
        aria-expanded="false" aria-controls="nav-links">
        Menú
      </button>

      <ul class="nav-links" id="nav-links">
        <li><a href="#sobre-mi">Sobre mí</a></li>
        <li><a href="#habilidades">Habilidades</a></li>
        <li><a href="#proyectos">Proyectos</a></li>
        <li><a href="#contacto">Contacto</a></li>
      </ul>

    </nav>
  </header>

  <main>

    <!-- PRESENTACIÓN -->

    <div class="hero container" id="inicio">

      <div class="eyebrow">
        Estudiante · 4.º año de Tecnología
      </div>

      <h1>
        Hola, soy<br>
        <span class="accent">Diego Núñez.</span>
      </h1>

      <p class="hero-copy">
        Tengo 16 años y estoy explorando el mundo del desarrollo
        de software y la ciberseguridad.
        Aprendo por curiosidad, experimento con ideas y convierto
        lo que voy aprendiendo en proyectos.
      </p>

      <div class="hero-actions">
        <a class="button" href="#proyectos">
          Explorar proyectos <span aria-hidden="true">↗</span>
        </a>

        <a class="text-link" href="#sobre-mi">
          Conoce más sobre mí ↓
        </a>
      </div>

    </div>

    <!-- SOBRE MÍ -->

    <section id="sobre-mi">
      <div class="container">

        <div class="section-heading">
          <span class="section-kicker">Un poco de contexto</span>
          <h2>Sobre mí</h2>
        </div>

        <div class="about-copy">

          <p>
            Soy <strong>Diego Núñez</strong>, tengo 16 años y estoy
            en 4.º año del bachillerato de tecnología.
            Me interesan el desarrollo de software y la ingeniería
            de sistemas; todavía estoy descubriendo cuál de estos
            caminos me llama más. También participo en
            <strong>CIBERISTMO</strong>, donde encuentro retos
            interesantes para aprender sobre ciberseguridad.
          </p>

          <p>
            Llevo <strong>dos años aprendiendo Arduino</strong>
            a nivel básico, incluyendo programación en bloques.
            También realicé un curso de programación en
            <strong>Python</strong> aplicado a Arduino y conservo
            el material que utilicé. Actualmente sigo aprendiendo
            por mi cuenta y practicando <strong>pixel art</strong>
            para un proyecto personal.
          </p>

          <p>
            Me gusta aprender, experimentar y divertirme durante
            el proceso. La mayoría de mis proyectos han nacido
            de ideas propias; algunos siguen en desarrollo y otros
            están en pausa, pero todos me han dejado nuevos
            conocimientos.
          </p>

        </div>
      </div>
    </section>

    <!-- HABILIDADES -->

    <section id="habilidades">
      <div class="container">

        <div class="section-heading">
          <span class="section-kicker">Lo que estoy aprendiendo</span>
          <h2>Habilidades</h2>
        </div>

        <div class="skills-grid">

          <article class="card">
            <div class="card-icon" aria-hidden="true">Py</div>
            <h3>Python</h3>
            <p>
              Fundamentos de programación y lógica aprendidos
              mediante un curso aplicado a Arduino.
            </p>
          </article>

          <article class="card">
            <div class="card-icon" aria-hidden="true">A</div>
            <h3>Arduino</h3>
            <p>
              Dos años de práctica básica, experimentando
              también con programación en bloques.
            </p>
          </article>

          <article class="card">
            <div class="card-icon" aria-hidden="true">{}</div>
            <h3>Lógica de programación</h3>
            <p>
              Práctica con problemas, condicionales, ciclos
              y estructuras de datos sencillas.
            </p>
          </article>

          <article class="card">
            <div class="card-icon" aria-hidden="true">Px</div>
            <h3>Pixel art</h3>
            <p>
              En aprendizaje y experimentación como parte
              de un proyecto personal.
            </p>
          </article>

          <article class="card">
            <div class="card-icon" aria-hidden="true">&lt;/&gt;</div>
            <h3>HTML y CSS</h3>
            <p>
              Aprendiendo desarrollo web mientras construyo
              y mejoro este portafolio.
            </p>
          </article>

          <article class="card">
            <div class="card-icon" aria-hidden="true">Git</div>
            <h3>Git y GitHub</h3>
            <p>
              Explorando el control de versiones y la publicación
              de proyectos con GitHub Pages.
            </p>
          </article>

        </div>
      </div>
    </section>

    <!-- PROYECTOS -->

    <section id="proyectos">
      <div class="container">

        <div class="section-heading">
          <span class="section-kicker">Ideas en movimiento</span>
          <h2>Proyectos</h2>
        </div>

        <div class="projects-grid">

          <article class="card">
            <span class="project-status">En desarrollo</span>
            <h3>Proyecto personal de pixel art</h3>
            <p>
              Un proyecto personal para practicar pixel art
              y programación. Por ahora, estoy estudiando
              y experimentando con ideas.
            </p>
          </article>

          <article class="card">
            <span class="project-status">Aprendizaje</span>
            <h3>Retos de Python</h3>
            <p>
              Ejercicios de lógica y resolución de problemas,
              además de retos de ciberseguridad tipo
              Capture The Flag (CTF).
            </p>
          </article>

          <article class="card">
            <span class="project-status">En pausa</span>
            <h3>Experimentos con Arduino</h3>
            <p>
              Pequeños experimentos realizados por curiosidad
              durante los últimos dos años. Cada uno aportó
              una experiencia nueva.
            </p>
          </article>

        </div>
      </div>
    </section>

    <!-- CONTACTO -->

    <section id="contacto">
      <div class="container">

        <div class="section-heading">
          <span class="section-kicker">Hablemos</span>
          <h2>Contacto</h2>
        </div>

        <div class="contact-panel">

          <div>
            <h3>¿Quieres conocer más de mi trabajo?</h3>
            <p>
              Puedes escribirme por correo o visitar mi perfil
              de GitHub para ver mis proyectos y avances.
            </p>
          </div>

          <div class="contact-links">
            <a href="mailto:zenunogeid@gmail.com">
              ✉ zenunogeid@gmail.com
            </a>

            <a href="https://github.com/diego13pa890"
               target="_blank"
               rel="noopener noreferrer">
              ↗ github.com/diego13pa890
            </a>
          </div>

        </div>
      </div>
    </section>

  </main>

  <!-- PIE DE PÁGINA -->

  <footer>
    <div class="container">
      © 2026 Diego Núñez · Hecho con
      <span>HTML, CSS y curiosidad.</span>
    </div>
  </footer>

  <!-- JAVASCRIPT: MENÚ PARA CELULARES -->

  <script>
    const menuButton = document.querySelector(".menu-toggle");
    const navLinks = document.querySelector(".nav-links");

    menuButton.addEventListener("click", () => {
      const isOpen = navLinks.classList.toggle("open");

      menuButton.setAttribute(
        "aria-expanded",
        String(isOpen)
      );
    });

    navLinks.querySelectorAll("a").forEach((link) => {
      link.addEventListener("click", () => {
        navLinks.classList.remove("open");

        menuButton.setAttribute(
          "aria-expanded",
          "false"
        );
      });
    });
  </script>

</body>
</html>

