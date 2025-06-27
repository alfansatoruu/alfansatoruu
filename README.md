<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alvan - Creative Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(-45deg, #1a1a2e, #16213e, #0f3460, #533483);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
            color: white;
            overflow-x: hidden;
            min-height: 100vh;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite alternate;
        }

        @keyframes twinkle {
            from { opacity: 0.3; }
            to { opacity: 1; }
        }

        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .header {
            text-align: center;
            margin-bottom: 3rem;
            animation: slideDown 1s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .wave-emoji {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
            font-size: 2rem;
            margin: 0 10px;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-10deg); }
        }

        .main-title {
            font-size: 4rem;
            font-weight: bold;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #ffff00, #00ffff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientText 3s ease infinite, bounce 2s ease-in-out infinite;
            margin: 20px 0;
        }

        @keyframes gradientText {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .typing-container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            margin: 2rem 0;
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: glow 3s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { box-shadow: 0 0 20px rgba(0, 255, 255, 0.3); }
            to { box-shadow: 0 0 40px rgba(0, 255, 255, 0.6); }
        }

        .typing-text {
            font-size: 1.8rem;
            font-weight: bold;
            color: #00ffff;
            text-align: center;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .coding-gif {
            text-align: center;
            margin: 3rem 0;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .coding-gif img {
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.3);
            max-width: 100%;
            height: auto;
        }

        .about-section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(15px);
            border-radius: 25px;
            padding: 3rem;
            margin: 3rem 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
            animation: slideUp 1s ease-out 0.5s both;
        }

        @keyframes slideUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .rocket {
            font-size: 2rem;
            animation: rocketFly 2s ease-in-out infinite;
        }

        @keyframes rocketFly {
            0%, 100% { transform: translateX(0) rotate(0deg); }
            25% { transform: translateX(10px) rotate(10deg); }
            75% { transform: translateX(-10px) rotate(-10deg); }
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .skill-card {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1), rgba(255, 0, 255, 0.1));
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: cardSlide 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            animation: shimmer 3s linear infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        @keyframes cardSlide {
            from {
                transform: translateX(-50px);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.4);
        }

        .skill-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        .skill-name {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
            color: #00ffff;
        }

        .skill-desc {
            font-size: 1rem;
            opacity: 0.8;
            line-height: 1.6;
        }

        .animated-arrow {
            display: inline-block;
            animation: arrowBounce 1.5s ease-in-out infinite;
            color: #ff00ff;
            font-size: 1.2rem;
            margin: 0 10px;
        }

        @keyframes arrowBounce {
            0%, 100% { transform: translateX(0); }
            50% { transform: translateX(10px); }
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin: 2rem 0;
        }

        .tech-badge {
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            color: white;
            padding: 0.5rem 1.5rem;
            border-radius: 25px;
            font-weight: bold;
            animation: techFloat 3s ease-in-out infinite;
            border: 2px solid rgba(255, 255, 255, 0.3);
            transition: transform 0.3s ease;
        }

        .tech-badge:nth-child(odd) {
            animation-delay: -1s;
        }

        .tech-badge:nth-child(even) {
            animation-delay: -2s;
        }

        @keyframes techFloat {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            33% { transform: translateY(-5px) rotate(1deg); }
            66% { transform: translateY(5px) rotate(-1deg); }
        }

        .tech-badge:hover {
            transform: scale(1.1) rotate(5deg);
        }

        .portfolio-section {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 4rem 3rem;
            margin: 4rem 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
            animation: slideUp 1s ease-out 0.8s both;
        }

        .portfolio-icon {
            font-size: 2.5rem;
            animation: briefcaseBounce 2s ease-in-out infinite;
        }

        @keyframes briefcaseBounce {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            25% { transform: translateY(-5px) rotate(5deg); }
            75% { transform: translateY(5px) rotate(-5deg); }
        }

        .portfolio-description {
            font-size: 1.2rem;
            line-height: 1.8;
            text-align: center;
            margin: 2rem 0 4rem 0;
            opacity: 0.9;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
            gap: 3rem;
            margin: 3rem 0;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.05), rgba(255, 0, 255, 0.05));
            border-radius: 25px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.15);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            position: relative;
            animation: projectSlideIn 1s ease-out;
            backdrop-filter: blur(10px);
        }

        .project-card:nth-child(odd) {
            animation-delay: 0.2s;
        }

        .project-card:nth-child(even) {
            animation-delay: 0.4s;
        }

        @keyframes projectSlideIn {
            from {
                transform: translateY(50px) scale(0.9);
                opacity: 0;
            }
            to {
                transform: translateY(0) scale(1);
                opacity: 1;
            }
        }

        .project-card:hover {
            transform: translateY(-15px) scale(1.03);
            box-shadow: 0 25px 50px rgba(0, 255, 255, 0.3);
            border-color: rgba(0, 255, 255, 0.4);
        }

        .project-image {
            position: relative;
            width: 100%;
            height: 250px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s ease;
            border-radius: 20px 20px 0 0;
        }

        .project-card:hover .project-image img {
            transform: scale(1.1);
        }

        .project-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(0, 0, 0, 0.7), rgba(0, 255, 255, 0.3));
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 1.5rem;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover .project-overlay {
            opacity: 1;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-tag {
            background: rgba(0, 255, 255, 0.8);
            color: #000;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: bold;
            animation: tagFloat 2s ease-in-out infinite;
        }

        .tech-tag:nth-child(2) {
            animation-delay: -0.5s;
        }

        .tech-tag:nth-child(3) {
            animation-delay: -1s;
        }

        @keyframes tagFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-3px); }
        }

        .project-buttons {
            display: flex;
            gap: 1rem;
            align-self: flex-end;
        }

        .btn-demo, .btn-code {
            padding: 0.8rem 1.5rem;
            border: none;
            border-radius: 25px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .btn-demo {
            background: linear-gradient(45deg, #00ffff, #0080ff);
            color: #000;
        }

        .btn-code {
            background: linear-gradient(45deg, #ff00ff, #ff0080);
            color: #fff;
        }

        .btn-demo:hover, .btn-code:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .project-content {
            padding: 2rem;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 1rem;
            color: #00ffff;
            animation: titleGlow 3s ease-in-out infinite alternate;
        }

        @keyframes titleGlow {
            from { text-shadow: 0 0 5px #00ffff; }
            to { text-shadow: 0 0 15px #00ffff, 0 0 25px #00ffff; }
        }

        .project-description {
            font-size: 1rem;
            line-height: 1.6;
            opacity: 0.85;
            margin-bottom: 1.5rem;
        }

        .project-stats {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 0.4rem 1rem;
            border-radius: 20px;
            font-size: 0.85rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: statPulse 3s ease-in-out infinite;
        }

        .stat-item:nth-child(2) {
            animation-delay: -1.5s;
        }

        @keyframes statPulse {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; }
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #ffff00, #00ffff);
            z-index: -1;
            border-radius: 27px;
            opacity: 0;
            transition: opacity 0.3s ease;
            animation: borderGlow 3s linear infinite;
        }

        .project-card:hover::before {
            opacity: 0.7;
        }

        @keyframes borderGlow {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @media (max-width: 768px) {
            .projects-grid {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
            
            .project-card {
                min-width: unset;
            }
            
            .portfolio-section {
                padding: 2rem 1.5rem;
            }
            
            .project-buttons {
                flex-direction: column;
                gap: 0.5rem;
            }
        }

        .passion-text {
            font-size: 1.2rem;
            line-height: 1.8;
            text-align: center;
            margin: 2rem 0;
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .highlight {
            color: #00ffff;
            font-weight: bold;
            animation: textGlow 2s ease-in-out infinite alternate;
        }

        @keyframes textGlow {
            from { text-shadow: 0 0 5px #00ffff; }
            to { text-shadow: 0 0 20px #00ffff, 0 0 30px #00ffff; }
        }

        @media (max-width: 768px) {
            .main-title {
                font-size: 2.5rem;
            }
            
            .typing-text {
                font-size: 1.2rem;
            }
            
            .container {
                padding: 1rem;
            }
            
            .about-section {
                padding: 2rem;
            }
        }
    </style>
</head>
<body>
    <div class="stars"></div>
    
    <div class="container">
        <header class="header">
            <h1 class="main-title">
                <span class="wave-emoji">👋</span>
                Hi, I'm Alvan
                <span class="wave-emoji">👋</span>
            </h1>
            
            <div class="typing-container">
                <div class="typing-text" id="typingText"></div>
            </div>
            
            <div class="coding-gif">
                <img src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" width="350" alt="Coding Animation" />
            </div>
        </header>

        <section class="about-section">
            <h2 class="section-title">
                <span class="rocket">🚀</span>
                About Me
                <span class="animated-arrow">→</span>
            </h2>
            
            <div class="passion-text">
                Saya adalah seorang <span class="highlight">Creative Developer</span> yang passionate dalam menciptakan 
                <span class="highlight">pengalaman digital yang menakjubkan</span>. Dengan keahlian di berbagai teknologi modern, 
                saya selalu berusaha menggabungkan <span class="highlight">kreativitas</span> dan <span class="highlight">teknologi</span> 
                untuk menghasilkan solusi yang inovatif dan user-friendly.
            </div>

            <div class="tech-stack">
                <span class="tech-badge">Flutter 💙</span>
                <span class="tech-badge">React ⚛️</span>
                <span class="tech-badge">UI/UX Design 🎨</span>
                <span class="tech-badge">Data Analysis 📊</span>
                <span class="tech-badge">Python 🐍</span>
                <span class="tech-badge">JavaScript ⚡</span>
                <span class="tech-badge">Google Colab 📓</span>
            </div>

            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-icon">📱</div>
                    <div class="skill-name">Mobile Development</div>
                    <div class="skill-desc">
                        Membuat aplikasi mobile yang responsif dan intuitif menggunakan Flutter 
                        dengan performa tinggi dan design yang memukau.
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-icon">💻</div>
                    <div class="skill-name">Web Development</div>
                    <div class="skill-desc">
                        Mengembangkan web applications modern dengan React, menciptakan 
                        user experience yang engaging dan interactive.
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-icon">🎨</div>
                    <div class="skill-name">UI/UX Design</div>
                    <div class="skill-desc">
                        Merancang interface yang beautiful dan functional, dengan fokus pada 
                        user-centered design dan accessibility.
                    </div>
                </div>

                <div class="skill-card">
                    <div class="skill-icon">📈</div>
                    <div class="skill-name">Data Analysis</div>
                    <div class="skill-desc">
                        Menganalisis data kompleks menggunakan Python dan Google Colab untuk 
                        menghasilkan insights yang valuable dan actionable.
                    </div>
                </div>
            </div>

            <div class="passion-text">
                <span class="highlight">Passion saya</span> adalah menciptakan teknologi yang tidak hanya functional, 
                tetapi juga <span class="highlight">memberikan impact positif</span> bagi penggunanya. 
                Setiap project adalah opportunity untuk <span class="highlight">belajar, berinovasi, dan berkolaborasi</span> 
                dalam menciptakan masa depan digital yang lebih baik.
                <span class="animated-arrow">🌟</span>
            </div>
        </section>

        <section class="portfolio-section">
            <h2 class="section-title">
                <span class="portfolio-icon">💼</span>
                My Portfolio
                <span class="animated-arrow">→</span>
            </h2>
            
            <div class="portfolio-description">
                Berikut adalah koleksi project terbaik yang telah saya kerjakan, 
                mulai dari <span class="highlight">mobile apps</span>, <span class="highlight">web applications</span>, 
                hingga <span class="highlight">data analysis projects</span>. Klik pada setiap project untuk melihat detail lengkapnya!
            </div>

            <div class="projects-grid">
                <div class="project-card" data-url="https://github.com/alvan/project1">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/FF6B6B/FFFFFF?text=E-Commerce+App" alt="E-Commerce Mobile App" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">Flutter</span>
                                <span class="tech-tag">Firebase</span>
                                <span class="tech-tag">UI/UX</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">E-Commerce Mobile App</h3>
                        <p class="project-description">
                            Aplikasi mobile e-commerce yang lengkap dengan fitur keranjang belanja, 
                            payment gateway, dan sistem notifikasi real-time.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">📱 Mobile App</span>
                            <span class="stat-item">⭐ 4.8 Rating</span>
                        </div>
                    </div>
                </div>

                <div class="project-card" data-url="https://github.com/alvan/project2">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/4ECDC4/FFFFFF?text=Dashboard+Analytics" alt="Data Analytics Dashboard" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">React</span>
                                <span class="tech-tag">Chart.js</span>
                                <span class="tech-tag">Python</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Data Analytics Dashboard</h3>
                        <p class="project-description">
                            Dashboard interaktif untuk visualisasi data real-time dengan 
                            berbagai chart dan filtering yang powerful.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">📊 Analytics</span>
                            <span class="stat-item">🔥 Real-time</span>
                        </div>
                    </div>
                </div>

                <div class="project-card" data-url="https://github.com/alvan/project3">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/45B7D1/FFFFFF?text=Task+Management" alt="Task Management App" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">Flutter</span>
                                <span class="tech-tag">SQLite</span>
                                <span class="tech-tag">Provider</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Task Management App</h3>
                        <p class="project-description">
                            Aplikasi manajemen tugas dengan fitur drag & drop, reminder, 
                            dan sinkronisasi cloud untuk produktivitas maksimal.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">✅ Productivity</span>
                            <span class="stat-item">☁️ Cloud Sync</span>
                        </div>
                    </div>
                </div>

                <div class="project-card" data-url="https://github.com/alvan/project4">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/F7B731/FFFFFF?text=Weather+App" alt="Weather Forecast App" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">React</span>
                                <span class="tech-tag">OpenWeather API</span>
                                <span class="tech-tag">Geolocation</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Weather Forecast App</h3>
                        <p class="project-description">
                            Aplikasi cuaca yang akurat dengan prediksi 7 hari, 
                            animasi weather yang menarik, dan location-based forecast.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">🌤️ Weather</span>
                            <span class="stat-item">📍 Location-based</span>
                        </div>
                    </div>
                </div>

                <div class="project-card" data-url="https://github.com/alvan/project5">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/5D4E75/FFFFFF?text=Chat+Application" alt="Real-time Chat App" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">Flutter</span>
                                <span class="tech-tag">Socket.IO</span>
                                <span class="tech-tag">Node.js</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Real-time Chat App</h3>
                        <p class="project-description">
                            Aplikasi chat real-time dengan fitur grup chat, file sharing, 
                            emoji reactions, dan end-to-end encryption.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">💬 Real-time</span>
                            <span class="stat-item">🔒 Encrypted</span>
                        </div>
                    </div>
                </div>

                <div class="project-card" data-url="https://github.com/alvan/project6">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/26A69A/FFFFFF?text=ML+Classifier" alt="Machine Learning Classifier" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">Python</span>
                                <span class="tech-tag">TensorFlow</span>
                                <span class="tech-tag">Jupyter</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">ML Image Classifier</h3>
                        <p class="project-description">
                            Model machine learning untuk klasifikasi gambar dengan 
                            akurasi tinggi menggunakan deep learning dan CNN.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">🤖 AI/ML</span>
                            <span class="stat-item">🎯 95% Accuracy</span>
                        </div>
                    </div>
                </div>

                <div class="project-card" data-url="https://github.com/alvan/project7">
                    <div class="project-image">
                        <img src="https://via.placeholder.com/400x250/EE5A24/FFFFFF?text=Portfolio+Website" alt="Portfolio Website" />
                        <div class="project-overlay">
                            <div class="project-tech">
                                <span class="tech-tag">React</span>
                                <span class="tech-tag">Three.js</span>
                                <span class="tech-tag">GSAP</span>
                            </div>
                            <div class="project-buttons">
                                <button class="btn-demo">🚀 Live Demo</button>
                                <button class="btn-code">💻 Source Code</button>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">3D Portfolio Website</h3>
                        <p class="project-description">
                            Website portfolio interaktif dengan elemen 3D, 
                            animasi smooth, dan design yang futuristik.
                        </p>
                        <div class="project-stats">
                            <span class="stat-item">🎨 3D Design</span>
                            <span class="stat-item">✨ Interactive</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Create animated stars
        function createStars() {
            const starsContainer = document.querySelector('.stars');
            const starCount = 50;

            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                star.style.animationDuration = (Math.random() * 3 + 2) + 's';
                starsContainer.appendChild(star);
            }
        }

        // Typing animation
        function typeWriter() {
            const texts = [
                'Creative Developer 💡',
                'Flutter Enthusiast 📱',
                'React Developer ⚛️',
                'UI/UX Designer 🎨',
                'Data Analysis Expert 📊',
                'Tech Innovation Lover 🚀'
            ];
            
            let textIndex = 0;
            let charIndex = 0;
            let isDeleting = false;
            const typingElement = document.getElementById('typingText');
            
            function type() {
                const currentText = texts[textIndex];
                
                if (isDeleting) {
                    typingElement.textContent = currentText.substring(0, charIndex - 1);
                    charIndex--;
                } else {
                    typingElement.textContent = currentText.substring(0, charIndex + 1);
                    charIndex++;
                }
                
                let typeSpeed = isDeleting ? 100 : 150;
                
                if (!isDeleting && charIndex === currentText.length) {
                    typeSpeed = 2000;
                    isDeleting = true;
                } else if (isDeleting && charIndex === 0) {
                    isDeleting = false;
                    textIndex = (textIndex + 1) % texts.length;
                    typeSpeed = 500;
                }
                
                setTimeout(type, typeSpeed);
            }
            
            type();
        }

        // Parallax scroll effect
        function parallaxScroll() {
            window.addEventListener('scroll', () => {
                const scrolled = window.pageYOffset;
                const parallaxElements = document.querySelectorAll('.skill-card');
                
                parallaxElements.forEach((element, index) => {
                    const speed = 0.5 + (index * 0.1);
                    element.style.transform = `translateY(${scrolled * speed * 0.1}px)`;
                });
            });
        }

        // Initialize animations
        document.addEventListener('DOMContentLoaded', () => {
            createStars();
            typeWriter();
            parallaxScroll();
            initializeProjectCards();
        });

        // Add mouse move effect
        document.addEventListener('mousemove', (e) => {
            const skillCards = document.querySelectorAll('.skill-card');
            const mouseX = e.clientX / window.innerWidth;
            const mouseY = e.clientY / window.innerHeight;

            skillCards.forEach((card, index) => {
                const xOffset = (mouseX - 0.5) * 20;
                const yOffset = (mouseY - 0.5) * 20;
                card.style.transform += ` translate(${xOffset * (index + 1) * 0.1}px, ${yOffset * (index + 1) * 0.1}px)`;
            });
        });

        // Project card functionality
        function initializeProjectCards() {
            const projectCards = document.querySelectorAll('.project-card');
            
            projectCards.forEach(card => {
                card.addEventListener('click', () => {
                    const url = card.getAttribute('data-url');
                    if (url) {
                        window.open(url, '_blank');
                    }
                });

                // Add ripple effect on click
                card.addEventListener('click', createRipple);
                
                // Add tilt effect on mouse move
                card.addEventListener('mousemove', (e) => {
                    const rect = card.getBoundingClientRect();
                    const x = e.clientX - rect.left;
                    const y = e.clientY - rect.top;
                    
                    const centerX = rect.width / 2;
                    const centerY = rect.height / 2;
                    
                    const rotateX = (y - centerY) / 10;
                    const rotateY = (centerX - x) / 10;
                    
                    card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) translateZ(0)`;
                });
                
                card.addEventListener('mouseleave', () => {
                    card.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) translateZ(0)';
                });
            });
        }

        // Create ripple effect
        function createRipple(e) {
            const card = e.currentTarget;
            const ripple = document.createElement('div');
            const rect = card.getBoundingClientRect();
            const size = Math.max(rect.width, rect.height);
            const x = e.clientX - rect.left - size / 2;
            const y = e.clientY - rect.top - size / 2;
            
            ripple.style.cssText = `
                position: absolute;
                width: ${size}px;
                height: ${size}px;
                left: ${x}px;
                top: ${y}px;
                background: radial-gradient(circle, rgba(0, 255, 255, 0.3) 0%, transparent 70%);
                border-radius: 50%;
                pointer-events: none;
                animation: rippleEffect 0.6s ease-out;
                z-index: 10;
            `;
            
            card.style.position = 'relative';
            card.appendChild(ripple);
            
            setTimeout(() => {
                ripple.remove();
            }, 600);
        }

        // Add ripple animation to CSS dynamically
        const rippleCSS = `
            @keyframes rippleEffect {
                0% {
                    transform: scale(0);
                    opacity: 1;
                }
                100% {
                    transform: scale(2);
                    opacity: 0;
                }
            }
        `;
        const style = document.createElement('style');
        style.textContent = rippleCSS;
        document.head.appendChild(style);

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationPlayState = 'running';
                }
            });
        }, observerOptions);

        // Observe project cards for scroll animations
        document.addEventListener('DOMContentLoaded', () => {
            const projectCards = document.querySelectorAll('.project-card');
            projectCards.forEach(card => {
                observer.observe(card);
            });
        });
    </script>
</body>
</html>
