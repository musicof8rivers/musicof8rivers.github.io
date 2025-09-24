<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Music of 8 Rivers | Portfolio</title>
  <style>
    /* Reset + Base */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: Arial, Helvetica, sans-serif;
      background: #0a0a0a;
      color: #eaeaea;
      line-height: 1.6;
      scroll-behavior: smooth;
    }
    a { color: inherit; text-decoration: none; }
    h1, h2 { font-weight: bold; }

    /* Navigation */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      background: rgba(0,0,0,0.8);
      display: flex; justify-content: center;
      padding: 1rem;
      z-index: 1000;
    }
    nav ul { display: flex; gap: 2rem; list-style: none; }
    nav a { transition: color 0.3s; }
    nav a:hover { color: #00ffaa; }

    /* Sections */
    section {
      min-height: 100vh;
      padding: 5rem 2rem;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
    }

    /* Hero */
    #home {
      background: linear-gradient(135deg, #111, #222);
    }
    #home h1 {
      font-size: 3rem;
      background: linear-gradient(90deg, #00ffaa, #00ccff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 1rem;
    }
    #home p { font-size: 1.2rem; color: #bbb; }

    /* About */
    #about { background: #141414; }
    #about h2 { font-size: 2rem; margin-bottom: 1rem; }

    /* Projects */
    #projects { background: #191919; }
    #projects h2 { font-size: 2rem; margin-bottom: 2rem; }
    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
      width: 100%;
      max-width: 1000px;
    }
    .project {
      background: #222;
      padding: 1.5rem;
      border-radius: 10px;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .project:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0,255,170,0.3);
    }

    /* Contact */
    #contact { background: #141414; }
    #contact h2 { font-size: 2rem; margin-bottom: 1rem; }
    #contact p { margin-bottom: 1rem; }

    /* Footer */
    footer {
      background: #0a0a0a;
      padding: 1rem;
      text-align: center;
      font-size: 0.9rem;
      color: #777;
    }

    /* Responsive */
    @media (max-width: 600px) {
      #home h1 { font-size: 2rem; }
      nav ul { gap: 1rem; }
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <nav>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- Hero -->
  <section id="home">
    <h1>Music of 8 Rivers</h1>
    <p>Welcome to my portfolio. Explore my work, ideas, and projects.</p>
  </section>

  <!-- About -->
  <section id="about">
    <h2>About Me</h2>
    <p>
      I’m a creator passionate about blending art, music, and technology.  
      This portfolio is a place where I share my journey and experiments.
    </p>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>Projects</h2>
    <div class="project-grid">
      <div class="project">
        <h3>Project One</h3>
        <p>A short description of this project. Maybe a link to GitHub or demo.</p>
      </div>
      <div class="project">
        <h3>Project Two</h3>
        <p>Another project you’re proud of. Describe what it does and why it matters.</p>
      </div>
      <div class="project">
        <h3>Project Three</h3>
        <p>Keep adding more projects as you go — this grid is expandable.</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact</h2>
    <p>If you’d like to connect, feel free to reach out:</p>
    <p>
      <a href="mailto:your@email.com">your@email.com</a><br>
      <a href="https://github.com/musicof8rivers" target="_blank">GitHub</a> | 
      <a href="https://linkedin.com" target="_blank">LinkedIn</a>
    </p>
  </section>

  <!-- Footer -->
  <footer>
    <p>&copy; 2025 Music of 8 Rivers. All rights reserved.</p>
  </footer>

</body>
</html>
