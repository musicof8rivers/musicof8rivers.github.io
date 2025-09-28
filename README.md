<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>8Rivers</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Open+Sans&display=swap" rel="stylesheet">
  <style>
/* Reset & base styles */
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: 'Open Sans', sans-serif; background: #000; color: #fff; }
a { color: inherit; text-decoration: none; }

/* Header & Navbar */
header { position: fixed; width: 100%; top: 0; left: 0; z-index: 100; }
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.8rem 2rem; /* slightly smaller padding */
  transition: background-color 0.3s ease;
  background-color: #000; /* black navbar */
}
.nav-links { display: flex; list-style: none; gap: 2rem; }
.nav-links li a {
  font-size: 1.3rem;  /* slightly smaller text */
  font-weight: bold;
  padding: 0.4rem 0.2rem;
  position: relative;
  transition: color 0.3s, text-decoration 0.3s;
  color: #fff; /* white links */
}
.nav-links li a:hover {
  color: #ddd; /* lighter on hover */
  text-decoration: underline;
}
header.scrolled .navbar { background-color: rgba(0,0,0,0.8); }

/* Hero section */
#hero { height: 100vh; background: url('hero.jpg') center center / cover no-repeat; position: relative; }
.hero-overlay { position: absolute; top: 0; left: 0; height: 100%; width: 100%; background: rgba(0,0,0,0.5); }
.hero-content {
  position: relative; z-index: 1; height: 100%;
  display: flex; flex-direction: column; justify-content: center; align-items: center;
  text-align: center; padding: 0 2rem;
}
.hero-content h1 { font-family: 'Playfair Display', serif; font-size: 3rem; margin-bottom: 1rem; }
.hero-content p { font-size: 1.5rem; }

/* Section spacing */
section { padding: 6rem 2rem 5rem; max-width: 1100px; margin: auto; } /* padding-top adjusted for navbar */
#about { padding-top: 6rem; }
#works { padding-top: 6rem; }
#contact { padding-top: 6rem; }
h2 { font-family: 'Playfair Display', serif; font-size: 2rem; margin-bottom: 1rem; }
p { line-height: 1.6; }

/* Works grid */
.works-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }
.work-item {
  background: #111; border-radius: 12px; overflow: hidden;
  transition: transform 0.3s; cursor: pointer; position: relative;
}
.work-item:hover { transform: translateY(-5px); }
.work-item img {
  width: 100%; height: auto; display: block;
  filter: grayscale(100%); transition: filter 0.5s ease;
}
.work-item:hover img { filter: grayscale(0%); }
.work-item h3 { padding: 1rem; font-size: 1.2rem; text-align: center; }

/* Modal styles */
.modal {
  display: none;
  position: fixed; top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.9);
  justify-content: center; align-items: center;
  z-index: 200; padding: 2rem; overflow-y: auto;
  opacity: 0; transform: scale(0.95);
  transition: opacity 0.3s ease, transform 0.3s ease;
}
.modal.show { display: flex; opacity: 1; transform: scale(1); }
.modal-content {
  background: #111; padding: 1rem; border-radius: 10px;
  max-width: 800px; width: 100%; position: relative;
  display: flex; flex-direction: column; gap: 1rem;
}
.modal-video-container { background: #222; padding: 1rem; border-radius: 6px; }
.modal-note-container { background: #333; padding: 1rem; border-radius: 6px; color: #fff; font-size: 1rem; line-height: 1.4; }
.modal iframe { width: 100%; height: 450px; border: none; border-radius: 6px; }

/* Close button */
.close-btn {
  position: absolute; top: 10px; right: 10px;
  background: #444; color: #fff; border: none;
  font-size: 2rem; padding: 0.8rem 1.4rem; cursor: pointer;
  border-radius: 6px;
}
.close-btn:hover { background: #666; }

/* Form styles */
form { display: flex; flex-direction: column; gap: 1rem; }
input, textarea { padding: 0.8rem; border: none; border-radius: 6px; font-family: inherit; }
button { background: #444; color: #fff; border: none; padding: 0.8rem; border-radius: 6px; cursor: pointer; transition: background 0.3s; }
button:hover { background: #666; }

/* Footer */
footer { text-align: center; padding: 2rem; color: #aaa; background: #000; }

/* Smooth scroll for anchor links */
html { scroll-behavior: smooth; }
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
      <!-- 15 projects -->
      <div class="work-item" data-video="video1" data-note="8Rivers notes: Project 1"><img src="d86.jpg" alt="Project 1" /><h3>Project 1</h3></div>
      <div class="work-item" data-video="video2" data-note="8Rivers notes: Project 2"><img src="d86.jpg" alt="Project 2" /><h3>Project 2</h3></div>
      <div class="work-item" data-video="video3" data-note="8Rivers notes: Project 3"><img src="d86.jpg" alt="Project 3" /><h3>Project 3</h3></div>
      <div class="work-item" data-video="video4" data-note="8Rivers notes: Project 4"><img src="d86.jpg" alt="Project 4" /><h3>Project 4</h3></div>
      <div class="work-item" data-video="video5" data-note="8Rivers notes: Project 5"><img src="d86.jpg" alt="Project 5" /><h3>Project 5</h3></div>
      <div class="work-item" data-video="video6" data-note="8Rivers notes: Project 6"><img src="d86.jpg" alt="Project 6" /><h3>Project 6</h3></div>
      <div class="work-item" data-video="video7" data-note="8Rivers notes: Project 7"><img src="d86.jpg" alt="Project 7" /><h3>Project 7</h3></div>
      <div class="work-item" data-video="video8" data-note="8Rivers notes: Project 8"><img src="d86.jpg" alt="Project 8" /><h3>Project 8</h3></div>
      <div class="work-item" data-video="video9" data-note="8Rivers notes: Project 9"><img src="d86.jpg" alt="Project 9" /><h3>Project 9</h3></div>
      <div class="work-item" data-video="video10" data-note="8Rivers notes: Project 10"><img src="d86.jpg" alt="Project 10" /><h3>Project 10</h3></div>
      <div class="work-item" data-video="video11" data-note="8Rivers notes: Project 11"><img src="d86.jpg" alt="Project 11" /><h3>Project 11</h3></div>
      <div class="work-item" data-video="video12" data-note="8Rivers notes: Project 12"><img src="d86.jpg" alt="Project 12" /><h3>Project 12</h3></div>
      <div class="work-item" data-video="video13" data-note="8Rivers notes: Project 13"><img src="d86.jpg" alt="Project 13" /><h3>Project 13</h3></div>
      <div class="work-item" data-video="video14" data-note="8Rivers notes: Project 14"><img src="d86.jpg" alt="Project 14" /><h3>Project 14</h3></div>
      <div class="work-item" data-video="video15" data-note="8Rivers notes: Project 15"><img src="d86.jpg" alt="Project 15" /><h3>Project 15</h3></div>
    </div>
  </section>

  <div class="modal" id="modal">
    <div class="modal-content">
      <button class="close-btn" id="close-btn">X</button>
      <div class="modal-video-container">
        <iframe id="modal-video" src="" allowfullscreen></iframe>
      </div>
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
    window.addEventListener('click', e => { if(e.target === modal) closeModal(); });
  </script>
</body>
</html>
