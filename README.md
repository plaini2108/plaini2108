<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Palini Mulgund | Cinematic Portfolio</title>
  <!-- Google Fonts + Font Awesome -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #05070a;
      color: #edf2fb;
      scroll-behavior: smooth;
      overflow-x: hidden;
    }

    /* animated gradient background */
    .animated-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: radial-gradient(circle at 20% 30%, rgba(45, 156, 124, 0.12), transparent 55%),
                  radial-gradient(circle at 85% 70%, rgba(108, 99, 255, 0.08), transparent 70%),
                  repeating-linear-gradient(45deg, rgba(45,156,124,0.02) 0px, rgba(45,156,124,0.02) 2px, transparent 2px, transparent 8px);
      pointer-events: none;
      z-index: -2;
    }

    /* glassmorphism + neumorphism hybrid */
    .glass-card {
      background: rgba(15, 20, 26, 0.6);
      backdrop-filter: blur(14px);
      border-radius: 2rem;
      border: 1px solid rgba(45, 156, 124, 0.25);
      box-shadow: 0 20px 35px -12px rgba(0,0,0,0.5), inset 0 1px 0 rgba(255,255,255,0.03);
      transition: all 0.35s cubic-bezier(0.2, 0.9, 0.4, 1.1);
    }

    .glass-card:hover {
      transform: translateY(-6px);
      border-color: rgba(45, 156, 124, 0.6);
      box-shadow: 0 28px 40px -16px rgba(0,0,0,0.6);
    }

    .container {
      max-width: 1300px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    /* sticky navbar + animated underline */
    nav {
      position: sticky;
      top: 0;
      z-index: 100;
      background: rgba(5, 7, 10, 0.82);
      backdrop-filter: blur(18px);
      border-bottom: 1px solid rgba(45, 156, 124, 0.3);
    }
    .nav-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      max-width: 1300px;
      margin: 0 auto;
    }
    .logo {
      font-weight: 800;
      font-size: 1.8rem;
      background: linear-gradient(135deg, #e0f7f0, #2D9C7C);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.5px;
    }
    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }
    .nav-links a {
      text-decoration: none;
      color: #cddcff;
      font-weight: 500;
      transition: 0.2s;
      font-size: 0.95rem;
      position: relative;
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -6px;
      left: 0;
      width: 0%;
      height: 2px;
      background: #2D9C7C;
      transition: width 0.25s;
    }
    .nav-links a:hover::after, .nav-links a.active::after {
      width: 100%;
    }
    .nav-links a.active {
      color: #2D9C7C;
    }

    /* scroll progress */
    .scroll-progress {
      position: fixed;
      top: 0;
      left: 0;
      height: 3.5px;
      background: linear-gradient(90deg, #2D9C7C, #6C63FF, #2D9C7C);
      width: 0%;
      z-index: 102;
      transition: width 0.08s linear;
      box-shadow: 0 0 8px #2D9C7C;
    }

    section {
      padding: 6rem 0;
      border-bottom: 1px solid rgba(255,255,255,0.03);
    }
    h2 {
      font-size: 2.8rem;
      font-weight: 700;
      margin-bottom: 2.5rem;
      display: inline-block;
      background: linear-gradient(125deg, #ffffff, #a3f0db, #2D9C7C);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      letter-spacing: -0.5px;
    }

    /* Hero cinematic */
    .hero {
      min-height: 92vh;
      display: flex;
      align-items: center;
      position: relative;
    }
    .hero-content {
      max-width: 800px;
    }
    .greeting {
      font-size: 1.2rem;
      letter-spacing: 5px;
      text-transform: uppercase;
      color: #2D9C7C;
      font-weight: 500;
    }
    .dynamic-title {
      font-size: 4.5rem;
      font-weight: 800;
      line-height: 1.2;
      margin: 1.2rem 0;
    }
    .typed-cursor {
      display: inline-block;
      width: 3px;
      background: #2D9C7C;
      animation: blink 0.7s infinite;
    }
    @keyframes blink {
      0%,100% { opacity: 1; }
      50% { opacity: 0; }
    }
    .hero-desc {
      font-size: 1.2rem;
      margin: 1.5rem 0;
      color: #b9ceff;
      line-height: 1.5;
    }

    /* skills animated progress */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }
    .skill-item p {
      display: flex;
      justify-content: space-between;
      margin-bottom: 0.6rem;
      font-weight: 500;
    }
    .progress-bar-bg {
      background: #1e293b;
      border-radius: 40px;
      height: 8px;
      overflow: hidden;
    }
    .progress-fill {
      background: linear-gradient(95deg, #2D9C7C, #6C63FF);
      width: 0%;
      height: 100%;
      border-radius: 40px;
      transition: width 1.2s cubic-bezier(0.22, 0.97, 0.36, 1);
    }

    /* Timeline */
    .timeline {
      position: relative;
      padding-left: 2rem;
    }
    .timeline::before {
      content: '';
      position: absolute;
      left: 8px;
      top: 15px;
      bottom: 15px;
      width: 2px;
      background: linear-gradient(to bottom, #2D9C7C, #6C63FF, #2D9C7C);
    }
    .timeline-item {
      position: relative;
      margin-bottom: 2.8rem;
      padding-left: 2rem;
    }
    .timeline-dot {
      position: absolute;
      left: -2px;
      top: 6px;
      width: 18px;
      height: 18px;
      background: #2D9C7C;
      border-radius: 50%;
      border: 2px solid #05070a;
      box-shadow: 0 0 0 3px rgba(45,156,124,0.3);
      transition: 0.2s;
    }
    .timeline-content {
      background: rgba(22, 28, 36, 0.7);
      padding: 1.2rem 1.8rem;
      border-radius: 1.5rem;
      backdrop-filter: blur(5px);
    }

    /* project cards */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(310px, 1fr));
      gap: 2rem;
    }
    .project-card {
      background: rgba(18, 22, 30, 0.75);
      border-radius: 1.8rem;
      padding: 1.8rem;
      transition: all 0.3s;
      cursor: pointer;
      border: 1px solid rgba(45,156,124,0.2);
      backdrop-filter: blur(4px);
    }
    .project-card:hover {
      border-color: #2D9C7C;
      transform: translateY(-8px) scale(1.01);
      background: rgba(28, 34, 44, 0.85);
      box-shadow: 0 20px 35px -12px black;
    }
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.85);
      backdrop-filter: blur(14px);
      justify-content: center;
      align-items: center;
      z-index: 200;
    }
    .modal-content {
      max-width: 550px;
      background: #0f141c;
      padding: 2rem;
      border-radius: 2rem;
      border-top: 5px solid #2D9C7C;
      position: relative;
      animation: modalPop 0.35s ease;
    }
    @keyframes modalPop {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }
    .close-modal {
      position: absolute;
      top: 1rem;
      right: 1.5rem;
      font-size: 1.8rem;
      cursor: pointer;
      color: #aaa;
    }

    /* contact form */
    .contact-form input, .contact-form textarea {
      width: 100%;
      background: rgba(255,255,255,0.05);
      border: 1px solid rgba(45,156,124,0.4);
      padding: 1rem;
      border-radius: 1.2rem;
      color: #f0f3fa;
      margin-bottom: 1rem;
      transition: 0.2s;
      font-family: inherit;
    }
    .contact-form input:focus, .contact-form textarea:focus {
      outline: none;
      border-color: #2D9C7C;
      box-shadow: 0 0 8px rgba(45,156,124,0.3);
    }
    .btn-primary {
      background: linear-gradient(100deg, #2D9C7C, #1c6b56);
      border: none;
      padding: 0.9rem 2rem;
      border-radius: 2rem;
      font-weight: 600;
      color: white;
      cursor: pointer;
      transition: 0.2s;
    }
    .btn-primary:hover {
      transform: scale(1.02);
      box-shadow: 0 10px 22px -8px #2D9C7C;
    }
    .social-icons a {
      color: #cdd9ff;
      font-size: 1.6rem;
      margin-right: 1.2rem;
      transition: 0.2s;
      display: inline-block;
    }
    .social-icons a:hover {
      color: #2D9C7C;
      transform: translateY(-5px);
    }
    .back-to-top {
      position: fixed;
      bottom: 2rem;
      right: 2rem;
      background: #2D9C7C;
      width: 48px;
      height: 48px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      opacity: 0;
      transition: 0.3s;
      z-index: 99;
      box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    }
    footer {
      text-align: center;
      padding: 2rem 1rem;
      font-size: 0.85rem;
      opacity: 0.7;
    }
    @media (max-width: 780px) {
      .nav-links { gap: 1rem; flex-wrap: wrap; justify-content: center; }
      .dynamic-title { font-size: 2.4rem; }
      h2 { font-size: 2rem; }
      .hero { min-height: 70vh; }
      .container { padding: 0 1.2rem; }
    }
    .grid-2col {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.8rem;
    }
  </style>
</head>
<body>
<div class="scroll-progress" id="progressBar"></div>
<div class="animated-bg"></div>

<nav>
  <div class="nav-container">
    <div class="logo">PALINI<span style="color:#2D9C7C;">✦</span>M</div>
    <ul class="nav-links">
      <li><a href="#home" class="nav-link active">Home</a></li>
      <li><a href="#about" class="nav-link">About</a></li>
      <li><a href="#skills" class="nav-link">Skills</a></li>
      <li><a href="#experience" class="nav-link">Experience</a></li>
      <li><a href="#projects" class="nav-link">Projects</a></li>
      <li><a href="#education" class="nav-link">Education</a></li>
      <li><a href="#contact" class="nav-link">Contact</a></li>
    </ul>
  </div>
</nav>

<main class="container">
  <!-- Hero Section -->
  <section id="home" class="hero">
    <div class="hero-content">
      <div class="greeting">✦ CINEMATIC PORTFOLIO ✦</div>
      <div class="dynamic-title">
        <span id="typedOutput"></span><span class="typed-cursor">|</span>
      </div>
      <p class="hero-desc">Pre-final year CS • General Secretary • National Debate Finalist • Crafting intelligent systems with AI & cloud.</p>
      <button class="btn-primary" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Let's connect <i class="fas fa-arrow-right"></i></button>
    </div>
  </section>

  <!-- About Section -->
  <section id="about">
    <h2>About Me</h2>
    <div class="glass-card" style="padding: 2rem;">
      <p style="font-size: 1.1rem; line-height: 1.6;">I'm <strong class="highlight">Palini Mulgund</strong>, a passionate tech leader with CGPA 8.73, NPTEL certified in DBMS & Python. I blend engineering with oratory — finalist at <strong>Speak for India</strong> regional debate. As <strong>General Secretary</strong>, I lead campus-wide initiatives, fostering innovation and collaboration. My projects merge AI, full-stack development, and time-series data, aiming to solve real-world friction. Open to challenging roles where I can deliver impact with code and conviction.</p>
      <div style="margin-top: 1.5rem; display: flex; gap: 1.2rem; flex-wrap: wrap;">
        <span><i class="fas fa-map-marker-alt" style="color:#2D9C7C;"></i> Gadag, Karnataka</span>
        <span><i class="fas fa-phone-alt"></i> +91 7483096295</span>
        <span><i class="fas fa-envelope"></i> mulgundpalini@gmail.com</span>
      </div>
    </div>
  </section>

  <!-- Skills with progress bars -->
  <section id="skills">
    <h2>Technical Brilliance</h2>
    <div class="skills-grid">
      <div class="skill-item"><p>Python (Advanced) <span>88%</span></p><div class="progress-bar-bg"><div class="progress-fill" data-width="88"></div></div></div>
      <div class="skill-item"><p>Flask & Web Dev <span>82%</span></p><div class="progress-bar-bg"><div class="progress-fill" data-width="82"></div></div></div>
      <div class="skill-item"><p>MongoDB / SQL <span>78%</span></p><div class="progress-bar-bg"><div class="progress-fill" data-width="78"></div></div></div>
      <div class="skill-item"><p>OpenCV / MediaPipe <span>76%</span></p><div class="progress-bar-bg"><div class="progress-fill" data-width="76"></div></div></div>
      <div class="skill-item"><p>HTML/CSS/JS (Frontend) <span>80%</span></p><div class="progress-bar-bg"><div class="progress-fill" data-width="80"></div></div></div>
      <div class="skill-item"><p>Cloud & Cybersecurity <span>70%</span></p><div class="progress-bar-bg"><div class="progress-fill" data-width="70"></div></div></div>
    </div>
    <div style="margin-top: 2.5rem; display: flex; gap: 0.8rem; flex-wrap: wrap;">
      <span class="glass-card" style="padding: 0.5rem 1.2rem;">🔧 InfluxDB</span>
      <span class="glass-card" style="padding: 0.5rem 1.2rem;">⚡ REST APIs</span>
      <span class="glass-card" style="padding: 0.5rem 1.2rem;">🎯 CVzone</span>
      <span class="glass-card" style="padding: 0.5rem 1.2rem;">📊 Line Protocol</span>
      <span class="glass-card" style="padding: 0.5rem 1.2rem;">🛡️ Flask-Login</span>
    </div>
  </section>

  <!-- Experience & Leadership Timeline -->
  <section id="experience">
    <h2>Leadership & Journey</h2>
    <div class="timeline">
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <h3>General Secretary</h3>
          <span style="color:#2D9C7C;">Tontadarya College of Engineering | 2023 – Present</span>
          <p>Lead student council, orchestrated 5+ inter-college tech fests, improved student participation by 45%, and initiated mentorship programs bridging juniors with industry experts.</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <h3>Finalist – Speak for India (Times Group)</h3>
          <span style="color:#2D9C7C;">Regional Level | 2023</span>
          <p>Competed among 2000+ participants, reached finals with evidence-based arguments on "Digital Divide & Education". Recognized for structured oratory & analytical depth.</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <h3>Research Presenter & Hackathon Finalist</h3>
          <span style="color:#2D9C7C;">National / State Level</span>
          <p>Presented papers on gesture-controlled interfaces, smart queue systems at IEEE symposiums. Awarded 'Best Presenter' for research on time-series databases.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects Cards with Modal -->
  <section id="projects">
    <h2>Signature Projects</h2>
    <div class="projects-grid">
      <div class="project-card" data-pid="0"><i class="fas fa-hand-peace fa-2x" style="color:#2D9C7C;"></i><h3>Hand Gesture Presentation</h3><p>AI gesture recognition (MediaPipe, OpenCV) for slide control, zoom, writing — eliminates hardware dependency.</p><small>🔬 Major Project · Real-time</small></div>
      <div class="project-card" data-pid="1"><i class="fas fa-users fa-2x" style="color:#2D9C7C;"></i><h3>Smart Queue Management</h3><p>Flask + MongoDB web app: token booking, live staff dashboard, analytics, REST APIs, animated Bootstrap UI.</p><small>⚡ Full-stack · Load tested</small></div>
      <div class="project-card" data-pid="2"><i class="fas fa-chart-line fa-2x" style="color:#2D9C7C;"></i><h3>Time-Series DB with InfluxDB</h3><p>Ingested, stored & visualized sensor archival data using Python + InfluxQL, enabling trend monitoring.</p><small>📈 Data Engineering · Visualization</small></div>
    </div>
  </section>

  <!-- Education & Certifications -->
  <section id="education">
    <h2>Education & Certifications</h2>
    <div class="grid-2col">
      <div class="glass-card" style="padding: 1.6rem;"><i class="fas fa-graduation-cap fa-2x"></i><h3>B.E. Computer Science</h3><p>Tontadarya College of Engineering, Gadag<br>2022 – 2026 | CGPA: 8.73 (till 6th Sem)</p></div>
      <div class="glass-card" style="padding: 1.6rem;"><i class="fas fa-school fa-2x"></i><h3>Pre-University + High School</h3><p>Government PU College: 84% | High School: 81.4% CGPA</p></div>
      <div class="glass-card" style="padding: 1.6rem;"><i class="fas fa-certificate fa-2x"></i><h3>Certifications</h3><p>✅ NPTEL: Database Management System (Elite)<br>✅ NPTEL: Python Programming<br>✅ Cybersecurity Essentials (Cisco)</p></div>
      <div class="glass-card" style="padding: 1.6rem;"><i class="fas fa-trophy fa-2x"></i><h3>Honors</h3><p>🏆 Speak for India Debate Finalist<br>🏆 Best Presenter Award (Tech Symposium)<br>🏆 College Leadership Excellence</p></div>
    </div>
  </section>

  <!-- Contact + Social -->
  <section id="contact">
    <h2>Let's Create Impact</h2>
    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem;">
      <div class="glass-card" style="padding: 1.8rem;">
        <h3>Send a message</h3>
        <form id="demoContactForm" class="contact-form">
          <input type="text" placeholder="Your name" required>
          <input type="email" placeholder="Email address">
          <textarea rows="3" placeholder="Collaboration / opportunity ..."></textarea>
          <button type="submit" class="btn-primary">Reach out <i class="fas fa-paper-plane"></i></button>
          <p style="font-size: 0.7rem; margin-top: 0.8rem;">✨ UI demo — I'll personally connect</p>
        </form>
      </div>
      <div class="glass-card" style="padding: 1.8rem;">
        <h3>Direct Connect</h3>
        <p><i class="fas fa-envelope"></i> mulgundpalini@gmail.com</p>
        <p><i class="fas fa-phone-alt"></i> +91 7483096295</p>
        <div class="social-icons" style="margin-top: 1.8rem;">
          <a href="#"><i class="fab fa-linkedin"></i></a>
          <a href="#"><i class="fab fa-github"></i></a>
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-dev"></i></a>
        </div>
        <div style="margin-top: 2rem;"><span class="glass-card" style="display: inline-block; padding: 0.4rem 1.2rem;"><i class="fas fa-map-pin"></i> Gadag, Karnataka, India</span></div>
      </div>
    </div>
  </section>
</main>

<footer>
  <p>© 2025 Palini Mulgund — Built with cinematic vision | Open for SDE internships & full-time collaborations</p>
</footer>

<div class="back-to-top" id="backToTopBtn"><i class="fas fa-arrow-up"></i></div>

<!-- Modal Structure -->
<div id="projectModal" class="modal">
  <div class="modal-content">
    <span class="close-modal">&times;</span>
    <h3 id="modalTitle"></h3>
    <p id="modalDesc" style="margin: 1rem 0;"></p>
    <p id="modalTech" style="color:#2D9C7C; font-weight:500;"></p>
  </div>
</div>

<script>
  // TYPING ANIMATION (cinematic header)
  const roles = ["Palini Mulgund", "CS Innovator", "Tech Orator", "Future Engineer"];
  let roleIdx = 0, charIdx = 0;
  const typedSpan = document.getElementById("typedOutput");
  function typeWriter() {
    if (charIdx <= roles[roleIdx].length) {
      typedSpan.textContent = roles[roleIdx].substring(0, charIdx);
      charIdx++;
      setTimeout(typeWriter, 120);
    } else {
      setTimeout(() => {
        charIdx = 0;
        roleIdx = (roleIdx + 1) % roles.length;
        typeWriter();
      }, 2200);
    }
  }
  typeWriter();

  // Intersection Observer for progress bars
  const fills = document.querySelectorAll('.progress-fill');
  const progressObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const el = entry.target;
        const widthVal = el.getAttribute('data-width');
        el.style.width = widthVal + '%';
        progressObserver.unobserve(el);
      }
    });
  }, { threshold: 0.3 });
  fills.forEach(f => progressObserver.observe(f));

  // scroll progress + active nav + back-to-top
  const progressBar = document.getElementById('progressBar');
  const sections = document.querySelectorAll('section');
  const navLinks = document.querySelectorAll('.nav-link');
  const backBtn = document.getElementById('backToTopBtn');
  window.addEventListener('scroll', () => {
    const winScroll = document.documentElement.scrollTop;
    const height = document.documentElement.scrollHeight - window.innerHeight;
    const scrolled = (winScroll / height) * 100;
    progressBar.style.width = scrolled + '%';
    let current = "";
    sections.forEach(section => {
      const sectionTop = section.offsetTop - 250;
      if (winScroll >= sectionTop) current = section.getAttribute('id');
    });
    navLinks.forEach(link => {
      link.classList.remove('active');
      if (link.getAttribute('href') === `#${current}`) link.classList.add('active');
    });
    if (winScroll > 450) backBtn.style.opacity = '1'; else backBtn.style.opacity = '0';
  });
  backBtn.addEventListener('click', () => window.scrollTo({ top: 0, behavior: 'smooth' }));

  // Project Modal interactivity
  const modal = document.getElementById('projectModal');
  const modalTitle = document.getElementById('modalTitle');
  const modalDesc = document.getElementById('modalDesc');
  const modalTech = document.getElementById('modalTech');
  const projectsData = [
    { title: "Hand Gesture Controlled Presentations", desc: "Revolutionary real-time system using MediaPipe & OpenCV. Control slides, zoom, annotations, video playback via intuitive hand gestures. No dataset training required — lightweight and enhances presenter dynamism. Major Research Project.", tech: "Python, OpenCV, CVzone, MediaPipe" },
    { title: "Smart Queue Management System", desc: "Full-stack web solution with Flask, MongoDB, and Bootstrap canvas. Staff dashboard with token actions (Done/Cancel), average service time analytics, secure Flask-Login, and REST APIs for real-time status updates.", tech: "Flask, MongoDB, REST API, Bootstrap, CSS animations" },
    { title: "Time Series Database for Archival Data", desc: "Built with InfluxDB (open source) and Python ingestion scripts. Efficiently stores sensor archival data, performs time-based queries, and visualizes historical trends for monitoring & anomaly detection.", tech: "InfluxDB, Python, Line Protocol, Data Visualization" }
  ];
  const projectCards = document.querySelectorAll('.project-card');
  projectCards.forEach((card, idx) => {
    card.addEventListener('click', () => {
      modalTitle.innerText = projectsData[idx].title;
      modalDesc.innerText = projectsData[idx].desc;
      modalTech.innerText = "🛠️ Stack: " + projectsData[idx].tech;
      modal.style.display = 'flex';
    });
  });
  document.querySelector('.close-modal').addEventListener('click', () => modal.style.display = 'none');
  window.addEventListener('click', (e) => { if (e.target === modal) modal.style.display = 'none'; });

  // Contact form demo handler
  const contactForm = document.getElementById('demoContactForm');
  contactForm.addEventListener('submit', (e) => {
    e.preventDefault();
    alert("✨ Message sent (demo). Palini will reach out to you soon. Thank you!");
    contactForm.reset();
  });

  // Smooth anchor scroll
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function(e) {
      const targetId = this.getAttribute('href');
      if (targetId === "#") return;
      const target = document.querySelector(targetId);
      if (target) {
        e.preventDefault();
        target.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });

  // Parallax-like background micro motion
  document.addEventListener('mousemove', (e) => {
    const moveX = (e.clientX / window.innerWidth) * 18;
    const moveY = (e.clientY / window.innerHeight) * 18;
    document.querySelector('.animated-bg').style.transform = `translate(${moveX * 0.03}px, ${moveY * 0.03}px)`;
  });
</script>
</body>
</html>
