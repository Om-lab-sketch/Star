<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Om Kumar Dubey | Developer Portfolio</title>
    
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary-color: #2ecc71;
            --bg-color: #ffffff;
            --text-color: #2c3e50; /* Fixed missing semicolon */
            --sub-text: #7f8c8d;
            --card-bg: #f9f9f9;
            --accent-gradient: linear-gradient(45deg, #2ecc71, #27ae60);
        }

        [data-theme="dark"] {
            --primary-color: #00ff88;
            --bg-color: #0b0e14;
            --text-color: #e0e0e0;
            --sub-text: #b0b0b0;
            --card-bg: #161b22;
            --accent-gradient: linear-gradient(45deg, #00ff88, #00bd68);
        }

        /* ... Your existing styles ... */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', -apple-system, sans-serif; transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
        body { background-color: var(--bg-color); color: var(--text-color); line-height: 1.6; overflow-x: hidden; }
        nav { display: flex; justify-content: space-between; align-items: center; padding: 20px 8%; position: fixed; width: 100%; top: 0; z-index: 1000; backdrop-filter: blur(10px); background: rgba(255, 255, 255, 0.8); }
        [data-theme="dark"] nav { background: rgba(11, 14, 20, 0.8); }
        .logo { font-weight: 800; font-size: 1.4rem; color: var(--primary-color); letter-spacing: -1px; }
        .nav-links { display: flex; list-style: none; align-items: center; }
        .nav-links li { margin-left: 25px; cursor: pointer; font-size: 0.95rem; }
        .hero { height: 100vh; display: flex; align-items: center; justify-content: space-between; padding: 0 10%; }
        .hero-text h1 { font-size: 4rem; line-height: 1.1; margin-bottom: 15px; }
        .hero-text span { color: var(--primary-color); }
        .hero-img img { width: 480px; animation: float 6s ease-in-out infinite; }

        @keyframes float { 0%, 100% { transform: translateY(0px); } 50% { transform: translateY(-20px); } }

        /* --- NEW: POKI BUTTON STYLES --- */
        .poki-btn-container {
            margin-top: 40px;
        }

        .poki-btn {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 18px 35px;
            font-size: 1.2rem;
            font-weight: 700;
            text-decoration: none;
            color: #fff;
            background: var(--accent-gradient);
            border-radius: 50px;
            position: relative;
            box-shadow: 0 10px 20px rgba(46, 204, 113, 0.3);
            animation: pulse-glow 2s infinite;
            overflow: hidden;
        }

        .poki-btn i {
            font-size: 1.4rem;
        }

        .poki-btn:hover {
            transform: scale(1.1) rotate(-2deg);
            box-shadow: 0 15px 30px rgba(46, 204, 113, 0.5);
            color: #fff;
        }

        /* Shine Effect Animation */
        .poki-btn::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: rgba(255,255,255,0.2);
            transform: rotate(45deg);
            transition: 0.5s;
            left: -100%;
        }

        .poki-btn:hover::after {
            left: 100%;
        }

        @keyframes pulse-glow {
            0% { box-shadow: 0 0 0 0 rgba(46, 204, 113, 0.7); }
            70% { box-shadow: 0 0 0 20px rgba(46, 204, 113, 0); }
            100% { box-shadow: 0 0 0 0 rgba(46, 204, 113, 0); }
        }

        /* --- END POKI BUTTON --- */

        section { padding: 120px 10%; }
        .section-title { font-size: 2.8rem; margin-bottom: 60px; text-align: center; }
        .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 25px; }
        .skill-card { background: var(--card-bg); padding: 40px 20px; border-radius: 20px; text-align: center; border: 1px solid transparent; }
        .skill-card:hover { border-color: var(--primary-color); box-shadow: 0 20px 40px rgba(0,0,0,0.1); transform: scale(1.03); }
        .skill-card i { font-size: 3.5rem; color: var(--primary-color); margin-bottom: 20px; }
        #theme-toggle { background: var(--primary-color); color: #000; border: none; padding: 10px 20px; border-radius: 12px; cursor: pointer; font-weight: 600; }

        @media (max-width: 968px) {
            .hero { flex-direction: column; text-align: center; justify-content: center; padding-top: 100px; }
            .hero-img img { width: 280px; margin-top: 40px; }
            .hero-text h1 { font-size: 2.8rem; }
        }
    </style>
