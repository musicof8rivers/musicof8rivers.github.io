<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>8Rivers</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Open+Sans&display=swap" rel="stylesheet">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Open Sans', sans-serif; background: #000; color: #fff; }
    a { color: inherit; text-decoration: none; }

    /* Navbar */
    header { position: fixed; width: 100%; top: 0; left: 0; z-index: 100; }
    .navbar {
      display: flex; justify-content: space-between; align-items: center;
      padding: 1rem 2rem; transition: background-color 0.3s ease;
    }
    .nav-links { display: flex; list-style: none; }
    .nav-links li { margin-left: 1.5rem; }
    .nav-links a:hover { color: #ddd; }
    header.scrolled .navbar { background-color: rgba(0,0,0,0.8); }

    /* Hero Section */
    #hero {
      height: 100vh;
      background: url('hero.jpg') center center / cover no-repeat;
      position: relative;
    }
    .hero-overlay {
      position: absolute; top: 0; left: 0; height: 100%; width: 100%;
      background: rgba(0,0,0,0.5);
    }
    .hero-content {
      position: relative; z-index: 1; height: 100%;
      display: flex; flex-direction: column;
      justify-content: center; align-items: center; text-align: center;
      padding: 0 2rem;
    }
    .hero-content h1 {
      font-family: 'Playfair Display', serif; font-size: 3rem; margin-bottom: 1rem;
    }
    .hero-content p { font-size: 1.5rem; }

    /* Sections */
    section { padding: 5rem 2rem; max-width: 1100px; margin: auto; }
    h2 { font-family: 'Playfair Display', serif; font-size: 2rem; margin-bottom: 1rem; }
    p { line-height: 1.6; }

    /* Works Grid */
    .works-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }
    .work-item {
      background: #111; border-radius: 12px; overflow: hidden;
      transition: transform 0.3s; cursor: pointer; position: relative;
    }
    .work-item:hover { transform: translateY(-5px); }
    .work-item img {
      width: 100%; height: auto; display: block;
      filter: grayscale(100%);
      transition: filter 0.5s ease;
    }
    .work-item:hover img { filter: grayscale(0%); }
    .work-item h3 { padding: 1rem; font-size: 1.2rem; text-align: center; }

    /* Contact */
    form { display: flex; flex-direction: column; gap: 1rem; }
    input, textarea {
      padding: 0.8rem; border: none; border-radius: 6px; font-family: inherit;
    }
    button {
      background: #444; color: #fff; border: none; padding: 0.8rem;
      border-radius: 6px; cursor: pointer; transition: background 0.3s;
    }
    button:hover { background: #666; }

    /* Footer */
    footer { text-align: center; padding: 2rem; color: #aaa; background: #000; }
  </style>
</head>
<body>
  <!-- Navbar -->
  <header id="main-header">
    <nav class="navbar">
      <a href="#hero" class="logo">8Rivers</a>
      <ul class="nav-links">
        <li><a href="#about">About</a></li>
        <li><a href="#works">Works</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- Hero -->
  <section id="hero">
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <h1>We Tell Stories in Code</h1>
      <p>Design · Development · Creativity</p>
    </div>
  </section>

  <!-- About -->
  <section id="about">
    <h2>About</h2>
    <p>
      8Rivers is a creative digital studio exploring the intersection of design,
      technology, and storytelling. Our mission is to craft meaningful experiences
      through elegant code and thoughtful visuals.
    </p>
  </section>

  <!-- Works -->
  <section id="works">
    <h2>Works</h2>
    <div class="works-grid">
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 1</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 2</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 3</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 4</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 5</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 6</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 7</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 8</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 9</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 10</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 11</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 12</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 13</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 14</h3>
      </a>
      <a href="https://example.com" target="_blank" class="work-item">
        <img src="d86.jpg" alt="Work d86" />
        <h3>Project 15</h3>
      </a>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea rows="5" placeholder="Your Message"></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <!-- Footer -->
  <footer>
    <p>© 2025, 8Rivers. All rights reserved.</p>
  </footer>

  <script>
    // Navbar scroll background
    window.addEventListener('scroll', () => {
      const header = document.getElementById('main-header');
      if (window.scrollY > 50) {
        header.classList.add('scrolled');
      } else {
        header.classList.remove('scrolled');
      }
    });

    // Smooth scrolling
    document.querySelectorAll('.nav-links a').forEach(anchor => {
      anchor.addEventListener('click', function(e) {
        e.preventDefault();
        const targetId = this.getAttribute('href').slice(1);
        const targetEl = document.getElementById(targetId);
        if (targetEl) {
          targetEl.scrollIntoView({ behavior: 'smooth' });
        }
      });
    });
  </script>
</body>
</html>
