<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Om Kumar Dubey | Developer Portfolio</title>
    
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
    <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
    
    <style>
        :root {
            --primary-color: #2ecc71; 
            --bg-color: #ffffff;
            --text-color: #2c3e50;
            --sub-text: #7f8c8d;
            --card-bg: #f9f9f9;
            --btn-grad: linear-gradient(135deg, #2ecc71 0%, #27ae60 100%);
        }

        [data-theme="dark"] {
            --primary-color: #00ff88;
            --bg-color: #0b0e14;
            --text-color: #e0e0e0;
            --sub-text: #b0b0b0;
            --card-bg: #161b22;
            --btn-grad: linear-gradient(135deg, #00ff88 0%, #00bd63 100%);
        }

        /* Existing Reset & Transitions */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', -apple-system, sans-serif;
            transition: background 0.3s ease, color 0.3s ease;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navbar Styling */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 8%;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.8);
        }
        [data-theme="dark"] nav { background: rgba(11, 14, 20, 0.8); }

        .logo { font-weight: 800; font-size: 1.4rem; color: var(--primary-color); letter-spacing: -1px; }
        .nav-links { display: flex; list-style: none; align-items: center; }
        .nav-links li { margin-left: 25px; cursor: pointer; font-size: 0.95rem; }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 10%;
        }
        .hero-text h1 { font-size: 4rem; line-height: 1.1; margin-bottom: 15px; }
        .hero-text span { color: var(--primary-color); }

        /* --- THE NEW BUTTON STYLES --- */
        .cta-container {
            margin-top: 35px;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            text-decoration: none;
            padding: 16px 32px;
            font-size: 1.1rem;
            font-weight: 700;
            color: #000;
            background: var(--btn-grad);
            border-radius: 50px;
            box-shadow: 0 4px 15px rgba(46, 204, 113, 0.3);
            position: relative;
            overflow: hidden;
            animation: pulse-glow 2s infinite;
            transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .cta-button i {
            margin-right: 10px;
            font-size: 1.2rem;
        }

        .cta-button:hover {
            transform: scale(1.08) rotate(-1deg);
            box-shadow: 0 8px 25px rgba(46, 204, 113, 0.5);
        }

        .cta-button:active {
            transform: scale(0.95);
        }

        /* Best Animation: Pulse & Glow */
        @keyframes pulse-glow {
            0% { box-shadow: 0 0 0 0 rgba(46, 204, 113, 0.7); }
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
