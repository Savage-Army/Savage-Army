<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muhid - GitHub Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #8a2be2;
            --secondary: #5e17eb;
            --accent: #371f76;
            --dark: #121212;
            --light: #f8f8f8;
            --gradient: linear-gradient(135deg, var(--primary), var(--secondary));
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--dark);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        header {
            text-align: center;
            padding: 3rem 1rem;
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: fadeIn 1s ease-out;
        }
        
        h2 {
            font-size: 2rem;
            margin-bottom: 2rem;
            color: var(--light);
        }
        
        h3 {
            font-size: 1.8rem;
            margin: 2rem 0 1.5rem;
            color: var(--primary);
        }
        
        p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }
        
        .gradient-text {
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: bold;
        }
        
        /* Animated background */
        .animated-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 15% 50%, rgba(138, 43, 226, 0.15), transparent 25%),
                radial-gradient(circle at 85% 30%, rgba(94, 23, 235, 0.1), transparent 25%);
            z-index: 1;
        }
        
        /* Skill icons */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }
        
        .skill-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            padding: 1rem;
            text-align: center;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(138, 43, 226, 0.3);
            background: rgba(138, 43, 226, 0.2);
        }
        
        .skill-item i, .skill-item img {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            color: var(--primary);
        }
        
        /* Stats section */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin: 3rem 0;
        }
        
        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            padding: 1.5rem;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 0.5rem;
        }
        
        /* Social badges */
        .social-badges {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin: 2rem 0;
        }
        
        .social-badge {
            display: inline-block;
            padding: 0.5rem 1.2rem;
            border-radius: 50px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--light);
            text-decoration: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }
        
        .social-badge:hover {
            background: var(--gradient);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(138, 43, 226, 0.4);
        }
        
        /* Project showcase */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            overflow: hidden;
            transition: transform 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .project-card:hover {
            transform: translateY(-8px);
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1rem 0;
        }
        
        .project-tag {
            background: rgba(138, 43, 226, 0.2);
            color: var(--light);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
        }
        
        /* Contribution graph */
        .contribution-graph {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            padding: 2rem;
            margin: 3rem 0;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        .animated {
            animation: fadeIn 1s ease-out;
        }
        
        .float {
            animation: float 3s ease-in-out infinite;
        }
        
        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.8rem;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="animated-bg"></div>
            <div class="header-content">
                <h1>Hey 👋 I'm Muhid</h1>
                <h2>Full Stack Developer & Open Source Enthusiast</h2>
                <p>I craft beautiful, functional web experiences with modern technologies. Passionate about clean code, user experience, and continuous learning.</p>
                
                <div class="social-badges">
                    <a href="#" class="social-badge"><i class="fab fa-linkedin"></i> LinkedIn</a>
                    <a href="#" class="social-badge"><i class="fab fa-twitter"></i> Twitter</a>
                    <a href="#" class="social-badge"><i class="fab fa-github"></i> GitHub</a>
                    <a href="#" class="social-badge"><i class="fab fa-dev"></i> Dev.to</a>
                    <a href="#" class="social-badge"><i class="fab fa-discord"></i> Discord</a>
                </div>
            </div>
        </header>
        
        <section class="animated">
            <h3>Tech Stack</h3>
            <div class="skills-grid">
                <div class="skill-item float">
                    <i class="fab fa-js-square"></i>
                    <p>JavaScript</p>
                </div>
                <div class="skill-item float" style="animation-delay: 0.2s;">
                    <i class="fab fa-typescript"></i>
                    <p>TypeScript</p>
                </div>
                <div class="skill-item float" style="animation-delay: 0.4s;">
                    <i class="fab fa-react"></i>
                    <p>React</p>
                </div>
                <div class="skill-item float" style="animation-delay: 0.6s;">
                    <i class="fab fa-node-js"></i>
                    <p>Node.js</p>
                </div>
                <div class="skill-item float" style="animation-delay: 0.8s;">
                    <i class="fab fa-python"></i>
                    <p>Python</p>
                </div>
                <div class="skill-item float" style="animation-delay: 1.0s;">
                    <i class="fab fa-aws"></i>
                    <p>AWS</p>
                </div>
                <div class="skill-item float" style="animation-delay: 1.2s;">
                    <i class="fab fa-docker"></i>
                    <p>Docker</p>
                </div>
                <div class="skill-item float" style="animation-delay: 1.4s;">
                    <i class="fab fa-git-alt"></i>
                    <p>Git</p>
                </div>
            </div>
        </section>
        
        <section class="animated">
            <h3>My Stats</h3>
            <div class="stats-container">
                <div class="stat-card">
                    <div class="stat-number" id="commits">0</div>
                    <p>Total Commits</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="repos">0</div>
                    <p>Public Repositories</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="contributions">0</div>
                    <p>Yearly Contributions</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="experience">0</div>
                    <p>Years of Experience</p>
                </div>
            </div>
        </section>
        
        <section class="animated">
            <h3>Featured Projects</h3>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-content">
                        <h4 class="project-title">LUNKERS</h4>
                        <p>A modern e-commerce platform with real-time inventory management and AI-powered recommendations.</p>
                        <div class="project-tags">
                            <span class="project-tag">React</span>
                            <span class="project-tag">Node.js</span>
                            <span class="project-tag">MongoDB</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-content">
                        <h4 class="project-title">INPUTER</h4>
                        <p>Advanced data processing tool that transforms unstructured data into structured formats with machine learning.</p>
                        <div class="project-tags">
                            <span class="project-tag">Python</span>
                            <span class="project-tag">TensorFlow</span>
                            <span class="project-tag">FastAPI</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-content">
                        <h4 class="project-title">PLY-7-D</h4>
                        <p>Multiplayer game development framework with built-in networking, physics engine, and asset pipeline.</p>
                        <div class="project-tags">
                            <span class="project-tag">C++</span>
                            <span class="project-tag">OpenGL</span>
                            <span class="project-tag">WebSocket</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="animated">
            <h3>Contribution Graph</h3>
            <div class="contribution-graph">
                <canvas id="contributionChart"></canvas>
            </div>
        </section>
        
        <section class="animated">
            <h3>About Me</h3>
            <p>I'm a passionate full-stack developer with expertise in modern web technologies. I enjoy creating efficient, scalable solutions and contributing to open-source projects. When I'm not coding, you can find me hiking, reading tech blogs, or experimenting with new frameworks.</p>
            
            <div class="stats-container">
                <div class="stat-card">
                    <div class="stat-number">15,842</div>
                    <p>Lines of Code This Month</p>
                </div>
                <div class="stat-card">
                    <div class="stat-number">98%</div>
                    <p>Project Completion Rate</p>
                </div>
            </div>
        </section>
        
        <footer>
            <p>Made with ❤️ by Muhid • 2023</p>
            <p>Connect with me on social media!</p>
        </footer>
    </div>

    <script>
        // Animated counters
        function animateValue(id, start, end, duration) {
            const obj = document.getElementById(id);
            let startTimestamp = null;
            const step = (timestamp) => {
                if (!startTimestamp) startTimestamp = timestamp;
                const progress = Math.min((timestamp - startTimestamp) / duration, 1);
                const value = Math.floor(progress * (end - start) + start);
                obj.innerHTML = value.toLocaleString();
                if (progress < 1) {
                    window.requestAnimationFrame(step);
                }
            };
            window.requestAnimationFrame(step);
        }
        
        // Initialize after page load
        document.addEventListener('DOMContentLoaded', function() {
            // Animate stats
            setTimeout(() => animateValue('commits', 0, 2842, 2000), 500);
            setTimeout(() => animateValue('repos', 0, 42, 1500), 1000);
            setTimeout(() => animateValue('contributions', 0, 1584, 2500), 1500);
            setTimeout(() => animateValue('experience', 0, 5, 1000), 2000);
            
            // Contribution chart
            const ctx = document.getElementById('contributionChart').getContext('2d');
            const contributionChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
                    datasets: [{
                        label: 'Monthly Contributions',
                        data: [324, 245, 387, 412, 356, 478, 521, 463, 395, 512, 487, 534],
                        backgroundColor: 'rgba(138, 43, 226, 0.5)',
                        borderColor: 'rgba(138, 43, 226, 1)',
                        borderWidth: 1
                    }]
                },
                options: {
                    scales: {
                        y: {
                            beginAtZero: true,
                            grid: {
                                color: 'rgba(255, 255, 255, 0.1)'
                            }
                        },
                        x: {
                            grid: {
                                color: 'rgba(255, 255, 255, 0.1)'
                            }
                        }
                    },
                    plugins: {
                        legend: {
                            labels: {
                                color: '#fff'
                            }
                        }
                    }
                }
            });
            
            // Add intersection observer for scroll animations
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animated');
                    }
                });
            }, { threshold: 0.1 });
            
            document.querySelectorAll('section').forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