</head>
<body data-theme="dark">

    <nav>
        <div class="logo">OM KUMAR DUBEY</div>
        <ul class="nav-links">
            <li>Skills</li>
            <li>Projects</li>
            <li>Contact</li>
            <li><button id="theme-toggle">Light Mode</button></li>
        </ul>
    </nav>

    <section class="hero">
        <div class="hero-text" data-aos="fade-right">
            <h1>Hi, I'm <span>Om Kumar Dubey</span></h1>
            <h2>I'm a <span id="typed"></span></h2>
            <p style="color: var(--sub-text); margin-top: 20px; max-width: 550px; font-size: 1.1rem;">
                Passionate about building clean web experiences and exploring the world of <b>Python</b> and <b>AI</b>. Always ranking high in performance and creativity.
            </p>
            
            <div class="poki-btn-container">
                <a href="https://poki.com/" target="_blank" class="poki-btn">
                    <i class="fas fa-gamepad"></i>
                    Take a Break & Play
                </a>
            </div>
        </div>
        <div class="hero-img" data-aos="zoom-in">
            <img src="https://raw.githubusercontent.com/saadpasta/developerFolio/master/src/assets/images/manOnTable.svg" alt="developer">
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title" data-aos="fade-up">My Expertise</h2>
        <div class="skills-grid">
            <div class="skill-card" data-aos="fade-up" data-aos-delay="100">
                <i class="fab fa-python"></i>
                <h3>Python Pro</h3>
                <p>Developing scripts and logic-driven applications.</p>
            </div>
            <div class="skill-card" data-aos="fade-up" data-aos-delay="200">
                <i class="fas fa-code"></i>
                <h3>Web Wizard</h3>
                <p>Creating responsive layouts with HTML, CSS, and JS.</p>
            </div>
            <div class="skill-card" data-aos="fade-up" data-aos-delay="300">
                <i class="fas fa-brain"></i>
                <h3>AI Enthusiast</h3>
                <p>Experimenting with prompts and high-fidelity generation.</p>
            </div>
        </div>
    </section>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1200, once: true });

        new Typed('#typed', {
            strings: ['Python Developer', 'Creative Coder', 'Web Designer', 'Tech Innovator'],
            typeSpeed: 60,
            backSpeed: 40,
            loop: true
        });

        const toggleBtn = document.getElementById('theme-toggle');
        const body = document.body;

        toggleBtn.addEventListener('click', () => {
            const isDark = body.getAttribute('data-theme') === 'dark';
            body.setAttribute('data-theme', isDark ? 'light' : 'dark');
            toggleBtn.innerText = isDark ? 'Dark Mode' : 'Light Mode';
        });
    </script>
</body>
</html>
            70% { box-shadow: 0 0 0 15px rgba(46, 204, 113, 0); }
            100% { box-shadow: 0 0 0 0 rgba(46, 204, 113, 0); }
        }

        /* Existing Hero Image Animation */
        .hero-img img {
            width: 480px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Skills/Cards Section */
        section { padding: 120px 10%; }
        .section-title { font-size: 2.8rem; margin-bottom: 60px; text-align: center; }
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
        }
        .skill-card {
            background: var(--card-bg);
            padding: 40px 20px;
            border-radius: 20px;
            text-align: center;
            border: 1px solid transparent;
        }
        .skill-card:hover {
            border-color: var(--primary-color);
            transform: translateY(-10px);
        }

        #theme-toggle {
            background: var(--primary-color);
            color: #000;
            border: none;
            padding: 10px 20px;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 600;
        }

        @media (max-width: 968px) {
            .hero { flex-direction: column; text-align: center; justify-content: center; padding-top: 100px; }
            .hero-img img { width: 280px; margin-top: 40px; }
            .hero-text h1 { font-size: 2.8rem; }
        }
    </style>
</head>
<body data-theme="dark">

    <nav>
        <div class="logo">OM KUMAR DUBEY</div>
        <ul class="nav-links">
            <li>Skills</li>
            <li>Projects</li>
            <li>Contact</li>
            <li><button id="theme-toggle">Light Mode</button></li>
        </ul>
    </nav>

    <section class="hero">
        <div class="hero-text" data-aos="fade-right">
            <h1>Hi, I'm <span>Om Kumar Dubey</span></h1>
            <h2>I'm a <span id="typed"></span></h2>
            <p style="color: var(--sub-text); margin-top: 20px; max-width: 550px; font-size: 1.1rem;">
                Passionate about building clean web experiences and exploring the world of <b>Python</b> and <b>AI</b>. Always ranking high in performance and creativity.
            </p>
            
            <div class="cta-container">
                <a href="https://poki.com/en/g/subway-surfers" target="_blank" class="cta-button">
                    <i class="fas fa-gamepad"></i> Play Subway Surfers
                </a>
            </div>
        </div>

        <div class="hero-img" data-aos="fade-left">
            <img src="https://raw.githubusercontent.com/saadpasta/developerFolio/master/src/assets/images/manOnTable.svg" alt="developer">
        </div>
    </section>

    <section id="skills">
        <h2 class="section-title" data-aos="fade-up">My Expertise</h2>
        <div class="skills-grid">
            <div class="skill-card" data-aos="fade-up" data-aos-delay="100">
                <i class="fab fa-python"></i>
                <h3>Python Pro</h3>
                <p>Developing scripts and logic-driven applications.</p>
            </div>
            <div class="skill-card" data-aos="fade-up" data-aos-delay="200">
                <i class="fas fa-code"></i>
                <h3>Web Wizard</h3>
                <p>Creating responsive layouts with HTML, CSS, and JS.</p>
            </div>
            <div class="skill-card" data-aos="fade-up" data-aos-delay="300">
                <i class="fas fa-brain"></i>
                <h3>AI Enthusiast</h3>
                <p>Experimenting with prompts and high-fidelity generation.</p>
            </div>
        </div>
    </section>

    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1000, once: true });

        new Typed('#typed', {
            strings: ['Python Developer', 'Creative Coder', 'Web Designer', 'Tech Innovator'],
            typeSpeed: 60,
            backSpeed: 40,
            loop: true
        });

        const toggleBtn = document.getElementById('theme-toggle');
        const body = document.body;

        toggleBtn.addEventListener('click', () => {
            const isDark = body.getAttribute('data-theme') === 'dark';
            body.setAttribute('data-theme', isDark ? 'light' : 'dark');
            toggleBtn.innerText = isDark ? 'Dark Mode' : 'Light Mode';
        });
    </script>
</body>
</html>
