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

    /* HEADER + NAVBAR */
    header {
      position: fixed;
      width: 100%;
      top: 0;
      left: 0;
      z-index: 1000;
      background: #111;
      box-shadow: 0 2px 8px rgba(0,0,0,0.6);
    }

    .navbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 3rem;
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.8rem;
      font-weight: bold;
      color: #fff;
      letter-spacing: 1px;
    }

    .nav-links {
      display: flex;
      list-style: none;
      gap: 3rem;
    }

    .nav-links li a {
      font-size: 1.1rem;
      font-weight: bold;
      color: #f0f0f0;
      padding-bottom: 0.3rem;
      position: relative;
      transition: color 0.3s;
    }

    .nav-links li a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -4px;
      width: 0%;
      height: 2px;
      background: #e63946;
      transition: width 0.3s ease;
    }

    .nav-links li a:hover {
      color: #e63946;
    }

    .nav-links li a:hover::after {
      width: 100%;
    }

    /* HERO */
    #hero {
      height: 100vh;
      background: url('hero.jpg') center center / cover no-repeat;
      position: relative;
    }

    .hero-overlay {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.5);
    }

    .hero-content {
      position: relative;
      z-index: 1;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: #fff;
      padding: 0 2rem;
    }

    .hero-content h1 {
      font-family: 'Playfair Display', serif;
      font-size: 3.5rem;
      margin-bottom: 1rem;
    }

    .hero-content p {
      font-size: 1.3rem;
      color: #ddd;
    }

    /* SECTION STYLES */
    section {
      padding: 7rem 2rem 5rem;
      max-width: 1100px;
      margin: auto;
    }

    h2 {
      font-family: 'Playfair Display', serif;
      font-size: 2.2rem;
      margin-bottom: 1rem;
      color: #e63946;
      text-align: center;
    }

    p {
      line-height: 1.6;
      text-align: center;
      color: #ccc;
    }

    /* WORKS GRID */
    .works-grid {
      margin-top: 2rem;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }

    .work-item {
      background: #111;
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.3s;
      cursor: pointer;
      position: relative;
    }

    .work-item:hover { transform: translateY(-5px); }
    .work-item img {
      width: 100%;
      display: block;
      filter: grayscale(100%);
      transition: filter 0.5s ease;
    }
    .work-item:hover img { filter: grayscale(0%); }
    .work-item h3 {
      padding: 1rem;
      font-size: 1.1rem;
      text-align: center;
      color: #fff;
    }

    /* MODAL */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.9);
      justify-content: center;
      align-items: center;
      z-index: 2000;
      padding: 2rem;
      overflow-y: auto;
      opacity: 0;
      transform: scale(0.95);
      transition: opacity 0.3s ease, transform 0.3s ease;
    }

    .modal.show {
      display: flex;
      opacity: 1;
      transform: scale(1);
    }

    .modal-content {
      background: #111;
      padding: 1rem;
      border-radius: 10px;
      max-width: 850px;
      width: 100%;
      position: relative;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      text-align: center;
    }

    .modal-video-container iframe {
      width: 100%;
      height: 450px;
      border: none;
    }

    .modal-note-container {
      color: #ddd;
      padding: 1rem;
      background: #222;
      border-radius: 8px;
      text-align: left;
    }

    .close-btn {
      position: absolute;
      top: 15px;
      right: 15px;
      background: #e63946;
      color: #fff;
      border: none;
      font-size: 1.6rem;
      font-weight: bold;
      padding: 0.6rem 1rem;
      cursor: pointer;
      border-radius: 50%;
      transition: background 0.3s;
    }

    .close-btn:hover { background: #ff4d5a; }

    /* CONTACT */
    form {
      margin-top: 2rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
      align-items: center;
    }

    input, textarea {
      padding: 0.8rem;
      width: 100%;
      max-width: 500px;
      border: none;
      border-radius: 6px;
      font-family: inherit;
    }

    button {
      background: #e63946;
      color: #fff;
      border: none;
      padding: 0.8rem 1.5rem;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s;
    }

    button:hover { background: #ff4d5a; }

    /* FOOTER */
    footer {
      text-align: center;
      padding: 2rem;
      color: #888;
      background: #000;
      margin-top: 3rem;
    }
  </style>
</head>
<body>
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

  <section id="hero">
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <h1>We Tell Stories in Code</h1>
      <p>Design · Development · Creativity</p>
    </div>
  </section>

  <section id="about">
    <h2>About</h2>
    <p>8Rivers is a creative digital studio exploring the intersection of design, technology, and storytelling. Our mission is to craft meaningful experiences through elegant code and thoughtful visuals.</p>
  </section>

  <section id="works">
    <h2>Works</h2>
    <div class="works-grid">
      <!-- Repeat 15 projects -->
      <div class="work-item" data-video="video1" data-note="8Rivers notes: Project 1"><img src="d86.jpg" alt="Project 1"><h3>Project 1</h3></div>
      <div class="work-item" data-video="video2" data-note="8Rivers notes: Project 2"><img src="d86.jpg" alt="Project 2"><h3>Project 2</h3></div>
      <div class="work-item" data-video="video3" data-note="8Rivers notes: Project 3"><img src="d86.jpg" alt="Project 3"><h3>Project 3</h3></div>
      <div class="work-item" data-video="video4" data-note="8Rivers notes: Project 4"><img src="d86.jpg" alt="Project 4"><h3>Project 4</h3></div>
      <div class="work-item" data-video="video5" data-note="8Rivers notes: Project 5"><img src="d86.jpg" alt="Project 5"><h3>Project 5</h3></div>
      <div class="work-item" data-video="video6" data-note="8Rivers notes: Project 6"><img src="d86.jpg" alt="Project 6"><h3>Project 6</h3></div>
      <div class="work-item" data-video="video7" data-note="8Rivers notes: Project 7"><img src="d86.jpg" alt="Project 7"><h3>Project 7</h3></div>
      <div class="work-item" data-video="video8" data-note="8Rivers notes: Project 8"><img src="d86.jpg" alt="Project 8"><h3>Project 8</h3></div>
      <div class="work-item" data-video="video9" data-note="8Rivers notes: Project 9"><img src="d86.jpg" alt="Project 9"><h3>Project 9</h3></div>
      <div class="work-item" data-video="video10" data-note="8Rivers notes: Project 10"><img src="d86.jpg" alt="Project 10"><h3>Project 10</h3></div>
      <div class="work-item" data-video="video11" data-note="8Rivers notes: Project 11"><img src="d86.jpg" alt="Project 11"><h3>Project 11</h3></div>
      <div class="work-item" data-video="video12" data-note="8Rivers notes: Project 12"><img src="d86.jpg" alt="Project 12"><h3>Project 12</h3></div>
      <div class="work-item" data-video="video13" data-note="8Rivers notes: Project 13"><img src="d86.jpg" alt="Project 13"><h3>Project 13</h3></div>
      <div class="work-item" data-video="video14" data-note="8Rivers notes: Project 14"><img src="d86.jpg" alt="Project 14"><h3>Project 14</h3></div>
      <div class="work-item" data-video="video15" data-note="8Rivers notes: Project 15"><img src="d86.jpg" alt="Project 15"><h3>Project 15</h3></div>
    </div>
  </section>

  <div class="modal" id="modal">
    <div class="modal-content">
      <button class="close-btn" id="close-btn">×</button>
      <div class="modal-video-container"><iframe id="modal-video" src="" allowfullscreen></iframe></div>
      <div class="modal-note-container" id="modal-note"></div>
    </div>
  </div>

  <section id="contact">
    <h2>Contact</h2>
    <form>
      <input type="text" placeholder="Your Name" required />
      <input type="email" placeholder="Your Email" required />
      <textarea rows="5" placeholder="Your Message"></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <footer>
    <p>© 2025, 8Rivers. All rights reserved.</p>
  </footer>

  <script>
    const modal = document.getElementById('modal');
    const modalVideo = document.getElementById('modal-video');
    const modalNote = document.getElementById('modal-note');
    const closeBtn = document.getElementById('close-btn');

    document.querySelectorAll('.work-item').forEach(item => {
      item.addEventListener('click', () => {
        const videoId = item.dataset.video;
        const note = item.dataset.note;
        modalVideo.src = `https://www.youtube.com/embed/${videoId}?autoplay=1`;
        modalNote.textContent = note;
        modal.classList.add('show');
      });
    });

    function closeModal() {
      modal.classList.remove('show');
      setTimeout(() => { modalVideo.src = ''; }, 300);
    }

    closeBtn.addEventListener('click', closeModal);
    window.addEventListener('click', e => { if (e.target === modal) closeModal(); });
  </script>
</body>
</html>
