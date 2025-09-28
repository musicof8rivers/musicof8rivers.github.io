<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Film — Clint Mansell</title>
  <link rel="stylesheet" href="assets/css/style.css" />
  <style>
    /* --- Reset & base styles --- */
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #fff;
      color: #111;
    }
    a {
      color: inherit;
      text-decoration: none;
    }
    ul {
      list-style: none;
      margin: 0;
      padding: 0;
    }

    /* --- Header & nav --- */
    header {
      background: #000;
      color: #fff;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    nav ul {
      display: flex;
      gap: 1.5rem;
    }
    nav a {
      color: #fff;
      text-transform: lowercase;
      font-weight: bold;
    }
    .cart-info {
      font-size: 0.9rem;
    }

    /* --- Main --- */
    main {
      padding: 2rem;
    }
    h1 {
      text-transform: uppercase;
      margin-bottom: 1rem;
    }

    /* --- Slideshow --- */
    .slideshow {
      position: relative;
      max-width: 800px;
      margin: 0 auto 2rem auto;
      overflow: hidden;
    }
    .slide {
      display: none;
      position: absolute;
      width: 100%;
    }
    .slide.active {
      display: block;
      position: relative;
    }
    .slide img {
      width: 100%;
      height: auto;
      display: block;
      filter: grayscale(100%);
      transition: filter 0.4s ease;
    }
    .slide img:hover {
      filter: grayscale(0%);
    }
    .caption {
      background: rgba(0,0,0,0.6);
      color: #fff;
      padding: 0.5rem 1rem;
      position: absolute;
      bottom: 0;
      left: 0;
      font-size: 0.9rem;
    }
    .slide-prev,
    .slide-next {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0,0,0,0.5);
      border: none;
      color: #fff;
      font-size: 1.5rem;
      padding: 0.5rem 1rem;
      cursor: pointer;
    }
    .slide-prev { left: 0.5rem; }
    .slide-next { right: 0.5rem; }

    .slide-instructions {
      text-align: center;
      font-size: 0.85rem;
      color: #555;
      margin-top: 1rem;
    }

    /* --- Footer --- */
    footer {
      background: #111;
      color: #aaa;
      text-align: center;
      padding: 1rem;
    }
    footer .social a {
      margin: 0 0.5rem;
      color: #aaa;
    }
  </style>
</head>
<body>
  <header>
    <nav>
      <ul>
        <li><a href="about.html">about</a></li>
        <li><a href="works.html">works</a></li>
        <li><a href="berlin.html">berlin</a></li>
        <li><a href="videos.html">videos</a></li>
        <li><a href="shop.html">shop</a></li>
        <li><a href="contact.html">contact</a></li>
      </ul>
    </nav>
    <div class="cart-info">
      <a href="#">Cart (0 items)</a>
    </div>
  </header>

  <main>
    <section class="works-section">
      <h1>works</h1>
      <div class="slideshow">
        <div class="slide active">
          <img src="assets/img/film1.jpg" alt="Work 1">
          <div class="caption">Work 1 — description</div>
        </div>
        <div class="slide">
          <img src="assets/img/film2.jpg" alt="Work 2">
          <div class="caption">Work 2 — description</div>
        </div>
        <div class="slide">
          <img src="assets/img/film3.jpg" alt="Work 3">
          <div class="caption">Work 3 — description</div>
        </div>
        <button class="slide-prev">&#8249;</button>
        <button class="slide-next">&#8250;</button>
      </div>

      <div class="slide-instructions">
        Use left/right arrows to navigate the slideshow or swipe left/right if using a mobile device.<br />
        Press the space key then arrow keys to make a selection.
      </div>
    </section>
  </main>

  <footer>
    <div class="social">
      <a href="#">Instagram</a> | 
      <a href="#">Twitter</a> | 
      <a href="#">Facebook</a>
    </div>
    <div class="copyright">
      &copy; 2025 Clint Mansell
    </div>
  </footer>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      let slides = document.querySelectorAll(".slide");
      let current = 0;
      const showSlide = (idx) => {
        slides.forEach((s, i) => s.classList.toggle("active", i === idx));
      };
      document.querySelector(".slide-next").addEventListener("click", () => {
        current = (current + 1) % slides.length;
        showSlide(current);
      });
      document.querySelector(".slide-prev").addEventListener("click", () => {
        current = (current - 1 + slides.length) % slides.length;
        showSlide(current);
      });
      document.addEventListener("keydown", (e) => {
        if (e.key === "ArrowRight") {
          current = (current + 1) % slides.length;
          showSlide(current);
        } else if (e.key === "ArrowLeft") {
          current = (current - 1 + slides.length) % slides.length;
          showSlide(current);
        }
      });
    });
  </script>
</body>
</html>
