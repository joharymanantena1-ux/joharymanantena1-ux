<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Johary Manantena - Développeur Fullstack</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto+Mono:wght@300;400;500&display=swap">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #4A90E2;
            --secondary: #8E44AD;
            --accent: #D32F2F;
            --dark: #121212;
            --dark-secondary: #1E1E1E;
            --light: #F5F7FA;
            --gray: #8A8A8A;
            --success: #2ECC71;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* ================= HEADER ================= */
        header {
            padding: 2rem 0;
            text-align: center;
            background: linear-gradient(135deg, rgba(26, 26, 46, 0.95) 0%, rgba(30, 30, 46, 0.95) 100%);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(74, 144, 226, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(142, 68, 173, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(211, 47, 47, 0.1) 0%, transparent 50%);
            z-index: 0;
        }
        
        .header-content {
            position: relative;
            z-index: 1;
        }
        
        .typing-container {
            min-height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
        }
        
        .typing-text {
            font-family: 'Roboto Mono', monospace;
            font-size: 2rem;
            font-weight: 500;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-align: center;
        }
        
        .badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
            margin-top: 1.5rem;
        }
        
        .badge {
            background: rgba(255, 255, 255, 0.1);
            padding: 10px 20px;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 500;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }
        
        .badge:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
        }
        
        .badge.fullstack {
            background: linear-gradient(90deg, rgba(74, 144, 226, 0.2), rgba(74, 144, 226, 0.4));
        }
        
        .badge.student {
            background: linear-gradient(90deg, rgba(142, 68, 173, 0.2), rgba(142, 68, 173, 0.4));
        }
        
        .badge.madagascar {
            background: linear-gradient(90deg, rgba(211, 47, 47, 0.2), rgba(211, 47, 47, 0.4));
        }
        
        hr {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            margin: 3rem auto;
            width: 80%;
        }
        
        /* ================= SECTIONS ================= */
        section {
            padding: 4rem 0;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.2rem;
            margin-bottom: 3rem;
            position: relative;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 2px;
        }
        
        /* ================= STACK ================= */
        .stack-category {
            margin-bottom: 3rem;
        }
        
        .stack-title {
            font-size: 1.3rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
            text-align: center;
        }
        
        .stack-icons {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }
        
        .stack-icon {
            background-color: var(--dark-secondary);
            border-radius: 10px;
            padding: 15px;
            width: 90px;
            height: 90px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .stack-icon:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            border-color: var(--primary);
        }
        
        .stack-icon i {
            font-size: 2rem;
            margin-bottom: 10px;
        }
        
        .stack-icon span {
            font-size: 0.8rem;
            text-align: center;
        }
        
        /* ================= STATS ================= */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 3rem;
        }
        
        .stats-card {
            background-color: var(--dark-secondary);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }
        
        .stats-card:hover {
            transform: translateY(-10px);
        }
        
        .stats-card h3 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.2rem;
        }
        
        .chart-container {
            position: relative;
            height: 250px;
            width: 100%;
        }
        
        /* ================= ACTIVITY GRAPH ================= */
        .activity-container {
            background-color: var(--dark-secondary);
            border-radius: 15px;
            padding: 25px;
            margin-top: 2rem;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        /* ================= CONTACT ================= */
        .contact-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin-top: 2rem;
        }
        
        .contact-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(74, 144, 226, 0.3);
        }
        
        .contact-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(74, 144, 226, 0.4);
        }
        
        /* ================= FOOTER ================= */
        footer {
            text-align: center;
            padding: 2rem 0;
            background-color: rgba(0, 0, 0, 0.3);
            margin-top: 4rem;
            font-size: 0.9rem;
            color: var(--gray);
        }
        
        /* ================= RESPONSIVE ================= */
        @media (max-width: 768px) {
            .typing-text {
                font-size: 1.5rem;
            }
            
            .badges {
                flex-direction: column;
                align-items: center;
            }
            
            .badge {
                width: 80%;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .stack-icon {
                width: 80px;
                height: 80px;
            }
            
            .stats-container {
                grid-template-columns: 1fr;
            }
            
            .contact-btn {
                width: 100%;
                justify-content: center;
            }
        }
        
        @media (max-width: 480px) {
            .typing-text {
                font-size: 1.2rem;
            }
            
            .stack-icons {
                gap: 10px;
            }
            
            .stack-icon {
                width: 70px;
                height: 70px;
                padding: 10px;
            }
            
            .stack-icon i {
                font-size: 1.5rem;
            }
        }
        
        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .fade-in {
            animation: fadeIn 0.8s ease forwards;
        }
        
        .delay-1 { animation-delay: 0.2s; }
        .delay-2 { animation-delay: 0.4s; }
        .delay-3 { animation-delay: 0.6s; }
        
        /* Theme toggle */
        .theme-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 1000;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .theme-toggle i {
            font-size: 1.2rem;
            color: var(--light);
        }
        
        /* Light theme */
        body.light-theme {
            background-color: var(--light);
            color: var(--dark);
        }
        
        body.light-theme .stats-card,
        body.light-theme .activity-container,
        body.light-theme .stack-icon,
        body.light-theme .badge {
            background-color: white;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            color: var(--dark);
        }
        
        body.light-theme header {
            background: linear-gradient(135deg, rgba(245, 247, 250, 0.95) 0%, rgba(230, 233, 240, 0.95) 100%);
        }
        
        body.light-theme header::before {
            background: 
                radial-gradient(circle at 20% 50%, rgba(74, 144, 226, 0.05) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(142, 68, 173, 0.05) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(211, 47, 47, 0.05) 0%, transparent 50%);
        }
        
        body.light-theme .theme-toggle {
            background: rgba(0, 0, 0, 0.05);
        }
        
        body.light-theme footer {
            background-color: rgba(0, 0, 0, 0.05);
        }
    </style>
</head>
<body>
    <!-- Theme Toggle -->
    <div class="theme-toggle" id="themeToggle">
        <i class="fas fa-moon"></i>
    </div>
    
    <!-- ================= HEADER ================= -->
    <header>
        <div class="container header-content">
            <div class="typing-container">
                <h1 class="typing-text" id="typingText"></h1>
            </div>
            
            <div class="badges">
                <div class="badge fullstack fade-in">Développeur Web Fullstack</div>
                <div class="badge student fade-in delay-1">Étudiant en Sciences Informatiques</div>
                <div class="badge madagascar fade-in delay-2">IT Student from Madagascar</div>
            </div>
        </div>
    </header>
    
    <hr>
    
    <div class="container">
        <!-- ================= STACK ================= -->
        <section id="stack">
            <h2 class="section-title">Stack Technique</h2>
            
            <div class="stack-category">
                <h3 class="stack-title">Langages de programmation</h3>
                <div class="stack-icons">
                    <div class="stack-icon">
                        <i class="fab fa-js-square" style="color: #F7DF1E;"></i>
                        <span>JavaScript</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-typescript" style="color: #3178C6;"></i>
                        <span>TypeScript</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-java" style="color: #007396;"></i>
                        <span>Java</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-php" style="color: #777BB4;"></i>
                        <span>PHP</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-python" style="color: #3776AB;"></i>
                        <span>Python</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-code" style="color: #00599C;"></i>
                        <span>C++</span>
                    </div>
                </div>
            </div>
            
            <div class="stack-category">
                <h3 class="stack-title">Frameworks & Frontend</h3>
                <div class="stack-icons">
                    <div class="stack-icon">
                        <i class="fab fa-react" style="color: #61DAFB;"></i>
                        <span>React</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-bolt" style="color: #000000;"></i>
                        <span>Next.js</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-vuejs" style="color: #4FC08D;"></i>
                        <span>Vue.js</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-angular" style="color: #DD0031;"></i>
                        <span>Angular</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-html5" style="color: #E34F26;"></i>
                        <span>HTML5</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-css3-alt" style="color: #1572B6;"></i>
                        <span>CSS3</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-sass" style="color: #CC6699;"></i>
                        <span>Sass</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-wind" style="color: #38B2AC;"></i>
                        <span>Tailwind</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-flutter" style="color: #02569B;"></i>
                        <span>Flutter</span>
                    </div>
                </div>
            </div>
            
            <div class="stack-category">
                <h3 class="stack-title">Backend & Bases de données</h3>
                <div class="stack-icons">
                    <div class="stack-icon">
                        <i class="fab fa-node-js" style="color: #339933;"></i>
                        <span>Node.js</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-server" style="color: #68A063;"></i>
                        <span>Express</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-laravel" style="color: #FF2D20;"></i>
                        <span>Laravel</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-python" style="color: #092E20;"></i>
                        <span>Django</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-database" style="color: #4479A1;"></i>
                        <span>MySQL</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-leaf" style="color: #47A248;"></i>
                        <span>MongoDB</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-database" style="color: #336791;"></i>
                        <span>PostgreSQL</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-fire" style="color: #FFCA28;"></i>
                        <span>Firebase</span>
                    </div>
                </div>
            </div>
            
            <div class="stack-category">
                <h3 class="stack-title">Outils & Technologies</h3>
                <div class="stack-icons">
                    <div class="stack-icon">
                        <i class="fab fa-git-alt" style="color: #F05032;"></i>
                        <span>Git</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-github" style="color: #181717;"></i>
                        <span>GitHub</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-gitlab" style="color: #FC6D26;"></i>
                        <span>GitLab</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-docker" style="color: #2496ED;"></i>
                        <span>Docker</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-aws" style="color: #232F3E;"></i>
                        <span>AWS</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-microsoft" style="color: #0078D4;"></i>
                        <span>Azure</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fab fa-figma" style="color: #F24E1E;"></i>
                        <span>Figma</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-code" style="color: #FF6C37;"></i>
                        <span>Postman</span>
                    </div>
                    <div class="stack-icon">
                        <i class="fas fa-code" style="color: #007ACC;"></i>
                        <span>VS Code</span>
                    </div>
                </div>
            </div>
        </section>
        
        <hr>
        
        <!-- ================= STATS ================= -->
        <section id="stats">
            <h2 class="section-title">Statistiques GitHub</h2>
            
            <div class="stats-container">
                <div class="stats-card fade-in">
                    <h3>Statistiques GitHub</h3>
                    <div class="chart-container">
                        <canvas id="githubStatsChart"></canvas>
                    </div>
                </div>
                
                <div class="stats-card fade-in delay-1">
                    <h3>Langages les plus utilisés</h3>
                    <div class="chart-container">
                        <canvas id="languagesChart"></canvas>
                    </div>
                </div>
            </div>
            
            <div class="stats-card fade-in delay-2">
                <h3>Activité des contributions</h3>
                <div class="chart-container">
                    <canvas id="contributionChart"></canvas>
                </div>
            </div>
        </section>
        
        <hr>
        
        <!-- ================= CONTACT ================= -->
        <section id="contact">
            <h2 class="section-title">Contact</h2>
            
            <div class="contact-container">
                <a href="mailto:andrianmanantena@gmail.com" class="contact-btn fade-in">
                    <i class="fas fa-envelope"></i> Email
                </a>
                <a href="https://linkedin.com/in/johary-manantena" target="_blank" class="contact-btn fade-in delay-1">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://github.com/joharymanantena1-ux" target="_blank" class="contact-btn fade-in delay-2">
                    <i class="fab fa-github"></i> GitHub
                </a>
            </div>
        </section>
    </div>
    
    <!-- ================= FOOTER ================= -->
    <footer>
        <div class="container">
            <p>© 2026 Johary Manantena - Développeur Fullstack & Étudiant en Sciences Informatiques</p>
        </div>
    </footer>
    
    <script>
        // Typing effect
        const typingText = document.getElementById('typingText');
        const texts = [
            "Johary Manantena",
            "Développeur Web Fullstack",
            "Étudiant en Sciences Informatiques",
            "Web & Design",
            "IT Student from Madagascar"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        let typingSpeed = 100;
        
        function typeText() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                // Deleting text
                typingText.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
                typingSpeed = 50;
            } else {
                // Typing text
                typingText.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
                typingSpeed = 100;
            }
            
            // If text is fully typed
            if (!isDeleting && charIndex === currentText.length) {
                isDeleting = true;
                typingSpeed = 1500; // Pause at the end
            }
            // If text is fully deleted
            else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                typingSpeed = 500; // Pause before typing next text
            }
            
            setTimeout(typeText, typingSpeed);
        }
        
        // Start typing effect after page loads
        document.addEventListener('DOMContentLoaded', () => {
            setTimeout(typeText, 1000);
            
            // Initialize charts
            initCharts();
            
            // Initialize theme toggle
            initThemeToggle();
        });
        
        // Initialize Charts
        function initCharts() {
            // GitHub Stats Chart
            const githubStatsCtx = document.getElementById('githubStatsChart').getContext('2d');
            const githubStatsChart = new Chart(githubStatsCtx, {
                type: 'bar',
                data: {
                    labels: ['Repositories', 'Stars', 'Followers', 'Following', 'Contributions'],
                    datasets: [{
                        label: 'GitHub Stats',
                        data: [42, 128, 56, 34, 389],
                        backgroundColor: [
                            'rgba(74, 144, 226, 0.8)',
                            'rgba(142, 68, 173, 0.8)',
                            'rgba(211, 47, 47, 0.8)',
                            'rgba(46, 204, 113, 0.8)',
                            'rgba(241, 196, 15, 0.8)'
                        ],
                        borderColor: [
                            'rgba(74, 144, 226, 1)',
                            'rgba(142, 68, 173, 1)',
                            'rgba(211, 47, 47, 1)',
                            'rgba(46, 204, 113, 1)',
                            'rgba(241, 196, 15, 1)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            },
                            grid: {
                                color: document.body.classList.contains('light-theme') ? 'rgba(0,0,0,0.05)' : 'rgba(255,255,255,0.1)'
                            }
                        },
                        x: {
                            ticks: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            },
                            grid: {
                                color: document.body.classList.contains('light-theme') ? 'rgba(0,0,0,0.05)' : 'rgba(255,255,255,0.1)'
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            labels: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            }
                        }
                    }
                }
            });
            
            // Languages Chart
            const languagesCtx = document.getElementById('languagesChart').getContext('2d');
            const languagesChart = new Chart(languagesCtx, {
                type: 'doughnut',
                data: {
                    labels: ['JavaScript', 'TypeScript', 'Java', 'PHP', 'Python', 'CSS/HTML', 'Autres'],
                    datasets: [{
                        data: [35, 20, 15, 10, 8, 7, 5],
                        backgroundColor: [
                            'rgba(247, 223, 30, 0.8)',
                            'rgba(49, 120, 198, 0.8)',
                            'rgba(0, 115, 150, 0.8)',
                            'rgba(119, 123, 180, 0.8)',
                            'rgba(55, 118, 171, 0.8)',
                            'rgba(227, 79, 38, 0.8)',
                            'rgba(142, 68, 173, 0.8)'
                        ],
                        borderColor: [
                            'rgba(247, 223, 30, 1)',
                            'rgba(49, 120, 198, 1)',
                            'rgba(0, 115, 150, 1)',
                            'rgba(119, 123, 180, 1)',
                            'rgba(55, 118, 171, 1)',
                            'rgba(227, 79, 38, 1)',
                            'rgba(142, 68, 173, 1)'
                        ],
                        borderWidth: 1
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'right',
                            labels: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            }
                        }
                    }
                }
            });
            
            // Contribution Chart
            const contributionCtx = document.getElementById('contributionChart').getContext('2d');
            const contributionChart = new Chart(contributionCtx, {
                type: 'line',
                data: {
                    labels: ['Jan', 'Fév', 'Mar', 'Avr', 'Mai', 'Juin', 'Juil', 'Août', 'Sept', 'Oct', 'Nov', 'Déc'],
                    datasets: [{
                        label: 'Contributions mensuelles',
                        data: [65, 78, 90, 81, 86, 95, 120, 110, 105, 98, 115, 130],
                        borderColor: 'rgba(74, 144, 226, 1)',
                        backgroundColor: 'rgba(74, 144, 226, 0.1)',
                        borderWidth: 3,
                        fill: true,
                        tension: 0.4
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        y: {
                            beginAtZero: true,
                            ticks: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            },
                            grid: {
                                color: document.body.classList.contains('light-theme') ? 'rgba(0,0,0,0.05)' : 'rgba(255,255,255,0.1)'
                            }
                        },
                        x: {
                            ticks: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            },
                            grid: {
                                color: document.body.classList.contains('light-theme') ? 'rgba(0,0,0,0.05)' : 'rgba(255,255,255,0.1)'
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            labels: {
                                color: document.body.classList.contains('light-theme') ? '#333' : '#FFF'
                            }
                        }
                    }
                }
            });
            
            // Update chart colors when theme changes
            window.updateChartColors = function() {
                const isLightTheme = document.body.classList.contains('light-theme');
                const textColor = isLightTheme ? '#333' : '#FFF';
                const gridColor = isLightTheme ? 'rgba(0,0,0,0.05)' : 'rgba(255,255,255,0.1)';
                
                // Update GitHub Stats Chart
                githubStatsChart.options.scales.x.ticks.color = textColor;
                githubStatsChart.options.scales.x.grid.color = gridColor;
                githubStatsChart.options.scales.y.ticks.color = textColor;
                githubStatsChart.options.scales.y.grid.color = gridColor;
                githubStatsChart.options.plugins.legend.labels.color = textColor;
                githubStatsChart.update();
                
                // Update Languages Chart
                languagesChart.options.plugins.legend.labels.color = textColor;
                languagesChart.update();
                
                // Update Contribution Chart
                contributionChart.options.scales.x.ticks.color = textColor;
                contributionChart.options.scales.x.grid.color = gridColor;
                contributionChart.options.scales.y.ticks.color = textColor;
                contributionChart.options.scales.y.grid.color = gridColor;
                contributionChart.options.plugins.legend.labels.color = textColor;
                contributionChart.update();
            };
        }
        
        // Theme Toggle
        function initThemeToggle() {
            const themeToggle = document.getElementById('themeToggle');
            const icon = themeToggle.querySelector('i');
            
            // Check for saved theme or default to dark
            const savedTheme = localStorage.getItem('theme') || 'dark';
            if (savedTheme === 'light') {
                document.body.classList.add('light-theme');
                icon.classList.remove('fa-moon');
                icon.classList.add('fa-sun');
            }
            
            themeToggle.addEventListener('click', () => {
                document.body.classList.toggle('light-theme');
                
                if (document.body.classList.contains('light-theme')) {
                    icon.classList.remove('fa-moon');
                    icon.classList.add('fa-sun');
                    localStorage.setItem('theme', 'light');
                } else {
                    icon.classList.remove('fa-sun');
                    icon.classList.add('fa-moon');
                    localStorage.setItem('theme', 'dark');
                }
                
                // Update chart colors
                if (typeof updateChartColors === 'function') {
                    updateChartColors();
                }
            });
        }
        
        // Fade in animation on scroll
        const fadeElements = document.querySelectorAll('.fade-in, .delay-1, .delay-2');
        
        const fadeInOnScroll = () => {
            fadeElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                
                if (elementTop < window.innerHeight - elementVisible) {
                    element.style.opacity = "1";
                    element.style.transform = "translateY(0)";
                }
            });
        };
        
        // Set initial state for fade elements
        fadeElements.forEach(element => {
            element.style.opacity = "0";
            element.style.transform = "translateY(20px)";
            element.style.transition = "opacity 0.8s ease, transform 0.8s ease";
        });
        
        // Check on scroll and on load
        window.addEventListener('scroll', fadeInOnScroll);
        window.addEventListener('load', fadeInOnScroll);
        fadeInOnScroll(); // Initial check
    </script>
</body>
</html>
