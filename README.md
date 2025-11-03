
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HMKN FAMS - Nostalgia Keluarga</title>
  <style>
    /* ================================
       HMKN FAMS — Nostalgia Family Edition
       by ChatGPT x Nathanael Sianipar
       ================================ */

    :root {
      --gold-light: #ffd27f;
      --gold-dark: #b36b00;
      --orange-soft: #ffb347;
      --orange-strong: #ff8c00;
      --white-warm: #fff8ee;
      --text-dark: #3e2f1c;
      --text-light: #f8f5f0;
      --transition: all 0.6s ease;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
      font-family: "Poppins", sans-serif;
    }

    body {
      background: var(--white-warm);
      color: var(--text-dark);
      overflow-x: hidden;
      transition: var(--transition);
    }

    /* ========== MODE SIANG ========== */
    body.day {
      background: linear-gradient(180deg, #fff8ee 0%, #ffe2b6 100%);
      color: var(--text-dark);
    }

    /* ========== MODE MALAM ========== */
    body.night {
      background: radial-gradient(circle at top, #3a2500 0%, #000000 100%);
      color: var(--text-light);
    }

    header {
      position: relative;
      height: 100vh;
      background: linear-gradient(120deg, rgba(255,165,0,0.4), rgba(255,255,255,0.1)), 
                url('image/Lovepik_com-500829952-family-silhouette-under-the-setting-sun.jpg');
      background-size: cover;
      background-position: center;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      text-align: center;
      color: #fff;
      overflow: hidden;
    }

    header::after {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle, rgba(255,255,255,0.15) 0%, transparent 70%);
      animation: shimmerMove 8s infinite linear;
      pointer-events: none;
    }

    @keyframes shimmerMove {
      0% {opacity: 0.3; transform: translateY(-20%) scale(1);}
      50% {opacity: 0.7; transform: translateY(10%) scale(1.05);}
      100% {opacity: 0.3; transform: translateY(-20%) scale(1);}
    }

    h1 {
      font-size: 4rem;
      text-shadow: 0 0 15px rgba(255,255,255,0.7);
      animation: fadeUp 1.5s ease forwards;
      opacity: 0;
    }

    h2 {
      font-size: 1.5rem;
      margin-top: 1rem;
      opacity: 0;
      animation: fadeUp 2s ease forwards 0.5s;
      text-shadow: 0 0 10px rgba(255,255,255,0.6);
    }

    @keyframes fadeUp {
      from {transform: translateY(50px); opacity: 0;}
      to {transform: translateY(0); opacity: 1;}
    }

    /* ========== PARTICLES ========== */
    canvas#particles {
      position: absolute;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
      pointer-events: none;
    }

    .content {
      position: relative;
      z-index: 2;
    }

    /* ========== SCROLL INDICATOR ========== */
.hero {
  position: relative;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.scroll-down {
  position: absolute;
  bottom: 40px; /* jarak dari bawah layar */
  left: 50%;
  transform: translateX(-50%);
  font-size: 1rem;
  color: #fff;
  opacity: 0.8;
  text-shadow: 0 2px 6px rgba(0,0,0,0.3);
  animation: pulse 2s infinite ease-in-out;
  letter-spacing: 1px;
}

@keyframes pulse {
  0%, 100% {
    opacity: 0.6;
    transform: translateX(-50%) translateY(0);
  }
  50% {
    opacity: 1;
    transform: translateX(-50%) translateY(-6px);
  }
}


    /* ====== NAVIGATION ====== */
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      background: rgba(255,255,255,0.2);
      backdrop-filter: blur(8px);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      z-index: 1000;
      transition: var(--transition);
    }

    nav.scrolled {
      background: rgba(255,140,0,0.9);
    }

    nav a {
      color: white;
      margin: 0 10px;
      text-decoration: none;
      font-weight: 500;
      transition: 0.3s;
    }

    nav a:hover {
      color: var(--gold-light);
    }

    .logo {
      font-size: 1.5rem;
      font-weight: bold;
      color: var(--gold-light);
      letter-spacing: 2px;
    }

    /* ===========================
       BAGIAN ALBUM KELUARGA
       =========================== */
    section#album {
      padding: 100px 20px;
      text-align: center;
      background: var(--white-warm);
      transition: var(--transition);
    }

    body.night section#album {
      background: #1b1b1b;
    }

    #album h3 {
      font-size: 2.5rem;
      margin-bottom: 40px;
      color: var(--orange-strong);
    }

    #anggota h3 {
      font-size: 2.5rem;
      margin-bottom: 40px;
      color: var(--orange-strong);
    }

    .family-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
    }

    .family-member {
      background: rgba(255,255,255,0.6);
      border-radius: 20px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.1);
      overflow: hidden;
      width: 250px;
      transition: 0.4s;
      transform: scale(1);
    }

    .family-member:hover {
      transform: scale(1.05);
      box-shadow: 0 15px 25px rgba(0,0,0,0.2);
    }

    .family-member img {
      width: 100%;
      height: 300px;
      object-fit: cover;
    }

    .member-info {
      padding: 15px;
      background: rgba(255,255,255,0.8);
    }

    .member-info h4 {
      font-size: 1.3rem;
      color: var(--orange-strong);
    }

    .member-info p {
      font-size: 0.9rem;
      color: #5a4734;
    }
  </style>
