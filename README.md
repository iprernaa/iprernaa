<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prerna Singh | Engineering Portfolio</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        
        /* Pastel Pink Palette Variable System */
        :root {
            --bg-base: #fff5f8;       /* Very soft pastel pink background */
            --text-primary: #5c3b46;  /* Deep mauve text */
            --text-secondary: #8c6a75;/* Lighter mauve */
            --accent-pink: #ffb7c5;   /* Sakura pastel accent */
            --accent-glow: #ffe0e6;   /* Lighter accent/glow */
            --glass-bg: rgba(255, 255, 255, 0.7);
            --border-base: #f1d3db;
        }

        body { background: var(--bg-base); color: var(--text-primary); scroll-behavior: smooth; overflow-x: hidden; }
        
        /* Navigation Bar (Glassmorphic Pastel) */
        nav { display: flex; justify-content: space-between; align-items: center; padding: 18px 8%; background: rgba(255, 245, 248, 0.9); position: fixed; width: 100%; top: 0; z-index: 1000; backdrop-filter: blur(10px); border-bottom: 1px solid var(--border-base); box-shadow: 0 4px 10px rgba(92, 59, 70, 0.05); }
        .logo { font-size: 22px; font-weight: bold; color: var(--text-primary); letter-spacing: 1px; }
        .nav-links a { color: var(--text-secondary); text-decoration: none; margin-left: 25px; font-weight: 500; transition: 0.3s; font-size: 15px; }
        .nav-links a:hover { color: var(--text-primary); border-bottom: 2px solid var(--accent-pink); padding-bottom: 4px; }

        /* Hero Section (Soft Pink Gradient Fade) */
        .hero { height: 100vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; padding: 0 20px; background: radial-gradient(circle at center, #ffffff 0%, var(--bg-base) 100%); position: relative; }
        .hero h1 { font-size: 4rem; margin-bottom: 15px; font-weight: 800; letter-spacing: -1px; animation: fadeIn 1.5s ease; color: var(--text-primary); }
        .hero h1 span { color: var(--text-primary); text-shadow: 0 0 20px var(--accent-glow); }
        .hero h2 { font-size: 1.5rem; color: var(--text-secondary); margin-bottom: 20px; font-weight: 400; max-width: 700px; }
        .hero p { font-size: 1.1rem; color: var(--text-secondary); max-width: 700px; margin-bottom: 35px; line-height: 1.6; }
        
        /* Modern Button (Soft Pink) */
        .btn { background: #ffcfd9; color: var(--text-primary); padding: 14px 35px; font-weight: bold; border-radius: 30px; text-decoration: none; transition: 0.3s; box-shadow: 0 4px 12px rgba(241, 211, 219, 0.8); display: inline-block; border: 1px solid var(--border-base); }
        .btn:hover { transform: translateY(-3px); box-shadow: 0 6px 18px rgba(241, 211, 219, 1); background: #fcdde4; }

        /* General Layout Sections */
        section { padding: 100px 10% 80px 10%; border-bottom: 1px solid var(--border-base); }
        .section-title { font-size: 2.5rem; text-align: center; margin-bottom: 60px; font-weight: 700; position: relative; color: var(--text-primary); }
        .section-title::after { content: ''; width: 60px; height: 4px; background: var(--accent-pink); position: absolute; bottom: -15px; left: 50%; transform: translateX(-50%); border-radius: 2px; }

        /* Grid & Card Frameworks (Pastel Glass) */
        .grid-layout { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        .card { background: var(--glass-bg); padding: 30px; border-radius: 16px; border: 1px solid var(--border-base); transition: 0.3s; position: relative; display: flex; flex-direction: column; justify-content: space-between; box-shadow: 0 4px 15px rgba(92, 59, 70, 0.05); }
        .card:hover { transform: translateY(-5px); border-color: var(--accent-pink); box-shadow: 0 10px 25px rgba(92, 59, 70, 0.08); }
        
        .card-tag { background: rgba(255, 183, 197, 0.15); color: #c47684; padding: 5px 12px; border-radius: 20px; font-size: 11px; display: inline-block; margin-bottom: 15px; font-weight: 600; width: max-content; text-transform: uppercase; border: 1px solid rgba(255, 183, 197, 0.3); }
        .card-tag.intern { background: rgba(16, 185, 129, 0.1); color: #10b981; border: 1px solid rgba(16, 185, 129, 0.2); }
        .card-tag.award { background: rgba(245, 158, 11, 0.1); color: #d48e10; border: 1px solid rgba(245, 158, 11, 0.2); }
        
        .card h3 { font-size: 1.3rem; margin-bottom: 8px; color: var(--text-primary); }
        .card h4 { font-size: 1rem; color: var(--text-secondary); margin-bottom: 12px; font-weight: 500; }
        .card p { color: var(--text-secondary); font-size: 14px; line-height: 1.6; margin-bottom: 15px; }
        
        .tech-badges span { background: #ffebee; color: var(--text-secondary); font-size: 12px; padding: 4px 10px; border-radius: 6px; margin-right: 5px; display: inline-block; margin-top: 5px; border: 1px solid var(--border-base); }

        /* Achievements Styling */
        .achievement-icon { font-size: 40px; margin-bottom: 15px; filter: drop-shadow(0 4px 6px rgba(0,0,0,0.1)); }

        /* Skills Layout (Pastel Pink Track) */
        .skills-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; }
        .skill-bar { margin-bottom: 20px; }
        .skill-info { display: flex; justify-content: space-between; margin-bottom: 8px; font-weight: 600; color: var(--text-secondary); font-size: 14px; }
        .progress-line { background: #ffebee; height: 10px; border-radius: 5px; overflow: hidden; border: 1px solid var(--border-base); }
        .progress-line span { height: 100%; background: linear-gradient(90deg, var(--accent-pink), #fcdde4); border-radius: 5px; display: block; }

        /* Footer styling */
        footer { background: #fff1f4; padding: 35px; text-align: center; color: var(--text-secondary); font-size: 14px; border-top: 1px solid var(--border-base); }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        @media(max-width: 768px) { .skills-grid { grid-template-columns: 1fr; } }
    </style>
</head>
<body>

    <nav>
        <div class="logo">Prerna.Dev</div>
        <div class="nav-links">
            <a href="#home">Home</a>
            <a href="#internships">Internships</a>
            <a href="#projects">Projects</a>
            <a href="#skills">Skills</a>
            <a href="#achievements">Achievements</a>
        </div>
    </nav>

    <section id="home" class="hero">
        <h1>Hi, I am <span>Prerna Singh</span></h1>
        <h2>MERN Stack Developer Intern & Computer Science Engineer (B.Tech '29)</h2>
        <p>Student at Kanpur Institute of Technology. Fusing modern full-stack web architectures (React, Node.js) with hands-on hardware engineering exploration, including automated sensory arrays and embedded microcontrollers.</p>
        <a href="#internships" class="btn">Explore My Journey</a>
    </section>

    <section id="internships" style="background: #fff9fb;">
        <h2 class="section-title">Professional Experience</h2>
        <div class="grid-layout">
            
            <div class="card" style="border-left: 4px solid #10b981;">
                <div>
                    <span class="card-tag intern">Current Experience</span>
                    <h3>Web Development Intern</h3>
                    <h4>SaiKet Systems (June 2026 - Present)</h4>
                    <p>Building rich user-friendly interactive frontends, validating clean semantic structures, and implementing responsive system components for optimized consumer delivery.</p>
                </div>
                <div class="tech-badges">
                    <span>HTML5</span><span>CSS3</span><span>JavaScript</span><span>DOM Control</span>
                </div>
            </div>

            <div class="card" style="border-left: 4px solid #38bdf8;">
                <div>
                    <span class="card-tag intern">Remote Experience</span>
                    <h3>MERN Stack Developer Intern</h3>
                    <h4>Emertxe Information Technologies</h4>
                    <p>Engineered full-stack responsive capabilities, managed scalable source repositories via Git architectures, and organized local logic trees.</p>
                </div>
                <div class="tech-badges">
                    <span>MERN Stack</span><span>Git Controls</span><span>React.js</span>
                </div>
            </div>

        </div>
    </section>

    <section id="projects">
        <h2 class="section-title">Featured Projects</h2>
        <div class="grid-layout">
            
            <div class="card">
                <div>
                    <span class="card-tag">Full-Stack</span>
                    <h3>Student Productivity & Placement Tracker</h3>
                    <p>Designed a comprehensive analytics dashboard monitoring core student metrics, tracking performance thresholds, and ensuring employment readiness milestones.</p>
                </div>
                <div class="tech-badges">
                    <span>React.js</span><span>Tailwind CSS</span><span>Vite</span>
                </div>
            </div>

            <div class="card">
                <div>
                    <span class="card-tag">Hardware Automation</span>
                    <h3>RADAR System Using Arduino</h3>
                    <p>Programmed an automated sonic sensory matrix utilizing spatial ultrasonic sound-wave tracking to build interactive mapping charts.</p>
                </div>
                <div class="tech-badges">
                    <span>Arduino</span><span>Ultrasonic Sensor</span><span>Embedded C</span>
                </div>
            </div>

        </div>
    </section>

    <section id="skills" style="background: #fff9fb;">
        <h2 class="section-title">Technical Expertise</h2>
        <div class="skills-grid">
            
            <div>
                <h3 style="color: var(--text-primary); margin-bottom: 20px; font-size: 18px;">Software & Architecture</h3>
                <div class="skill-bar">
                    <div class="skill-info"><span>MERN Stack (MongoDB, React.js, Express)</span><span>85%</span></div>
                    <div class="progress-line"><span style="width: 85%;"></span></div>
                </div>
                <div class="skill-bar">
                    <div class="skill-info"><span>JavaScript / Tailwind CSS Framework</span><span>80%</span></div>
                    <div class="progress-line"><span style="width: 80%;"></span></div>
                </div>
                <div class="skill-bar">
                    <div class="skill-info"><span>HTML5 Structures & Web Styling</span><span>95%</span></div>
                    <div class="progress-line"><span style="width: 95%;"></span></div>
                </div>
            </div>

            <div>
                <h3 style="color: var(--text-secondary); margin-bottom: 20px; font-size: 18px;">Analytics & Professional Sim</h3>
                <div class="skill-bar">
                    <div class="skill-info"><span>Embedded Electronics & Arduino Prototyping</span><span>75%</span></div>
                    <div class="progress-line"><span style="width: 75%;"></span></div>
                </div>
                <div class="skill-bar">
                    <div class="skill-info"><span>Data Visualization & Tableau</span><span>80%</span></div>
                    <div class="progress-line"><span style="width: 80%;"></span></div>
                </div>
                <div class="skill-bar">
                    <div class="skill-info"><span>Team Collaboration & Strategic Communication</span><span>90%</span></div>
                    <div class="progress-line"><span style="width: 90%;"></span></div>
                </div>
            </div>

        </div>
    </section>

    <section id="achievements">
        <h2 class="section-title">Honors & Achievements</h2>
        <div class="grid-layout">
            
            <div class="card" style="border-top: 4px solid #f59e0b;">
                <div>
                    <div class="achievement-icon">🏆</div>
                    <span class="card-tag award">Talent Hunt Champion</span>
                    <h3>Certificate of Achievement : Talent Hunt</h3>
                    <h4>Issued by BTech CSE • Sep 2025</h4>
                    <p>Secured top recognition for outstanding talent execution during the Srijan Induction Program at Kanpur Institute of Technology.</p>
                </div>
            </div>

            <div class="card" style="border-top: 4px solid #f59e0b;">
                <div>
                    <div class="achievement-icon">⚡</div>
                    <span class="card-tag award">Tongue Twister Winner</span>
                    <h3>Certificate of Achievement : Tongue Twister</h3>
                    <h4>Issued by BTech CSE • Sep 2025</h4>
                    <p>Won high honors celebrating linguistic processing speed, focus, and rapid execution skills at the Srijan 2025 event.</p>
                </div>
            </div>

            <div class="card" style="border-top: 4px solid #38bdf8;">
                <div>
                    <div class="achievement-icon">💼</div>
                    <span class="card-tag award">Corporate Simulation</span>
                    <h3>JPMorgan Chase Software Simulation</h3>
                    <h4>Issued June 2026</h4>
                    <p>Successfully evaluated interface structures, code adjustments, and technical workflows modeling enterprise engineering teams.</p>
                </div>
            </div>

        </div>
    </section>

    <footer>
        Designed & Maintained by Prerna Singh © 2026 | Portfolio Crafted for SaiKet Systems Intern Evaluation Review
    </footer>

</body>
</html>
