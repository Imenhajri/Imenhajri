<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Imen HAJRI - GitHub Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        :root {
            --primary: #6e44ff;
            --secondary: #00ADEF;
            --accent: #ff44a8;
            --dark: #0f0f23;
            --darker: #0a0a18;
            --card-bg: rgba(30, 30, 46, 0.8);
            --light: #ffffff;
            --gradient: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: var(--dark);
            color: var(--light);
            overflow-x: hidden;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            padding: 60px 0 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .typing-container {
            min-height: 120px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 30px;
        }
        
        .typing-text {
            font-size: 2.2rem;
            font-weight: bold;
            text-align: center;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
        }
        
        .typing-text::after {
            content: '|';
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }
        
        .profile-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
            margin-bottom: 40px;
        }
        
        @media (max-width: 968px) {
            .profile-section {
                grid-template-columns: 1fr;
            }
        }
        
        .profile-info {
            text-align: left;
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid var(--primary);
            margin-bottom: 20px;
            background: var(--gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            color: white;
            box-shadow: 0 10px 30px rgba(110, 68, 255, 0.4);
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .tagline {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }
        
        .username {
            font-size: 1.2rem;
            color: var(--light);
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .username i {
            color: var(--accent);
        }
        
        .coding-gif {
            text-align: center;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .coding-gif img {
            max-width: 100%;
            border-radius: 15px;
            transition: transform 0.3s;
        }
        
        .coding-gif:hover img {
            transform: scale(1.05);
        }
        
        /* Banner */
        .banner {
            background: var(--gradient);
            border-radius: 15px;
            padding: 25px;
            margin: 30px 0;
            text-align: center;
            font-size: 1.8rem;
            font-weight: bold;
            color: white;
            box-shadow: 0 10px 30px rgba(110, 68, 255, 0.3);
            animation: pulse 3s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.02); }
        }
        
        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin: 40px 0;
        }
        
        .stat-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient);
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .stat-card h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 10px;
        }
        
        .stat-label {
            font-size: 1rem;
            color: var(--secondary);
            margin-bottom: 15px;
        }
        
        .language-bar {
            margin-bottom: 12px;
        }
        
        .language-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
            font-size: 0.9rem;
        }
        
        .language-progress {
            height: 8px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 4px;
            overflow: hidden;
        }
        
        .language-progress-bar {
            height: 100%;
            background: var(--gradient);
            border-radius: 4px;
            transition: width 1.5s ease-in-out;
        }
        
        .streak-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 20px;
        }
        
        .streak-item {
            text-align: center;
            padding: 15px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }
        
        .streak-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .streak-label {
            font-size: 0.9rem;
            color: var(--secondary);
        }
        
        .streak-dates {
            font-size: 0.8rem;
            color: var(--light);
            opacity: 0.8;
        }
        
        /* Main Content */
        .main-content {
            display: grid;
            grid-template-columns: 1fr 350px;
            gap: 40px;
            margin-bottom: 60px;
        }
        
        @media (max-width: 968px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }
        
        /* About Section */
        .about-section {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transform-style: preserve-3d;
            transition: transform 0.3s;
        }
        
        .about-section:hover {
            transform: translateY(-5px) rotateX(2deg);
        }
        
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .section-title i {
            font-size: 1.2rem;
        }
        
        .about-item {
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .about-item:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }
        
        .about-item h3 {
            font-size: 1.1rem;
            margin-bottom: 8px;
            color: var(--secondary);
        }
        
        .about-item p {
            color: var(--light);
            font-size: 0.95rem;
        }
        
        /* Skills Section */
        .skills-section {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transform-style: preserve-3d;
            transition: transform 0.3s;
        }
        
        .skills-section:hover {
            transform: translateY(-5px) rotateX(2deg);
        }
        
        .skills-category {
            margin-bottom: 25px;
        }
        
        .skills-category h3 {
            font-size: 1.1rem;
            margin-bottom: 15px;
            color: var(--secondary);
            border-left: 3px solid var(--primary);
            padding-left: 10px;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
            gap: 10px;
        }
        
        .skill-item {
            background: rgba(110, 68, 255, 0.1);
            border-radius: 8px;
            padding: 10px;
            text-align: center;
            font-size: 0.85rem;
            transition: all 0.3s;
            border: 1px solid rgba(110, 68, 255, 0.2);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 5px;
        }
        
        .skill-item:hover {
            background: rgba(110, 68, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .skill-icon {
            font-size: 1.5rem;
            color: var(--primary);
        }
        
        /* Contact Section */
        .contact-section {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            margin-bottom: 60px;
            transform-style: preserve-3d;
            transition: transform 0.3s;
        }
        
        .contact-section:hover {
            transform: translateY(-5px) rotateX(2deg);
        }
        
        .contact-links {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 20px;
        }
        
        .contact-link {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            text-decoration: none;
            color: var(--light);
            transition: all 0.3s;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .contact-link:hover {
            background: rgba(110, 68, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .contact-link i {
            font-size: 1.2rem;
            color: var(--primary);
        }
        
        /* 3D Background */
        #three-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 40px 0;
            color: var(--secondary);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: 60px;
            position: relative;
            overflow: hidden;
        }
        
        .footer-wave {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient);
            clip-path: polygon(0 70%, 100% 30%, 100% 100%, 0% 100%);
            opacity: 0.1;
            z-index: -1;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .typing-text {
                font-size: 1.8rem;
            }
            
            .tagline {
                font-size: 1.1rem;
            }
            
            .contact-links {
                flex-direction: column;
            }
            
            .banner {
                font-size: 1.4rem;
            }
            
            .streak-container {
                grid-template-columns: 1fr;
            }
            
            .profile-section {
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <!-- 3D Background -->
    <div id="three-container"></div>
    
    <header>
        <div class="container">
            <div class="typing-container">
                <div class="typing-text" id="typing-text"></div>
            </div>
            
            <div class="profile-section">
                <div class="profile-info">
                    <div class="profile-img">
                        <i class="fas fa-user"></i>
                    </div>
                    <h1>Hi 👋, I'm Imen HAJRI</h1>
                    <p class="tagline">Backend & DevOps Engineer ⚙️ || Cloud Infrastructure ☁️ || Microservices Architect 🏗️</p>
                    <div class="username">
                        <i class="fab fa-github"></i>
                        <span>imenhajri</span>
                    </div>
                </div>
                
                <div class="coding-gif">
                    <img src="https://media.tenor.com/IF2JdxzmyN4AAAAj/coding-girl.gif" alt="Girl Coding Animation">
                </div>
            </div>
        </div>
    </header>
    
    <div class="container">
        <div class="banner">
            Backend | DevOps | Cloud Engineer
        </div>
        
        <!-- Stats Grid -->
        <div class="stats-grid">
            <!-- Most Used Languages -->
            <div class="stat-card">
                <h3><i class="fas fa-code"></i> Most Used Languages</h3>
                <div class="language-bar">
                    <div class="language-name">
                        <span>JavaScript</span>
                        <span>80.59%</span>
                    </div>
                    <div class="language-progress">
                        <div class="language-progress-bar" data-width="80.59"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-name">
                        <span>HTML</span>
                        <span>9.33%</span>
                    </div>
                    <div class="language-progress">
                        <div class="language-progress-bar" data-width="9.33"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-name">
                        <span>Jupyter Notebook</span>
                        <span>3.56%</span>
                    </div>
                    <div class="language-progress">
                        <div class="language-progress-bar" data-width="3.56"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-name">
                        <span>Java</span>
                        <span>2.89%</span>
                    </div>
                    <div class="language-progress">
                        <div class="language-progress-bar" data-width="2.89"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-name">
                        <span>CSS</span>
                        <span>2.48%</span>
                    </div>
                    <div class="language-progress">
                        <div class="language-progress-bar" data-width="2.48"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-name">
                        <span>TypeScript</span>
                        <span>1.14%</span>
                    </div>
                    <div class="language-progress">
                        <div class="language-progress-bar" data-width="1.14"></div>
                    </div>
                </div>
            </div>
            
            <!-- GitHub Stats -->
            <div class="stat-card">
                <h3><i class="fas fa-chart-bar"></i> Imen HAJRI's GitHub Stats</h3>
                <div class="stat-number" id="star-count">130</div>
                <div class="stat-label">Total Stars Earned</div>
                
                <div class="stat-number" id="commit-count">430</div>
                <div class="stat-label">Total Commits (last year)</div>
                
                <div class="stat-number" id="pr-count">1</div>
                <div class="stat-label">Total PRs</div>
                
                <div class="stat-number">0</div>
                <div class="stat-label">Total Issues</div>
                
                <div class="stat-number">0</div>
                <div class="stat-label">Contributed to (last year)</div>
            </div>
            
            <!-- Contribution Stats -->
            <div class="stat-card">
                <h3><i class="fas fa-fire"></i> Contribution Stats</h3>
                <div class="stat-number">594</div>
                <div class="stat-label">Total Contributions</div>
                <div class="stat-label">Dec 2, 2023 - Present</div>
                
                <div class="streak-container">
                    <div class="streak-item">
                        <div class="streak-number">12</div>
                        <div class="streak-label">Current Streak</div>
                        <div class="streak-dates">Nov 28</div>
                    </div>
                    <div class="streak-item">
                        <div class="streak-number">12</div>
                        <div class="streak-label">Longest Streak</div>
                        <div class="streak-dates">Jun 22 - Jul 3</div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="main-content">
            <div class="about-section">
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-rocket"></i> What I'm Working On</h3>
                    <p>Building scalable <strong>Spring Boot Microservices</strong>, <strong>Kubernetes</strong> deployments & GitOps, <strong>CI/CD pipelines</strong> (GitHub Actions, GitLab CI), and high-availability <strong>distributed systems</strong> on AWS Cloud.</p>
                </div>
                
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-seedling"></i> What I'm Learning</h3>
                    <p>Advanced <strong>Resilience4j patterns</strong>, <strong>Kafka / RabbitMQ / SQS</strong>, Infrastructure as Code automation with <strong>Terraform</strong>, and cloud monitoring & optimization techniques.</p>
                </div>
                
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-tools"></i> My Tech Stack</h3>
                    <p>Working with <strong>Java & Spring Boot Microservices</strong>, <strong>Docker & Kubernetes</strong>, <strong>AWS Cloud</strong> (ECS, EKS, IAM, CloudWatch), <strong>Redis, Kafka, RabbitMQ</strong>, and building modern frontends with <strong>React, Angular, Vue.js</strong>.</p>
                </div>
                
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-laptop-code"></i> My Projects</h3>
                    <p>All of my projects are available at <a href="https://github.com/Imenhajri" style="color: var(--primary); text-decoration: none; font-weight: bold;">https://github.com/Imenhajri</a></p>
                </div>
                
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-comments"></i> Ask Me About</h3>
                    <p><strong>Java & Spring Boot Microservices</strong>, <strong>Docker, Kubernetes</strong>, <strong>AWS (ECS / EKS / IAM / CloudWatch)</strong>, <strong>Redis, Kafka, RabbitMQ</strong>, and <strong>CI/CD automation</strong>.</p>
                </div>
                
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-envelope"></i> How To Reach Me</h3>
                    <p>📧 <strong>hajriimen154@gmail.com</strong><br>📍 Tunisia</p>
                </div>
                
                <div class="about-item">
                    <h3 class="section-title"><i class="fas fa-lightbulb"></i> Fun Fact</h3>
                    <p>Cloud + DevOps = The fastest way to turn ideas into production 🚀</p>
                </div>
            </div>
            
            <div class="skills-section">
                <h2 class="section-title"><i class="fas fa-rocket"></i> Technologies & Tools</h2>
                
                <div class="skills-category">
                    <h3>Frontend</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <i class="fab fa-html5 skill-icon"></i>
                            <span>HTML5</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-css3-alt skill-icon"></i>
                            <span>CSS3</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-js skill-icon"></i>
                            <span>JavaScript</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-react skill-icon"></i>
                            <span>React</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-angular skill-icon"></i>
                            <span>Angular</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-vuejs skill-icon"></i>
                            <span>Vue.js</span>
                        </div>
                    </div>
                </div>
                
                <div class="skills-category">
                    <h3>Backend</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <i class="fab fa-java skill-icon"></i>
                            <span>Java</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-leaf skill-icon"></i>
                            <span>Spring</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-node-js skill-icon"></i>
                            <span>Node.js</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-python skill-icon"></i>
                            <span>Python</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-bolt skill-icon"></i>
                            <span>FastAPI</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-project-diagram skill-icon"></i>
                            <span>GraphQL</span>
                        </div>
                    </div>
                </div>
                
                <div class="skills-category">
                    <h3>Cloud & DevOps</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <i class="fab fa-aws skill-icon"></i>
                            <span>AWS</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-docker skill-icon"></i>
                            <span>Docker</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-ship skill-icon"></i>
                            <span>Kubernetes</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-github skill-icon"></i>
                            <span>GitHub Actions</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-gitlab skill-icon"></i>
                            <span>GitLab CI</span>
                        </div>
                        <div class="skill-item">
                            <i class="fab fa-jenkins skill-icon"></i>
                            <span>Jenkins</span>
                        </div>
                    </div>
                </div>
                
                <div class="skills-category">
                    <h3>Databases & Messaging</h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <i class="fas fa-database skill-icon"></i>
                            <span>PostgreSQL</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-database skill-icon"></i>
                            <span>MySQL</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-database skill-icon"></i>
                            <span>MongoDB</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-bolt skill-icon"></i>
                            <span>Redis</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-stream skill-icon"></i>
                            <span>Kafka</span>
                        </div>
                        <div class="skill-item">
                            <i class="fas fa-rabbit skill-icon"></i>
                            <span>RabbitMQ</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="contact-section">
            <h2 class="section-title"><i class="fas fa-handshake"></i> Connect With Me</h2>
            <div class="contact-links">
                <a href="https://github.com/Imenhajri" class="contact-link" target="_blank">
                    <i class="fab fa-github"></i>
                    <span>GitHub</span>
                </a>
                <a href="#" class="contact-link">
                    <i class="fab fa-linkedin"></i>
                    <span>LinkedIn</span>
                </a>
                <a href="#" class="contact-link">
                    <i class="fab fa-twitter"></i>
                    <span>Twitter</span>
                </a>
                <a href="#" class="contact-link">
                    <i class="fab fa-dev"></i>
                    <span>Dev.to</span>
                </a>
                <a href="mailto:hajriimen154@gmail.com" class="contact-link">
                    <i class="fas fa-envelope"></i>
                    <span>Email</span>
                </a>
            </div>
        </div>
    </div>
    
    <footer>
        <div class="footer-wave"></div>
        <div class="container">
            <p>&copy; 2023 Imen HAJRI. All rights reserved.</p>
            <p>Made with <i class="fas fa-heart" style="color: var(--accent);"></i> and JavaScript</p>
        </div>
    </footer>
    
    <script>
        // Three.js 3D Background
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ 
            alpha: true,
            antialias: true
        });
        
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.setClearColor(0x000000, 0);
        document.getElementById('three-container').appendChild(renderer.domElement);
        
        // Create floating geometric shapes
        const geometry = new THREE.IcosahedronGeometry(0.5, 0);
        const material = new THREE.MeshBasicMaterial({ 
            color: 0x6e44ff,
            wireframe: true,
            transparent: true,
            opacity: 0.3
        });
        
        const shapes = [];
        const numShapes = 20;
        
        for (let i = 0; i < numShapes; i++) {
            const shape = new THREE.Mesh(geometry, material);
            
            // Random position
            shape.position.x = (Math.random() - 0.5) * 30;
            shape.position.y = (Math.random() - 0.5) * 30;
            shape.position.z = (Math.random() - 0.5) * 20;
            
            // Random rotation
            shape.rotation.x = Math.random() * Math.PI;
            shape.rotation.y = Math.random() * Math.PI;
            
            // Random scale
            const scale = Math.random() * 1 + 0.3;
            shape.scale.set(scale, scale, scale);
            
            scene.add(shape);
            shapes.push({
                mesh: shape,
                speed: Math.random() * 0.02 + 0.005,
                rotationSpeed: {
                    x: (Math.random() - 0.5) * 0.02,
                    y: (Math.random() - 0.5) * 0.02,
                    z: (Math.random() - 0.5) * 0.02
                }
            });
        }
        
        camera.position.z = 5;
        
        // Animation
        function animate() {
            requestAnimationFrame(animate);
            
            // Animate shapes
            shapes.forEach(shape => {
                shape.mesh.rotation.x += shape.rotationSpeed.x;
                shape.mesh.rotation.y += shape.rotationSpeed.y;
                shape.mesh.rotation.z += shape.rotationSpeed.z;
                
                // Float up and down
                shape.mesh.position.y += Math.sin(Date.now() * shape.speed) * 0.005;
            });
            
            renderer.render(scene, camera);
        }
        
        animate();
        
        // Handle window resize
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });
        
        // Typing Animation
        const typingText = document.getElementById('typing-text');
        const texts = [
            "Hi 👋, I'm Imen HAJRI!",
            "Backend Engineer ⚙️ | DevOps Engineer 🚀",
            "Cloud Architect ☁️ | Microservices Expert 🏗️",
            "CI/CD Automation | Kubernetes | AWS",
            "Welcome to my GitHub Profile ✨"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        
        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingText.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingText.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }
            
            if (!isDeleting && charIndex === currentText.length) {
                isDeleting = true;
                setTimeout(type, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                setTimeout(type, 500);
            } else {
                setTimeout(type, isDeleting ? 50 : 100);
            }
        }
        
        // Start typing animation
        setTimeout(type, 1000);
        
        // Animate counters
        function animateCounter(elementId, targetValue, duration = 2000) {
            const element = document.getElementById(elementId);
            let start = 0;
            const increment = targetValue / (duration / 16);
            
            const updateCounter = () => {
                start += increment;
                if (start < targetValue) {
                    element.textContent = Math.floor(start);
                    requestAnimationFrame(updateCounter);
                } else {
                    element.textContent = targetValue;
                }
            };
            
            updateCounter();
        }
        
        // Animate language bars
        function animateLanguageBars() {
            const bars = document.querySelectorAll('.language-progress-bar');
            bars.forEach(bar => {
                const width = bar.getAttribute('data-width');
                bar.style.width = '0%';
                setTimeout(() => {
                    bar.style.width = width + '%';
                }, 500);
            });
        }
        
        // Start animations when in view
        const observerOptions = {
            threshold: 0.3
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateCounter('star-count', 130);
                    animateCounter('commit-count', 430);
                    animateCounter('pr-count', 1);
                    animateLanguageBars();
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);
        
        observer.observe(document.querySelector('.stats-grid'));
    </script>
</body>
</html>
