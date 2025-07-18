<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Bio Banner</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            background: #0d1117;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .bio-banner {
            width: 600px;
            height: 300px;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 50%, #ff6b6b 100%);
            border-radius: 15px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        .matrix-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, rgba(0, 255, 127, 0.1), rgba(0, 191, 255, 0.1));
            opacity: 0.3;
        }
        .code-rain {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            font-family: 'Courier New', monospace;
            font-size: 12px;
            color: #00ff7f;
            overflow: hidden;
            opacity: 0.4;
        }
        .code-line {
            position: absolute;
            white-space: nowrap;
            animation: fall linear infinite;
        }
        .code-line:nth-child(1) { left: 10%; animation-duration: 8s; animation-delay: 0s; }
        .code-line:nth-child(2) { left: 25%; animation-duration: 6s; animation-delay: 2s; }
        .code-line:nth-child(3) { left: 40%; animation-duration: 9s; animation-delay: 1s; }
        .code-line:nth-child(4) { left: 55%; animation-duration: 7s; animation-delay: 3s; }
        .code-line:nth-child(5) { left: 70%; animation-duration: 8s; animation-delay: 1.5s; }
        .code-line:nth-child(6) { left: 85%; animation-duration: 6s; animation-delay: 2.5s; }
        @keyframes fall {
            0% { transform: translateY(-100px); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(400px); opacity: 0; }
        }
        .profile-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            color: white;
            z-index: 10;
        }
        .greeting {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
            animation: typewriter 4s steps(40) infinite;
            overflow: hidden;
            white-space: nowrap;
            border-right: 2px solid #00ff7f;
        }
        @keyframes typewriter {
            0%, 10% { width: 0; }
            50%, 90% { width: 100%; }
            100% { width: 0; }
        }
        .role {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: #00ff7f;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
            animation: glow 2s ease-in-out infinite alternate;
        }
        @keyframes glow {
            from { text-shadow: 0 0 5px #00ff7f, 0 0 10px #00ff7f, 0 0 15px #00ff7f; }
            to { text-shadow: 0 0 10px #00ff7f, 0 0 20px #00ff7f, 0 0 30px #00ff7f; }
        }
        .tech-stack {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        .tech-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 8px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: float 3s ease-in-out infinite;
        }
        .tech-item:nth-child(1) { animation-delay: 0s; }
        .tech-item:nth-child(2) { animation-delay: 0.5s; }
        .tech-item:nth-child(3) { animation-delay: 1s; }
        .tech-item:nth-child(4) { animation-delay: 1.5s; }
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        .github-stats {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 20px;
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.8);
        }
        .stat-item {
            text-align: center;
            animation: pulse 2s ease-in-out infinite;
        }
        .stat-item:nth-child(2) { animation-delay: 0.5s; }
        .stat-item:nth-child(3) { animation-delay: 1s; }
        @keyframes pulse {
            0%, 100% { opacity: 0.8; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.05); }
        }
        .cursor {
            position: absolute;
            top: 20px;
            right: 30px;
            width: 20px;
            height: 20px;
            background: #00ff7f;
            border-radius: 50%;
            animation: blink 1s infinite;
        }
        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }
        .terminal-window {
            position: absolute;
            top: 15px;
            left: 20px;
            width: 200px;
            height: 80px;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 8px;
            padding: 10px;
            font-family: 'Courier New', monospace;
            font-size: 10px;
            color: #00ff7f;
            border: 1px solid rgba(0, 255, 127, 0.3);
            animation: slideIn 3s ease-in-out infinite;
        }
        @keyframes slideIn {
            0%, 30% { transform: translateX(-220px); opacity: 0; }
            40%, 90% { transform: translateX(0); opacity: 1; }
            100% { transform: translateX(-220px); opacity: 0; }
        }
        .terminal-header {
            display: flex;
            gap: 5px;
            margin-bottom: 8px;
        }
        .terminal-dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
        }
        .terminal-dot.red { background: #ff5f56; }
        .terminal-dot.yellow { background: #ffbd2e; }
        .terminal-dot.green { background: #27ca3f; }
        .particles-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .floating-emoji {
            position: absolute;
            font-size: 20px;
            animation: floatEmoji 6s ease-in-out infinite;
        }
        .floating-emoji:nth-child(1) { left: 20%; animation-delay: 0s; }
        .floating-emoji:nth-child(2) { left: 80%; animation-delay: 2s; }
        .floating-emoji:nth-child(3) { left: 50%; animation-delay: 4s; }
        @keyframes floatEmoji {
            0%, 100% { transform: translateY(300px) rotate(0deg); opacity: 0; }
            10%, 90% { opacity: 1; }
            50% { transform: translateY(-50px) rotate(180deg); }
        }
    </style>
</head>
<body>
    <div class="bio-banner">
        <div class="matrix-bg"></div>   
        <div class="code-rain">
            <div class="code-line">const developer = { skills: ['JS', 'Python', 'React'] };</div>
            <div class="code-line">function createAwesome() { return innovation + passion; }</div>
            <div class="code-line">git commit -m "Building the future, one line at a time"</div>
            <div class="code-line">while(learning) { keepCoding(); }</div>
            <div class="code-line">npm install creativity --save</div>
            <div class="code-line">console.log('Hello, World! 🚀');</div>
        </div>
        <div class="particles-container">
            <div class="floating-emoji">🚀</div>
            <div class="floating-emoji">💻</div>
            <div class="floating-emoji">⚡</div>
        </div>
        <div class="terminal-window">
            <div class="terminal-header">
                <div class="terminal-dot red"></div>
                <div class="terminal-dot yellow"></div>
                <div class="terminal-dot green"></div>
            </div>
            <div>$ whoami</div>
            <div>awesome_developer</div>
            <div>$ git status</div>
            <div>On branch: main</div>
            <div>Status: Coding...</div>
        </div>
        <div class="cursor"></div>
        <div class="profile-content">
            <div class="greeting">Hi there! I'm a Developer 👋</div>
            <div class="role">Full Stack Developer & Problem Solver</div>
            <div class="tech-stack">
                <div class="tech-item">JavaScript</div>
                <div class="tech-item">Python</div>
                <div class="tech-item">React</div>
                <div class="tech-item">Django</div>
            </div>
        </div>
        <div class="github-stats">
            <div class="stat-item">
                <div>⭐ 1.2K</div>
                <div>Stars</div>
            </div>
            <div class="stat-item">
                <div>🔥 500</div>
                <div>Commits</div>
            </div>
            <div class="stat-item">
                <div>📦 50</div>
                <div>Repos</div>
            </div>
        </div>
    </div>
    <script>
        // Add some interactive elements
        function createCodeBubble() {
            const banner = document.querySelector('.bio-banner');
            const bubble = document.createElement('div');
            const codeSnippets = ['{}', '[]', '()', '<>', '/>', '==', '++', '--', '=>', '&&']; 
            bubble.textContent = codeSnippets[Math.floor(Math.random() * codeSnippets.length)];
            bubble.style.position = 'absolute';
            bubble.style.left = Math.random() * 100 + '%';
            bubble.style.top = '100%';
            bubble.style.fontSize = Math.random() * 16 + 12 + 'px';
            bubble.style.color = '#00ff7f';
            bubble.style.fontFamily = 'Courier New, monospace';
            bubble.style.opacity = '0.6';
            bubble.style.pointerEvents = 'none';
            bubble.style.zIndex = '5';
            bubble.style.animation = 'bubble 4s ease-out forwards';
            banner.appendChild(bubble);
            setTimeout(() => {
                bubble.remove();
            }, 4000);
        }
        // Add bubble animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes bubble {
                0% { 
                    transform: translateY(0) rotate(0deg);
                    opacity: 0.6;
                }
                50% { 
                    opacity: 1;
                }
                100% { 
                    transform: translateY(-350px) rotate(360deg);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);
        // Create bubbles periodically
        setInterval(createCodeBubble, 2000);
        // Add click interaction
        document.querySelector('.bio-banner').addEventListener('click', function(e) {
            const ripple = document.createElement('div');
            ripple.style.position = 'absolute';
            ripple.style.left = e.offsetX + 'px';
            ripple.style.top = e.offsetY + 'px';
            ripple.style.width = '20px';
            ripple.style.height = '20px';
            ripple.style.background = 'rgba(0, 255, 127, 0.5)';
            ripple.style.borderRadius = '50%';
            ripple.style.transform = 'translate(-50%, -50%)';
            ripple.style.animation = 'ripple 1s ease-out forwards';
            ripple.style.pointerEvents = 'none';            
            this.appendChild(ripple);            
            setTimeout(() => {
                ripple.remove();
            }, 1000);
        });
        // Add ripple animation
        const rippleStyle = document.createElement('style');
        rippleStyle.textContent = `
            @keyframes ripple {
                0% { 
                    transform: translate(-50%, -50%) scale(0);
                    opacity: 1;
                }
                100% { 
                    transform: translate(-50%, -50%) scale(10);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(rippleStyle);
    </script>
</body>
</html>

# 👋 Hi, I'm Darshan Pokhrel
I'm a passionate backend developer and Computer Science student with a strong interest in building scalable APIs and smart IoT solutions. I enjoy working with technologies like Django, PostgreSQL, and JWT Authentication, and I'm currently exploring cloud integration and real-time systems.
🔧 Currently working as an IT Intern

💻 Projects: Expense Tracker API, Smart Pet Feeder (Feed Mate)

🌱 Learning: Django Rest Framework, Git, and CI/CD

📍 Based in Nepal

 ## 🔧 Tech Stack
- ⚙️ Languages: Python, JavaScript, C
- 💻 Backend: Django, Node.js
- 🧠 DB: PostgreSQL, SQLite
- ☁️ Tools: Git, Docker, AWS

## 📫 Connect with Me

- ✉️ Email: dpokhrel420@gmail.com
- 🔗 [LinkedIn](www.linkedin.com/in/darshan-pokhrel-9073a4292)

<h2 align="center">🚀 Tech Stack</h2>

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" height="70" alt="Python"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg" height="70" alt="Django"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="70" alt="JavaScript"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" height="70" alt="PostgreSQL"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="70" alt="Git"/>
</p>