</head>
<body>
  <canvas id="particles"></canvas>
  <nav>
    <div class="logo">HMKN FAMS</div>
    <div>
      <a href="#anggota">Anggota</a>
      <a href="#slideshow">Kenangan</a>
      <a href="#album">Album</a>
      <a href="#music">Musik</a>
    </div>
  </nav>

  <header>
    <div class="hero">
      <h1>HMKN FAMS</h1>
      <h2>Harta yang paling berharga adalah keluarga</h2>
      <div class="scroll-down">↓ Scroll untuk melihat kenangan ↓</div>
    </div>
  </header>

<!-- END PART 1 -->
  <!-- =========================
       PART 2 — ALBUM KELUARGA
       ========================= -->
  <section id="anggota" class="fade-up">
    <h3><center>Anggota Keluarga</center></h3>
    <div class="family-container">
      <div class="family-member">
        <img src="image/bapak.jpg" alt="Bapak">
        <div class="member-info">
          <h4>Ayah</h4>
          <p>Penyemangat keluarga, tempat bersandar dan panutan sejati.</p>
        </div>
      </div>

      <div class="family-member">
        <img src="image/mama.jpg" alt="Mama">
        <div class="member-info">
          <h4>Mama</h4>
          <p>Pelukannya adalah rumah, senyumnya penenang hati.</p>
        </div>
      </div>

      <div class="family-member">
        <img src="image/kakak.jpg" alt="Kakak">
        <div class="member-info">
          <h4>Kakak</h4>
          <p>Pembawa canda, teman cerita, dan partner gila dalam petualangan.</p>
        </div>
      </div>

      <div class="family-member">
        <img src="image/Foto ku.jpg" alt="Sitampan">
        <div class="member-info">
          <h4>Aku</h4>
          <p>Pewaris tawa dan kenangan yang akan terus dijaga.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- =========================
       SLIDESHOW KENANGAN
       ========================= -->
  <section id="slideshow" class="fade-up">
    <h3>Kenangan Bersama</h3>
    <div class="slideshow-container">
      <div class="slides">
        <img src="image/WhatsApp Image 2025-10-21 at 16.44.17_022b223c.jpg" alt="Kenangan 1">
        <img src="image/WhatsApp Image 2025-10-27 at 14.35.26_91c60de1.jpg" alt="Kenangan 2">
        <img src="image/WhatsApp Image 2025-10-27 at 14.50.42_1a490fb1.jpg" alt="Kenangan 3">
        <img src="image/WhatsApp Image 2025-10-27 at 14.45.45_8218803c.jpg" alt="Kenangan 4">
      </div>
    </div>
  </section>

  <section id="album" class="fade-up">
    <h3>Album Keluarga</h3>
    <div class="family-container">
      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-21 at 16.44.17_022b223c.jpg" alt="Bapak">
        <div class="member-info">
          <h4>Inagurasi</h4>
        </div>
      </div>

      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-21 at 16.49.23_7f4f3762.jpg" alt="Mama">
        <div class="member-info">
          <h4>Bersama Tulang</h4>
        </div>
      </div>

      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-27 at 07.58.20_9224a7a0.jpg" alt="Kakak">
        <div class="member-info">
          <h4>Waktu kecil</h4>
        </div>
      </div>

      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-27 at 14.34.59_4d348735.jpg" alt="Aku">
        <div class="member-info">
          <h4>H-1 di IT Del</h4>
        </div>
      </div>
    </div>

    <div class="family-container">
      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-27 at 14.34.59_cddb0710.jpg" alt="Bapak">
        <div class="member-info">
          <h4>sebelum PCA</h4>
        </div>
      </div>

      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-27 at 14.50.42_503a2b7d.jpg" alt="Mama">
        <div class="member-info">
          <h4>di patung sibea bea</h4>
        </div>
      </div>

      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-27 at 14.35.26_fbe1431a.jpg" alt="Kakak">
        <div class="member-info">
          <h4>with mama</h4>
        </div>
      </div>

      <div class="family-member">
        <img src="image/WhatsApp Image 2025-10-27 at 14.35.27_83d27f88.jpg" alt="Aku">
        <div class="member-info">
          <h4>with kakak</h4>
        </div>
      </div>
    </div>
  </section>

  <style>
    #slideshow {
      background: linear-gradient(to bottom, #fff8ee, #ffe2b6);
      padding: 100px 20px;
      text-align: center;
      overflow: hidden;
    }

    #slideshow h3 {
      font-size: 2.5rem;
      color: var(--orange-strong);
      margin-bottom: 40px;
    }

    .slideshow-container {
      width: 900%;
      max-width: 900px;
      margin: 0 auto;
      overflow: hidden;
      border-radius: 100px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
    }

    .slides {
      display: flex;
      width: 400%;
      transition: transform 1s ease-in-out;
    }

    .slides img {
      width: 25%;
      height: 650px;
      object-fit: cover;
      border-radius: 25px;
    }

    /* Fade-up transition */
    .fade-up {
      opacity: 0;
      transform: translateY(40px);
      transition: opacity 1s ease, transform 1s ease;
    }
    .fade-up.visible {
      opacity: 1;
      transform: translateY(0);
    }
  </style>

  <!-- =========================
       VIDEO & MUSIK FAVORIT
       ========================= -->
  <section id="music" class="fade-up">
    <h3>Musik & Video Favorit Keluarga</h3>
    <div class="music-section">
      <div class="video-container">
        <iframe width="560" height="315" 
          src="https://www.youtube.com/embed/1ZYbU82GVz4?autoplay=0&mute=0" 
          title="Orkestra Nostalgia"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen></iframe>

        <iframe width="560" height="315" 
          src="https://www.youtube.com/embed/SVsEdZseq3o?si=n-fEP0StzgfAjhSN=0&mute=0" 
          title="Lagu Populer Bertema Keluarga"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen></iframe>
      </div>

      <div class="audio-container">
        <audio id="audioPlayer" controls autoplay loop>
          <source src="music1.mp3" type="audio/mp3">
          <source src="music2.mp3" type="audio/mp3">
          Browser kamu tidak mendukung audio.
        </audio>

        <p class="song-title">🎵 Sedang memutar: <span id="currentSong">Orkestra Keluarga</span></p>
      </div>
    </div>
  </section>

  <style>
    #music {
      padding: 100px 20px;
      text-align: center;
      background: linear-gradient(to top, #fff8ee, #ffe2b6);
    }

    #music h3 {
      color: var(--orange-strong);
      font-size: 2.5rem;
      margin-bottom: 40px;
    }

    .music-section {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 40px;
      align-items: center;
    }

    .video-container {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    iframe {
      border-radius: 20px;
      box-shadow: 0 5px 25px rgba(0,0,0,0.3);
      transition: 0.3s;
    }

    iframe:hover {
      transform: scale(1.02);
    }

    .audio-container {
      background: rgba(255,255,255,0.8);
      padding: 30px;
      border-radius: 25px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.1);
      max-width: 400px;
    }

    audio {
      width: 100%;
      outline: none;
      border-radius: 10px;
    }

    .song-title {
      margin-top: 10px;
      color: var(--text-dark);
      font-weight: bold;
    }
  </style>

