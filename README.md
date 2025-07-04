
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Developer Portfolio | @tyson_owner</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Orbitron:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0a0a14;
            --secondary: #1a1a2e;
            --accent: #ff2a6d;
            --accent-light: #ff4d87;
            --accent-blue: #05d9e8;
            --text: #e0e0ff;
            --card-bg: rgba(26, 26, 46, 0.7);
            --border: rgba(80, 80, 120, 0.3);
        }

        body {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: var(--text);
            min-height: 100vh;
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            position: relative;
            line-height: 1.6;
        }

        /* Scanlines effect */
        body::after {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(
                0deg,
                rgba(0, 0, 0, 0.15),
                rgba(0, 0, 0, 0.15) 1px,
                transparent 1px,
                transparent 2px
            );
            pointer-events: none;
            z-index: 100;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            backdrop-filter: blur(10px);
            background: rgba(10, 10, 20, 0.8);
            border-bottom: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .header-scrolled {
            background: rgba(10, 10, 20, 0.95);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 24px;
            font-weight: 700;
            background: linear-gradient(90deg, var(--accent), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .logo-icon {
            font-size: 26px;
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            color: var(--text);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 5px 0;
            transition: color 0.3s ease;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--accent-light);
        }

        /* Hero Section */
        .hero {
            padding: 120px 0 80px;
            text-align: center;
            position: relative;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .hero h1 {
            font-size: 4.5rem;
            margin-bottom: 20px;
            font-family: 'Orbitron', sans-serif;
            background: linear-gradient(90deg, var(--accent), var(--accent-blue));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: 1px;
            line-height: 1.1;
        }

        .hero h2 {
            font-size: 2rem;
            margin-bottom: 30px;
            color: var(--accent-light);
            font-weight: 400;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 40px;
            color: #a0a0c0;
        }

        .specialization {
            display: inline-block;
            padding: 8px 20px;
            background: rgba(255, 42, 109, 0.1);
            border-radius: 30px;
            font-size: 1.1rem;
            margin-top: 20px;
            border: 1px solid var(--accent);
            color: var(--accent-light);
            font-weight: 500;
        }

        /* Sections */
        .section {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 70px;
            position: relative;
            font-family: 'Orbitron', sans-serif;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--accent-blue));
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-image {
            position: relative;
            border-radius: 15px;
            overflow: hidden;
            border: 3px solid var(--accent);
            box-shadow: 0 10px 30px rgba(255, 42, 109, 0.2);
        }

        .about-image img {
            width: 100%;
            display: block;
            transition: transform 0.5s ease;
        }

        .about-image:hover img {
            transform: scale(1.05);
        }

        .about-text {
            padding: 20px;
        }

        .about-info {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin: 30px 0;
        }

        .info-item {
            background: var(--card-bg);
            padding: 20px;
            border-radius: 10px;
            border: 1px solid var(--border);
            backdrop-filter: blur(10px);
        }

        .info-item h4 {
            color: var(--accent-blue);
            margin-bottom: 10px;
            font-size: 1.1rem;
        }

        .info-item p {
            font-size: 1.1rem;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            border: 1px solid var(--border);
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(5, 217, 232, 0.2);
        }

        .skill-card i {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--accent-blue);
        }

        .skill-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--accent-light);
        }

        .skill-card p {
            color: #a0a0c0;
        }

        /* Channels Section */
        .channel-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .channel-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(10px);
        }

        .channel-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
        }

        .channel-card:hover {
            transform: translateY(-10px);
        }

        .channel-card.trading::before {
            background: linear-gradient(90deg, #FFD700, #FFA500);
        }

        .channel-card.trading:hover {
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.2);
        }

        .channel-card.src::before {
            background: linear-gradient(90deg, #1E90FF, #4169E1);
        }

        .channel-card.src:hover {
            box-shadow: 0 10px 30px rgba(30, 144, 255, 0.2);
        }

        .channel-card.hacking::before {
            background: linear-gradient(90deg, #32CD32, #00FF00);
        }

        .channel-card.hacking:hover {
            box-shadow: 0 10px 30px rgba(50, 205, 50, 0.2);
        }

        .channel-card.gaming::before {
            background: linear-gradient(90deg, #FF4500, #FF6347);
        }

        .channel-card.gaming:hover {
            box-shadow: 0 10px 30px rgba(255, 69, 0, 0.2);
        }

        .channel-icon {
            font-size: 40px;
            margin-bottom: 20px;
        }

        .channel-card.trading .channel-icon {
            color: #FFD700;
        }

        .channel-card.src .channel-icon {
            color: #1E90FF;
        }

        .channel-card.hacking .channel-icon {
            color: #32CD32;
        }

        .channel-card.gaming .channel-icon {
            color: #FF4500;
        }

        .channel-card h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
        }

        .channel-card p {
            color: #a0a0c0;
            margin-bottom: 25px;
            min-height: 80px;
        }

        /* Buttons */
        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(90deg, var(--accent), var(--accent-light));
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            font-size: 1rem;
        }

        .btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.6s ease;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(255, 42, 109, 0.4);
        }

        .btn:hover::after {
            left: 100%;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--accent);
            color: var(--accent-light);
        }

        .btn-outline:hover {
            background: rgba(255, 42, 109, 0.1);
        }

        /* Contact Section */
        .owner-info {
            background: var(--card-bg);
            max-width: 600px;
            margin: 0 auto;
            padding: 40px;
            border-radius: 15px;
            border: 1px solid var(--border);
            backdrop-filter: blur(10px);
            position: relative;
            text-align: center;
        }

        .owner-info::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(90deg, var(--accent), var(--accent-blue));
        }

        .owner-icon {
            font-size: 50px;
            color: var(--accent-blue);
            margin-bottom: 20px;
        }

        .owner-info h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
        }

        .telegram-handle {
            display: inline-block;
            font-size: 1.5rem;
            font-weight: 600;
            background: linear-gradient(90deg, #0088cc, #00aced);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin: 20px 0;
            padding: 8px 20px;
            border-radius: 30px;
            border: 1px solid #0088cc;
        }

        /* Footer */
        footer {
            padding: 40px 0;
            text-align: center;
            border-top: 1px solid var(--border);
            margin-top: 60px;
            background: rgba(10, 10, 20, 0.8);
        }

        .copyright {
            color: #a0a0c0;
            font-size: 1.1rem;
        }

        .made-by {
            margin-top: 10px;
            font-size: 1.2rem;
            color: var(--accent-light);
        }

        /* Animation for hero text */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero-content {
            animation: fadeIn 1s ease-out;
        }

        /* Glowing elements */
        .glow {
            text-shadow: 0 0 10px rgba(255, 42, 109, 0.7);
        }

        /* Responsive design */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 3.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .about-image {
                max-width: 500px;
                margin: 0 auto;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero h2 {
                font-size: 1.5rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .about-info {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .section {
                padding: 70px 0;
            }
            
            .channel-card, .skill-card {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container nav-container">
            <div class="logo">
                <i class="fas fa-code logo-icon"></i>
                <span>TysonPortfolio</span>
            </div>
            <nav class="nav-links">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#skills">Skills</a>
                <a href="#channels">Channels</a>
                <a href="#contact">Contact</a>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container hero-content">
            <h1>TYSON DEVELOPER PORTFOLIO</h1>
            <h2>Full Stack Developer & Security Specialist</h2>
            <p>Specializing in advanced development, security solutions, and innovative gaming modifications. Pushing the boundaries of technology with cutting-edge expertise.</p>
            <div class="specialization glow">@TYSON_OK_WIN_HACK Specialist</div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section" id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1536104968055-4d61aa56f46a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=880&q=80" alt="Developer Image">
                </div>
                <div class="about-text">
                    <h3>Hello, I'm a Tyson Developer</h3>
                    <p>I specialize in creating secure, efficient, and innovative solutions for web applications, Telegram bots, and gaming platforms. With a background in technology and a passion for coding, I constantly explore new horizons in development.</p>
                    
                    <div class="about-info">
                        <div class="info-item">
                            <h4>Country:</h4>
                            <p>India</p>
                        </div>
                        <div class="info-item">
                            <h4>Age:</h4>
                            <p>26</p>
                        </div>
                        <div class="info-item">
                            <h4>Education:</h4>
                            <p>B.Tech (Bachelor of Technology)</p>
                        </div>
                        <div class="info-item">
                            <h4>Hobbies:</h4>
                            <p>Coding, Gaming, Designing, Web Development</p>
                        </div>
                    </div>
                    
                    <a href="#contact" class="btn">Contact Me</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="section" id="skills">
        <div class="container">
            <h2 class="section-title">My Skills</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <i class="fab fa-php"></i>
                    <h3>PHP & Python Bots</h3>
                    <p>Development of advanced bots for automation, data processing, and interaction using PHP and Python.</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-html5"></i>
                    <h3>HTML, CSS, JS</h3>
                    <p>Expert in front-end technologies to create responsive, interactive, and visually appealing web interfaces.</p>
                </div>
                <div class="skill-card">
                    <i class="fab fa-telegram"></i>
                    <h3>Telegram Bot Development</h3>
                    <p>Building feature-rich Telegram bots for various purposes including automation, notifications, and interactions.</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-paint-brush"></i>
                    <h3>Web UI/UX Design</h3>
                    <p>Creating intuitive user interfaces and experiences with a focus on usability and aesthetic appeal.</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-robot"></i>
                    <h3>Automation Systems</h3>
                    <p>Designing and implementing complex automation systems to streamline processes and increase efficiency.</p>
                </div>
                <div class="skill-card">
                    <i class="fas fa-shield-alt"></i>
                    <h3>Security Solutions</h3>
                    <p>Developing secure applications and implementing best practices for data protection and system security.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Channels Section -->
    <section class="section" id="channels">
        <div class="container">
            <h2 class="section-title">My Channels</h2>
            <div class="channel-grid">
                <!-- Trading Channel -->
                <div class="channel-card trading">
                    <div class="channel-icon">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Trading Channel</h3>
                    <p>Advanced trading strategies, market insights, and financial hacking techniques. Exclusive content for serious traders.</p>
                    <a href="https://t.me/TYSON_OK_WIN_HACK" target="_blank" class="btn">JOIN COLOR TRADING CHANNEL</a>
                </div>
                
                <!-- Source Code Channel -->
                <div class="channel-card src">
                    <div class="channel-icon">
                        <i class="fas fa-code"></i>
                    </div>
                    <h3>Source Code Channel</h3>
                    <p>Access premium source codes, development resources, and programming tools. Everything a developer needs in one place.</p>
                    <a href="https://t.me/nobita_src" target="_blank" class="btn">JOIN ALL SRC CHANNEL</a>
                </div>
                
                <!-- Hacking Channel -->
                <div class="channel-card hacking">
                    <div class="channel-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3>Hacking Channel</h3>
                    <p>Learn ethical hacking techniques, cybersecurity practices, and penetration testing. Stay ahead in the security landscape.</p>
                    <a href="https://t.me/+fCz8oujNthtlMzJl" target="_blank" class="btn">Join Hacking Channel</a>
                </div>
                
                <!-- Gaming Channel -->
                <div class="channel-card gaming">
                    <div class="channel-icon">
                        <i class="fas fa-gamepad"></i>
                    </div>
                    <h3>Gaming Channel</h3>
                    <p>Get the latest hacks, mods, and cheats for BGMI and PUBG Lite. Elevate your gaming experience with our exclusive tools.</p>
                    <a href="https://t.me/+O60hs11qayAwMzFl" target="_blank" class="btn">Join Gaming Channel</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section" id="contact">
        <div class="container">
            <h2 class="section-title">Contact Me</h2>
            <div class="owner-info">
                <div class="owner-icon">
                    <i class="fas fa-user-secret"></i>
                </div>
                <h3>Project Owner</h3>
                <p>For business inquiries, collaborations, or support questions, contact me directly via Telegram.</p>
                <div class="telegram-handle">@tyson_owner</div>
                <a href="https://t.me/tyson_owner" target="_blank" class="btn">Message on Telegram</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p class="copyright">© 2023 Tyson Developer Portfolio. All rights reserved. Specialized in Any solutions.</p>
            <p class="made-by">Made with <i class="fas fa-heart" style="color: var(--accent);"></i> by @tyson_owner</p>
        </div>
    </footer>

    <script>
        // Header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('header-scrolled');
            } else {
                header.classList.remove('header-scrolled');
            }
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Glowing effect for special elements
        setInterval(() => {
            const glow = document.querySelector('.glow');
            if(glow) {
                const r = Math.floor(200 + Math.random() * 55);
                const g = Math.floor(42 + Math.random() * 50);
                const b = Math.floor(109 + Math.random() * 100);
                glow.style.textShadow = `0 0 15px rgba(${r}, ${g}, ${b}, 0.8)`;
            }
        }, 2000);
    </script>
</body>
</html>
