<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>8Rivers</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { font-family: 'Open Sans', sans-serif; background: #000; color: #fff; }
    a { color: inherit; text-decoration: none; }

    /* Navbar */
    header { position: fixed; width: 100%; top: 0; left: 0; z-index: 100; background: #000; }
    .navbar { display: flex; justify-content: space-between; align-items: center; padding: 1rem 2rem; }
    .logo { font-size: 1.5rem; font-weight: bold; }
    .nav-links { display: flex; list-style: none; }
    .nav-links li { margin-left: 2rem; }
    .nav-links a { font-size: 1.2rem; }
    .nav-links a:hover { text-decoration: underline; }

    /* Hero */
    #hero { height: 100vh; background: url('hero.jpg') center center / cover no-repeat; position: relative; }
    .hero-overlay { position: absolute; top: 0; left: 0; height: 100%; width: 100%; background: rgba(0,0,0,0.5); }
    .hero-content { position: relative; z-index: 1; height: 100%; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 0 2rem; }
    .hero-content h1 { font-family: 'Playfair Display', serif; font-size: 3rem; margin-bottom: 1rem; }
    .hero-content p { font-size: 1.5rem; }

    /* Sections */
    section { padding: 6rem 2rem; max-width: 1100px; margin: auto; }
    h2 { font-family: 'Playfair Display', serif; font-size: 2rem; margin-bottom: 1rem; }
    p { line-height: 1.6; }

    /* Works grid */
    .works-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
    .work-item { background: #111; border-radius: 12px; overflow: hidden; transition: transform 0.3s; cursor: pointer; position: relative; }
    .work-item:hover { transform: translateY(-5px); }
    .work-item img { width: 100%; height: auto; display: block; filter: grayscale(100%); transition: filter 0.5s ease; }
    .work-item:hover img { filter: grayscale(0%); }
    .work-item h3 { padding: 1rem; font-size: 1.2rem; text-align: center; }

    /* Modal */
    .modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); justify-content: center; align-items: center; z-index: 200; padding: 2rem; overflow-y: auto; }
    .modal-content { background: #111; padding: 1rem; border-radius: 10px; max-width: 900px; width: 100%; position: relative; display: flex; flex-direction: column; gap: 1rem; animation: fadeIn 0.4s ease; }
    .modal-video-container { background: #222; padding: 1rem; border-radius: 6px; }
    .modal-note-container { background: #333; padding: 1rem; border-radius: 6px; color: #fff; font-size: 1rem; line-height: 1.4; }
    .modal iframe { width: 100%; height: 500px; border: none; border-radius: 6px; }
    .close-btn { position: absolute; top: 10px; right: 10px; background: #444; color: #fff; border: none; font-size: 1.5rem; padding: 0.7rem 1.2rem; cursor: pointer; border-radius: 6px; }
    .close-btn:hover { background: #666; }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* Forms */
    form { display: flex; flex-direction: column; gap: 1rem; }
    input, textarea { padding: 0.8rem; border: none; border-radius: 6px; font-family: inherit; }
    button { background: #444; color: #fff; border: none; padding: 0.8rem; border-radius: 6px; cursor: pointer; transition: background 0.3s; }
    button:hover { background: #666; }

    footer { text-align: center; padding: 2rem; color: #aaa; background: #000; }

    /* Anchor offset fix */
    :root { --nav-offset: 6rem; }
    section { scroll-margin-top: var(--nav-offset); }
    section::before {
      content: "";
      display: block;
      height: var(--nav-offset);
      margin-top: calc(-1 * var(--nav-offset));
      visibility: hidden;
      pointer-events: none;
    }
  </style>
</head>
<body>
  <!-- Header -->
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
      <h1>Welcome to 8Rivers</h1>
      <p>Exploring works and ideas</p>
    </div>
  </section>

  <!-- About -->
  <section id="about">
    <h2>About</h2>
    <p>8Rivers notes and works collection.</p>
  </section>

  <!-- Works -->
  <section id="works">
    <h2>Works</h2>
    <div class="works-grid">
      <!-- Repeat 15 items -->
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 1">
        <img src="d86.jpg" alt="Work 1">
        <h3>Work 1</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 2">
        <img src="d86.jpg" alt="Work 2">
        <h3>Work 2</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 3">
        <img src="d86.jpg" alt="Work 3">
        <h3>Work 3</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 4">
        <img src="d86.jpg" alt="Work 4">
        <h3>Work 4</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 5">
        <img src="d86.jpg" alt="Work 5">
        <h3>Work 5</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 6">
        <img src="d86.jpg" alt="Work 6">
        <h3>Work 6</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 7">
        <img src="d86.jpg" alt="Work 7">
        <h3>Work 7</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 8">
        <img src="d86.jpg" alt="Work 8">
        <h3>Work 8</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 9">
        <img src="d86.jpg" alt="Work 9">
        <h3>Work 9</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 10">
        <img src="d86.jpg" alt="Work 10">
        <h3>Work 10</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 11">
        <img src="d86.jpg" alt="Work 11">
        <h3>Work 11</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 12">
        <img src="d86.jpg" alt="Work 12">
        <h3>Work 12</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 13">
        <img src="d86.jpg" alt="Work 13">
        <h3>Work 13</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 14">
        <img src="d86.jpg" alt="Work 14">
        <h3>Work 14</h3>
      </div>
      <div class="work-item" data-video="https://www.youtube.com/embed/dQw4w9WgXcQ" data-note="8Rivers notes: Project 15">
        <img src="d86.jpg" alt="Work 15">
        <h3>Work 15</h3>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>Contact</h2>
    <form>
      <input type="text" placeholder="Your name">
      <input type="email" placeholder="Your email">
      <textarea rows="5" placeholder="Your message"></textarea>
      <button type="submit">Send</button>
    </form>
  </section>

  <footer>
    <p>&copy; 2025 8Rivers. All rights reserved.</p>
  </footer>

  <!-- Modal -->
  <div class="modal" id="modal">
    <div class="modal-content">
      <button class="close-btn" id="closeModal">&times;</button>
      <div class="modal-video-container">
        <iframe id="modalVideo" src="" allowfullscreen></iframe>
      </div>
      <div class="modal-note-container" id="modalNote"></div>
    </div>
  </div>

  <script>
    // Dynamic nav offset
    (function() {
      const nav = document.getElementById('main-header');
      function setNavOffset() {
        const h = (nav && nav.offsetHeight) ? nav.offsetHeight : 48;
        document.documentElement.style.setProperty('--nav-offset', h + 'px');
      }
      setNavOffset();
      window.addEventListener('resize', setNavOffset);
      window.addEventListener('load', setNavOffset);
    })();

    // Modal logic
    const modal = document.getElementById("modal");
    const modalVideo = document.getElementById("modalVideo");
    const modalNote = document.getElementById("modalNote");
    const closeModal = document.getElementById("closeModal");

    document.querySelectorAll(".work-item").forEach(item => {
      item.addEventListener("click", () => {
        const video = item.getAttribute("data-video");
        const note = item.getAttribute("data-note");
        modal.style.display = "flex";
        modalVideo.src = video;
        modalNote.textContent = note;
      });
    });

    closeModal.addEventListener("click", () => {
      modal.style.display = "none";
      modalVideo.src = "";
    });

    window.addEventListener("click", e => {
      if (e.target === modal) {
        modal.style.display = "none";
        modalVideo.src = "";
      }
    });
  </script>
</body>
</html>