<!-- END PART 2 -->
  <!-- =========================
       PART 3 — JAVASCRIPT INTERAKTIF
       ========================= -->
  <script>
    /* ======== SCROLL EFFECT NAV ======== */
    window.addEventListener('scroll', () => {
      const nav = document.querySelector('nav');
      if(window.scrollY > 100){
        nav.classList.add('scrolled');
      } else {
        nav.classList.remove('scrolled');
      }
    });

    /* ======== FADE-UP EFFECT ======== */
    const fadeElements = document.querySelectorAll('.fade-up');
    const fadeObserver = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if(entry.isIntersecting){
          entry.target.classList.add('visible');
        }
      });
    }, {threshold: 0.3});

    fadeElements.forEach(el => fadeObserver.observe(el));

    /* ======== PARTICLE BACKGROUND ======== */
    const canvas = document.getElementById('particles');
    const ctx = canvas.getContext('2d');
    let particlesArray = [];

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();

    class Particle {
      constructor(){
        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;
        this.size = Math.random() * 2 + 0.5;
        this.speedX = (Math.random() - 0.5) * 0.5;
        this.speedY = Math.random() * 0.7 + 0.3;
        this.color = `rgba(255,255,255,${Math.random()*0.7})`;
      }
      update(){
        this.x += this.speedX;
        this.y += this.speedY;
        if(this.y > canvas.height){
          this.y = 0;
          this.x = Math.random() * canvas.width;
        }
      }
      draw(){
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size, 0, Math.PI*2);
        ctx.fillStyle = this.color;
        ctx.fill();
      }
    }

    function initParticles(){
      particlesArray = [];
      for(let i=0; i < (canvas.width * canvas.height) / 12000; i++){
        particlesArray.push(new Particle());
      }
    }

    function animateParticles(){
      ctx.clearRect(0,0,canvas.width,canvas.height);
      particlesArray.forEach(p => {
        p.update();
        p.draw();
      });
      requestAnimationFrame(animateParticles);
    }

    initParticles();
    animateParticles();

    /* ======== SLIDESHOW OTOMATIS ======== */
    const slides = document.querySelector('.slides');
    let index = 0;
    function autoSlide(){
      index++;
      if(index >= slides.children.length) index = 0;
      slides.style.transform = `translateX(-${index * 25}%)`;
    }
    setInterval(autoSlide, 4000);

    /* ======== AUTO-THEME SIANG MALAM ======== */
    function autoTheme(){
      const hour = new Date().getHours();
      if(hour >= 18 || hour < 6){
        document.body.classList.add('night');
        document.body.classList.remove('day');
      } else {
        document.body.classList.add('day');
        document.body.classList.remove('night');
      }
    }
    autoTheme();
    setInterval(autoTheme, 60000);

    /* ======== QUOTES HARIAN ======== */
    const quotes = [
      "Keluarga adalah tempat di mana cinta tidak pernah berakhir.",
      "Harta yang paling berharga adalah keluarga.",
      "Cinta sejati berawal dari rumah.",
      "Senyum keluarga menghangatkan dunia.",
      "Keluarga bukan hanya darah, tapi hati yang saling terhubung.",
      "Tak perlu sempurna untuk bahagia, cukup ada keluarga.",
      "Di setiap tawa, ada kenangan yang tak tergantikan.",
      "Rumah adalah di mana cinta keluarga berada."
    ];
    const quoteBox = document.createElement('div');
    quoteBox.className = 'quote-box fade-up';
    document.body.appendChild(quoteBox);

    const styleQuote = document.createElement('style');
    styleQuote.textContent = `
      .quote-box {
        position: relative;
        padding: 80px 20px;
        text-align: center;
        font-size: 1.4rem;
        color: var(--text-dark);
        background: linear-gradient(to top, #fff8ee, #ffdca3);
        font-style: italic;
        opacity: 0;
        transform: translateY(50px);
        transition: opacity 1s ease, transform 1s ease;
      }
      .quote-box.visible {
        opacity: 1;
        transform: translateY(0);
      }
      body.night .quote-box {
        background: linear-gradient(to top, #2b1800, #000);
        color: var(--gold-light);
      }
    `;
    document.head.appendChild(styleQuote);

    let currentQuote = 0;
    function updateQuote(){
      quoteBox.textContent = `"${quotes[currentQuote]}"`;
      currentQuote = (currentQuote + 1) % quotes.length;
      quoteBox.classList.add('visible');
      setTimeout(()=>quoteBox.classList.remove('visible'), 4000);
    }
    updateQuote();
    setInterval(updateQuote, 6000);

    /* ======== PLAYLIST MUSIK OTOMATIS ======== */
    const audioPlayer = document.getElementById('audioPlayer');
    const currentSongText = document.getElementById('currentSong');

    const musicList = [
      { title: "Orkestra Keluarga", file: "music1.mp3" },
      { title: "Kenangan Manis", file: "music2.mp3" },
      { title: "Lagu Rumah", file: "music3.mp3" }
    ];

    let currentTrack = 0;
    audioPlayer.src = musicList[currentTrack].file;
    currentSongText.textContent = musicList[currentTrack].title;
    audioPlayer.play().catch(()=>{});

    audioPlayer.addEventListener('ended', () => {
      currentTrack = (currentTrack + 1) % musicList.length;
      audioPlayer.src = musicList[currentTrack].file;
      currentSongText.textContent = musicList[currentTrack].title;
      audioPlayer.play();
    });

    /* ======== AUTOPLAY FIX ======== */
    document.addEventListener('click', () => {
      if(audioPlayer.paused){
        audioPlayer.play();
      }
    }, { once: true });

  </script>

  <footer style="text-align:center; padding:50px; background:#fff8ee; color:#5a4734; font-size:0.9rem;">
    <p>© 2025 HMKN FAMS — Kenangan yang tak tergantikan 💛</p>
  </footer>

</body>
</html>
