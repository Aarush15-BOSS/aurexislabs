<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aurexis Labs - Innovation Redefined | Founded by Aarush Agrawal</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #6366f1;
            --primary-dark: #4f46e5;
            --secondary: #06b6d4;
            --accent: #f59e0b;
            --dark: #0f172a;
            --dark-light: #1e293b;
            --light: #f8fafc;
            --white: #ffffff;
            --gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --gradient-2: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--dark);
            overflow-x: hidden;
        }

        /* Navbar */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(20px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--white);
            text-decoration: none;
        }

        .logo img {
            height: 50px;
            width: 50px;
            border-radius: 12px;
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
            align-items: center;
        }

        .nav-link {
            color: rgba(255, 255, 255, 0.9);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-link:hover {
            color: var(--primary);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--primary);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        .cta-button {
            background: var(--gradient);
            color: white;
            padding: 12px 28px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.6);
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            background: var(--gradient);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 1000"><defs><radialGradient id="a" cx="50%" cy="50%"><stop offset="0%" stop-color="%23ffffff" stop-opacity="0.1"/><stop offset="100%" stop-color="%23ffffff" stop-opacity="0"/></radialGradient></defs><circle cx="200" cy="200" r="100" fill="url(%23a)"><animate attributeName="r" values="100;150;100" dur="3s" repeatCount="indefinite"/></circle><circle cx="800" cy="300" r="80" fill="url(%23a)"><animate attributeName="r" values="80;120;80" dur="4s" repeatCount="indefinite"/></circle></svg>');
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .hero-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            position: relative;
            z-index: 2;
        }

        .hero-text h1 {
            font-size: clamp(3rem, 6vw, 5rem);
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff 0%, #e2e8f0 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1.5rem;
            line-height: 1.1;
        }

        .hero-text .subtitle {
            font-size: 1.5rem;
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 2rem;
            font-weight: 400;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .btn-primary {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            color: white;
            padding: 18px 36px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .btn-primary:hover {
            background: white;
            color: var(--dark);
            transform: translateY(-3px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            padding: 18px 36px;
            border: 2px solid rgba(255, 255, 255, 0.3);
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-3px);
        }

        .hero-image {
            position: relative;
            justify-self: end;
        }

        .hero-image img {
            width: 100%;
            max-width: 500px;
            border-radius: 30px;
            box-shadow: 0 50px 100px rgba(0, 0, 0, 0.3);
            animation: floatImage 6s ease-in-out infinite;
        }

        @keyframes floatImage {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(2deg); }
        }

        /* Stats Section */
        .stats {
            padding: 6rem 2rem;
            background: var(--light);
            text-align: center;
        }

        .stats-container {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .stat-item {
            padding: 2rem;
        }

        .stat-number {
            font-size: 4rem;
            font-weight: 800;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        /* About Section */
        .about {
            padding: 8rem 2rem;
            background: var(--white);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .section-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .section-title {
            font-size: clamp(2.5rem, 4vw, 3.5rem);
            font-weight: 800;
            margin-bottom: 1rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-subtitle {
            font-size: 1.25rem;
            color: #64748b;
            max-width: 600px;
            margin: 0 auto;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .founder-info h3 {
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .founder-info .role {
            color: var(--primary);
            font-weight: 600;
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: var(--gradient);
            color: white;
            border-radius: 12px;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.2rem;
        }

        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 15px 30px rgba(99, 102, 241, 0.4);
        }

        .about-image {
            text-align: center;
        }

        .about-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 20px;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.15);
        }

        /* Services */
        .services {
            padding: 8rem 2rem;
            background: var(--dark-light);
            color: white;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            padding: 2.5rem;
            border-radius: 24px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient);
        }

        .service-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.3);
            border-color: var(--primary);
        }

        .service-icon {
            width: 80px;
            height: 80px;
            background: var(--gradient);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            margin-bottom: 1.5rem;
        }

        /* Contact */
        .contact {
            padding: 8rem 2rem;
            background: var(--gradient);
            color: white;
        }

        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: start;
        }

        .contact-info h3 {
            font-size: 2rem;
            margin-bottom: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 12px;
        }

        .contact-form {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            padding: 2.5rem;
            border-radius: 24px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 12px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            font-family: inherit;
            transition: all 0.3s ease;
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: rgba(255, 255, 255, 0.7);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.2);
        }

        .submit-btn {
            width: 100%;
            background: var(--white);
            color: var(--dark);
            padding: 1.2rem;
            border: none;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        /* Footer */
        .footer {
            background: var(--dark);
            color: white;
            text-align: center;
            padding: 3rem 2rem 1.5rem;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .footer-link {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-link:hover {
            color: var(--primary);
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }

            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 2rem;
            }

            .hero-buttons {
                justify-content: center;
            }

            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .stats-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Scroll animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#home" class="logo">
                <img src="https://i.postimg.cc/ZnvffBCg/1dcdb7f7-de7b-48ae-920e-9869e990031b-7C361840-19A8-47AC-B944-81763F2E43D9.jpg" alt="Aurexis Labs Logo">
                <span>Aurexis Labs</span>
            </a>
            <ul class="nav-menu">
                <li><a href="#home" class="nav-link">Home</a></li>
                <li><a href="#about" class="nav-link">About</a></li>
                <li><a href="#services" class="nav-link">Services</a></li>
                <li><a href="#contact" class="nav-link">Contact</a></li>
                <li><a href="mailto:aarushagrawal240411@gmail.com" class="nav-link">Email</a></li>
            </ul>
            <a href="#contact" class="cta-button">Get Started</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <div class="hero-text fade-in">
                <h1>Future-Ready Innovation<br>Engineered by <span style="background: linear-gradient(135deg, #ffffff 0%, #a5b4fc 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Aurexis Labs</span></h1>
                <p class="subtitle">Transforming bold ideas into world-class digital experiences. Founded by Aarush Agrawal.</p>
                <div class="hero-buttons">
                    <a href="#contact" class="btn-primary">Start Your Project</a>
                    <a href="#services" class="btn-secondary">Our Services</a>
                </div>
            </div>
            <div class="hero-image fade-in">
                <img src="https://i.postimg.cc/ZnvffBCg/1dcdb7f7-de7b-48ae-920e-9869e990031b-7C361840-19A8-47AC-B944-81763F2E43D9.jpg" alt="Aurexis Labs">
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="stats-container">
            <div class="stat-item fade-in">
                <div class="stat-number">100+</div>
                <div>Projects Delivered</div>
            </div>
            <div class="stat-item fade-in">
                <div class="stat-number">50+</div>
                <div>Happy Clients</div>
            </div>
            <div class="stat-item fade-in">
                <div class="stat-number">24/7</div>
                <div>Support</div>
            </div>
            <div class="stat-item fade-in">
                <div class="stat-number">99.9%</div>
                <div>Uptime</div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-header fade-in">
                <h2 class="section-title">Meet the Visionary Behind Aurexis Labs</h2>
                <p class="section-subtitle">Aarush Agrawal - Founder & CEO</p>
            </div>
            <div class="about-content">
                <div class="founder-info fade-in">
                    <h3>Aarush Agrawal</h3>
                    <div class="role">Founder & Chief Innovation Officer</div>
                    <p><strong>Aarush Agrawal</strong> is a visionary entrepreneur and technology leader who founded <strong>Aurexis Labs</strong> with a mission to redefine digital innovation. With expertise in cutting-edge technologies and a passion for creating transformative solutions, Aarush leads a team of elite developers to deliver unparalleled results.</p>
                    <p>Connect with us:</p>
                    <div class="social-links">
                        <a href="mailto:aarushagrawal240411@gmail.com" class="social-link" title="Email">
                            <i class="fas fa-envelope"></i>
                        </a>
                        <a href="https://instagram.com/aurexislabs" target="_blank" class="social-link" title="Instagram">
                            <i class="fab fa-instagram"></i>
                        </a>
                    </div>
                </div>
                <div class="about-image fade-in">
                    <img src="https://i.postimg.cc/ZnvffBCg/1dcdb7f7-de7b-48ae-920e-9869e990031b-7C361840-19A8-47AC-B944-81763F2E43D9.jpg" alt="Aarush Agrawal - Founder">
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
        <div class="container">
            <div class="section-header fade-in">
                <h2 class="section-title" style="color: white;">World-Class Services</h2>
                <p class="section-subtitle" style="color: rgba(255,255,255,0.8);">We craft digital excellence with precision and passion</p>
            </div>
            <div class="services-grid">
                <div class="service-card fade-in">
                    <div class="service-icon">
                        <i class="fas fa-rocket"></i>
                    </div>
                    <h3>Web Development</h3>
                    <p>Lightning-fast, responsive websites built with modern frameworks and best practices. From startups to enterprises.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon" style="background: linear-gradient(135deg, #06b6d4 0%, #0891b2 100%);">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3>Mobile Apps</h3>
                    <p>Native and cross-platform mobile applications that deliver exceptional user experiences across all devices.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon" style="background: linear-gradient(135deg, #10b981 0%, #059669 100%);">
                        <i class="fas fa-brain"></i>
                    </div>
                    <h3>AI & ML Solutions</h3>
                    <p>Cutting-edge artificial intelligence and machine learning solutions tailored to your business needs.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon" style="background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%);">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3>Cybersecurity</h3>
                    <p>Enterprise-grade security solutions to protect your digital assets and ensure compliance.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon" style="background: linear-gradient(135deg, #ec4899 0%, #be185d 100%);">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <h3>Digital Marketing</h3>
                    <p>Data-driven marketing strategies that convert visitors into loyal customers.</p>
                </div>
                <div class="service-card fade-in">
                    <div class="service-icon" style="background: linear-gradient(135deg, #8b5cf6 0%, #7c3aed 100%);">
                        <i class="fas fa-cloud"></i>
                    </div>
                    <h3>Cloud Solutions</h3>
                    <p>Scalable cloud infrastructure and DevOps services for maximum performance and reliability.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-header fade-in">
                <h2 class="section-title" style="color: white;">Ready to Transform Your Vision?</h2>
                <p class="section-subtitle">Let's create something extraordinary together</p>
            </div>
            <div class="contact-content">
                <div class="contact-info fade-in">
                    <h3>Get In Touch</h3>
                    <div class="contact-item">
                        <i class="fas fa-envelope" style="font-size: 1.5rem; color: var(--accent);"></i>
                        <div>
                            <strong>aarushagrawal240411@gmail.com</strong>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fab fa-instagram" style="font-size: 1.5rem; color: var(--accent);"></i>
                        <div>
                            <strong>@aurexislabs</strong>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt" style="font-size: 1.5rem; color: var(--accent);"></i>
                        <div>
                            <strong>Global Operations</strong><br>
                            Serving clients worldwide
                        </div>
                    </div>
                </div>
                <form action="https://formspree.io/f/xjgepqwn" method="POST" class="contact-form fade-in">
                    <div class="form-group">
                        <label for="name">Full Name</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email Address</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Subject</label>
                        <input type="text" id="subject" name="subject" required>
                    </div>
                    <div class="form-group">
                        <label for="message">Your Message</label>
                        <textarea id="message" name="message" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">
                        <i class="fas fa-paper-plane"></i> Send Message
                    </button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-links">
                <a href="#home" class="footer-link">Home</a>
                <a href="#about" class="footer-link">About</a>
                <a href="#services" class="footer-link">Services</a>
                <a href="#contact" class="footer-link">Contact</a>
                <a href="mailto:aarushagrawal240411@gmail.com" class="footer-link">Email</a>
                <a href="https://instagram.com/aurexislabs" target="_blank" class="footer-link">Instagram</a>
            </div>
            <p>&copy; 2024 Aurexis Labs. Founded by <strong>Aarush Agrawal</strong>. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(15, 23, 42, 0.98)';
                navbar.style.padding = '0.8rem 0';
            } else {
                navbar.style.background = 'rgba(15, 23, 42, 0.95)';
                navbar.style.padding = '1rem 0';
            }
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Fade in animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Form submission feedback
        const form = document.querySelector('form');
        form.addEventListener('submit', function() {
            const submitBtn = this.querySelector('.submit-btn');
            submitBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Sending...';
            submitBtn.disabled = true;
        });

        // Typing effect for hero title (optional enhancement)
        const heroTitle = document.querySelector('.hero-text h1');
        if (heroTitle) {
            const text = heroTitle.textContent;
            heroTitle.textContent = '';
            let i = 0;
            function typeWriter() {
                if (i < text.length) {
                    heroTitle.textContent += text.charAt(i);
                    i++;
                    setTimeout(typeWriter, 50);
                }
            }
            setTimeout(typeWriter, 500);
        }

        // Particle background effect (performance optimized)
        function createParticle() {
            const particle = document.createElement('div');
            particle.style.cssText = `
                position: fixed;
                width: 4px;
                height: 4px;
                background: rgba(255,255,255,0.3);
                border-radius: 50%;
                pointer-events: none;
                z-index: 1;
                left: ${Math.random() * 100}vw;
                animation: floatParticle linear infinite;
            `;
            particle.animate([
                { transform: 'translateY(100vh) scale(0)', opacity: 1 },
                { transform: 'translateY(-100px) scale(1)', opacity: 0 }
            ], {
                duration: Math.random() * 3000 + 5000,
                easing: 'linear'
            }).onfinish = () => particle.remove();
            document.body.appendChild(particle);
        }

        setInterval(createParticle, 300);
    </script>
</body>
</html>
