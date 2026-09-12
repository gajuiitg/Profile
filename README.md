<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-TND589HSEC"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-TND589HSEC');
</script>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chemical Engineer · Process & Thermodynamics</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #0f172a;
            --secondary: #1e293b;
            --accent: #0ea5e9;
            --accent-glow: rgba(14, 165, 233, 0.3);
            --gold: #f59e0b;
            --gold-glow: rgba(245, 158, 11, 0.25);
            --text: #f1f5f9;
            --text-muted: #94a3b8;
            --glass: rgba(30, 41, 59, 0.6);
            --glass-border: rgba(255, 255, 255, 0.08);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--primary);
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: 
                radial-gradient(ellipse at 20% 20%, rgba(14, 165, 233, 0.15) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 80%, rgba(245, 158, 11, 0.1) 0%, transparent 50%),
                radial-gradient(ellipse at 50% 50%, rgba(99, 102, 241, 0.08) 0%, transparent 60%);
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%2394a3b8' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            animation: drift 120s linear infinite;
        }

        @keyframes drift {
            0% { transform: translate(0, 0); }
            100% { transform: translate(-50px, -50px); }
        }

        /* Floating orbs */
        .orb {
            position: fixed;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.4;
            z-index: -1;
            animation: float 20s ease-in-out infinite;
        }

        .orb-1 {
            width: 400px;
            height: 400px;
            background: linear-gradient(135deg, #0ea5e9, #6366f1);
            top: -100px;
            right: -100px;
            animation-delay: 0s;
        }

        .orb-2 {
            width: 300px;
            height: 300px;
            background: linear-gradient(135deg, #f59e0b, #ef4444);
            bottom: -50px;
            left: -50px;
            animation-delay: -5s;
        }

        .orb-3 {
            width: 250px;
            height: 250px;
            background: linear-gradient(135deg, #10b981, #0ea5e9);
            top: 50%;
            left: 50%;
            animation-delay: -10s;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) scale(1); }
            33% { transform: translate(30px, -30px) scale(1.1); }
            66% { transform: translate(-20px, 20px) scale(0.9); }
        }

        /* Main container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 3rem 1.5rem;
        }

        /* Hero Section */
        .hero {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 3rem;
            padding: 2rem 0 4rem;
            position: relative;
        }

        /* Info Section */
        .info-section {
            flex: 1;
            min-width: 300px;
        }

        .name {
            font-family: 'Outfit', sans-serif;
            font-size: 3.2rem;
            font-weight: 800;
            background: linear-gradient(135deg, #fff 0%, #94a3b8 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.1;
            margin-bottom: 0.5rem;
            letter-spacing: -0.02em;
        }

        .title-row {
            display: flex;
            align-items: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin-bottom: 1.5rem;
        }

        .title {
            font-size: 1.25rem;
            color: var(--accent);
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .tagline {
            color: var(--text-muted);
            font-size: 1.05rem;
            margin-bottom: 2rem;
            display: flex;
            align-items: center;
            gap: 0.8rem;
            flex-wrap: wrap;
        }

        .tagline i {
            color: var(--accent);
        }

        .tagline span {
            display: inline-flex;
            align-items: center;
            gap: 0.4rem;
        }

        .tagline .dot {
            width: 4px;
            height: 4px;
            background: var(--text-muted);
            border-radius: 50%;
        }

        /* Section styling */
        .section {
            margin-top: 3rem;
        }

        .section-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid var(--glass-border);
        }

        .section-icon {
            width: 48px;
            height: 48px;
            border-radius: 16px;
            background: linear-gradient(135deg, rgba(14, 165, 233, 0.2), rgba(14, 165, 233, 0.05));
            border: 1px solid rgba(14, 165, 233, 0.2);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent);
            font-size: 1.3rem;
            flex-shrink: 0;
        }

        .section-title {
            font-family: 'Outfit', sans-serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--text);
        }

        .section-subtitle {
            color: var(--text-muted);
            font-size: 0.9rem;
            margin-top: 0.2rem;
        }

        /* Tools Grid */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 1.5rem;
        }

        .tool-card {
            background: var(--glass);
            border: 1px solid var(--glass-border);
            border-radius: 24px;
            padding: 2rem;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(20px);
        }

        .tool-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--accent), var(--gold));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .tool-card:hover {
            transform: translateY(-8px);
            border-color: rgba(14, 165, 233, 0.2);
            box-shadow: 
                0 20px 40px -10px rgba(0, 0, 0, 0.4),
                0 0 0 1px rgba(14, 165, 233, 0.1);
        }

        .tool-card:hover::before {
            opacity: 1;
        }

        .tool-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .tool-icon {
            width: 52px;
            height: 52px;
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            flex-shrink: 0;
        }

        .tool-icon.blue { background: linear-gradient(135deg, rgba(14, 165, 233, 0.2), rgba(14, 165, 233, 0.05)); color: #38bdf8; }
        .tool-icon.orange { background: linear-gradient(135deg, rgba(245, 158, 11, 0.2), rgba(245, 158, 11, 0.05)); color: #fbbf24; }
        .tool-icon.green { background: linear-gradient(135deg, rgba(16, 185, 129, 0.2), rgba(16, 185, 129, 0.05)); color: #34d399; }
        .tool-icon.purple { background: linear-gradient(135deg, rgba(139, 92, 246, 0.2), rgba(139, 92, 246, 0.05)); color: #a78bfa; }
        .tool-icon.red { background: linear-gradient(135deg, rgba(239, 68, 68, 0.2), rgba(239, 68, 68, 0.05)); color: #f87171; }

        .tool-name {
            font-family: 'Outfit', sans-serif;
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--text);
        }

        .tool-desc {
            color: var(--text-muted);
            font-size: 0.95rem;
            line-height: 1.6;
            margin-bottom: 1.5rem;
        }

        .tool-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .tool-tags {
            display: flex;
            gap: 0.5rem;
            flex-wrap: wrap;
        }

        .tool-tag {
            font-size: 0.75rem;
            font-weight: 600;
            padding: 0.3rem 0.8rem;
            border-radius: 100px;
            background: rgba(255,255,255,0.05);
            color: var(--text-muted);
            border: 1px solid var(--glass-border);
        }

        .launch-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: linear-gradient(135deg, var(--accent), #0284c7);
            color: white;
            text-decoration: none;
            padding: 0.6rem 1.4rem;
            border-radius: 100px;
            font-weight: 600;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(14, 165, 233, 0.3);
        }

        .launch-btn:hover {
            transform: translateX(4px);
            box-shadow: 0 8px 25px rgba(14, 165, 233, 0.4);
        }

        .launch-btn i {
            transition: transform 0.3s ease;
        }

        .launch-btn:hover i {
            transform: translateX(3px);
        }

        /* Footer */
        .footer {
            margin-top: 4rem;
            padding: 2.5rem 0;
            border-top: 1px solid var(--glass-border);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1.5rem;
            color: var(--text-muted);
            font-size: 0.9rem;
            text-align: center;
        }

        .footer-top {
            font-family: 'Outfit', sans-serif;
            font-size: 1.4rem;
            font-weight: 700;
            color: var(--text);
            letter-spacing: -0.01em;
        }

        .footer-contact {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
        }

        .footer-contact a,
        .footer-contact span {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: var(--glass);
            border: 1px solid var(--glass-border);
            padding: 0.5rem 1.2rem;
            border-radius: 100px;
            color: var(--text);
            text-decoration: none;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .footer-contact a:hover {
            background: rgba(14, 165, 233, 0.15);
            border-color: rgba(14, 165, 233, 0.3);
            transform: translateY(-2px);
        }

        .footer-contact i {
            color: var(--accent);
            font-size: 0.85rem;
        }

        .footer-bottom {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.5rem;
            align-items: center;
            font-size: 0.85rem;
        }

        .footer-item {
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }

        .footer-item i {
            color: var(--accent);
            font-size: 0.85rem;
        }

        .footer-divider {
            width: 4px;
            height: 4px;
            background: var(--text-muted);
            border-radius: 50%;
            opacity: 0.5;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--primary);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--secondary);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero {
                flex-direction: column;
                text-align: center;
                gap: 2rem;
            }

            .name {
                font-size: 2.4rem;
            }

            .title-row {
                justify-content: center;
            }

            .tagline {
                justify-content: center;
            }

            .tools-grid {
                grid-template-columns: 1fr;
            }

            .footer-contact {
                flex-direction: column;
                align-items: center;
            }

            .footer-bottom {
                flex-direction: column;
                gap: 0.8rem;
            }

            .footer-divider {
                display: none;
            }
        }

        /* Entrance animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.8s ease forwards;
        }

        .fade-in-delay-1 { animation-delay: 0.1s; }
        .fade-in-delay-2 { animation-delay: 0.2s; }
        .fade-in-delay-3 { animation-delay: 0.3s; }
        .fade-in-delay-4 { animation-delay: 0.4s; }
        .fade-in-delay-5 { animation-delay: 0.5s; }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Particle canvas */
        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }
    </style>
<base target="_blank">
</head>
<body>
    <canvas id="particles"></canvas>
    <div class="bg-animation"></div>
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="orb orb-3"></div>

    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <div class="info-section fade-in fade-in-delay-1">
                <h1 class="name">Chemical Engineer</h1>
                <div class="title-row">
                    <div class="title">
                        <i class="fas fa-flask"></i>
                        Process & Thermodynamics
                    </div>
                </div>

                <div class="tagline">
                    <span><i class="fas fa-atom"></i> Process Simulation</span>
                    <span class="dot"></span>
                    <span>Thermodynamics</span>
                    <span class="dot"></span>
                    <span>Control Valves</span>
                </div>
            </div>
        </div>

        <!-- Tools Section -->
        <div class="section fade-in fade-in-delay-2">
            <div class="section-header">
                <div class="section-icon">
                    <i class="fas fa-cogs"></i>
                </div>
                <div>
                    <div class="section-title">Engineering Tools</div>
                    <div class="section-subtitle">Specialized calculators & utilities for chemical engineering</div>
                </div>
            </div>

            <div class="tools-grid">
                <!-- PSV-cal -->
                <div class="tool-card fade-in fade-in-delay-3">
                    <div class="tool-header">
                        <div class="tool-icon red">
                            <i class="fas fa-exclamation-triangle"></i>
                        </div>
                        <div class="tool-name">PSV-cal</div>
                    </div>
                    <div class="tool-desc">
                        Pressure safety valve calculation for all types of cases & relief scenarios. Ensure safe operation with precise PSV sizing.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">PSV Sizing</span>
                            <span class="tool-tag">Safety</span>
                        </div>
                        <a href="https://gajuiitg.github.io/PSV-cal/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>

                <!-- Thermocal -->
                <div class="tool-card fade-in fade-in-delay-3">
                    <div class="tool-header">
                        <div class="tool-icon orange">
                            <i class="fas fa-thermometer-half"></i>
                        </div>
                        <div class="tool-name">Thermocal</div>
                    </div>
                    <div class="tool-desc">
                        Thermodynamic properties: density, calorific value, viscosity, saturation temperature, GCV, NCV, flushing for hydrocarbons (H₂, CH₄, C₂H₆, C₂H₄, C₃H₆, C₃H₈, C₄H₁₀, N₂, O₂, H₂O).
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">GCV · NCV</span>
                            <span class="tool-tag">Density</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Thermocal/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>

                <!-- Hydraulic -->
                <div class="tool-card fade-in fade-in-delay-4">
                    <div class="tool-header">
                        <div class="tool-icon blue">
                            <i class="fas fa-water"></i>
                        </div>
                        <div class="tool-name">Hydraulic</div>
                    </div>
                    <div class="tool-desc">
                        Pressure drop & erosion velocity calculations for pipelines, supporting sizes from minimum up to 64" diameter.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">64" Pipe</span>
                            <span class="tool-tag">Pressure Drop</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Hydraulic-Line-Sizing/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>

                <!-- CV-calculation -->
                <div class="tool-card fade-in fade-in-delay-4">
                    <div class="tool-header">
                        <div class="tool-icon purple">
                            <i class="fas fa-sliders-h"></i>
                        </div>
                        <div class="tool-name">CV-calculation</div>
                    </div>
                    <div class="tool-desc">
                        Control valve CV calculation with existing plant control valve curve generation for optimal flow control.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">Valve Curve</span>
                            <span class="tool-tag">Flow Control</span>
                        </div>
                        <a href="https://gajuiitg.github.io/CV-calculation/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>

                <!-- Dataexport -->
                <div class="tool-card fade-in fade-in-delay-5">
                    <div class="tool-header">
                        <div class="tool-icon green">
                            <i class="fas fa-file-export"></i>
                        </div>
                        <div class="tool-name">Dataexport</div>
                    </div>
                    <div class="tool-desc">
                        Export data from trend archives — quick and reliable data extraction for process analysis and reporting.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">Trend Export</span>
                            <span class="tool-tag">Data Analysis</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Dataexport/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>

                <!-- Flow-cal -->
                <div class="tool-card fade-in fade-in-delay-5">
                    <div class="tool-header">
                        <div class="tool-icon blue">
                            <i class="fas fa-wind"></i>
                        </div>
                        <div class="tool-name">Flow-cal</div>
                    </div>
                    <div class="tool-desc">
                        All type of flow meter calculation and rating of existing flow meters.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">Flow Meter</span>
                            <span class="tool-tag">Meter Rating</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Flow-cal/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>

                <!-- Compressor & Turbine Efficiency -->
                <div class="tool-card fade-in fade-in-delay-5">
                    <div class="tool-header">
                        <div class="tool-icon orange">
                            <i class="fas fa-chart-line"></i>
                        </div>
                        <div class="tool-name">Compressor &amp; Turbine Efficiency</div>
                    </div>
                    <div class="tool-desc">
                        Compressor polytropic efficiency, condensing + extraction steam turbine efficiency, and pump/fan efficiency calculation in one web utility.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">Compressor</span>
                            <span class="tool-tag">Turbine</span>
                            <span class="tool-tag">Pump/Fan</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Compressor-and-Turbine-Efficiency/" target="_blank" class="launch-btn">
                            Launch <i class="fas fa-arrow-right"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer fade-in fade-in-delay-5">
            <div class="footer-top">Gajanand Yadav</div>
            <div class="footer-contact">
                <a href="mailto:gajanandiitg@gmail.com">
                    <i class="fas fa-envelope"></i>
                    gajanandiitg@gmail.com
                </a>
                <a href="tel:+918369354472">
                    <i class="fas fa-phone-alt"></i>
                    +91 8369354472
                </a>
                <span>
                    <i class="fas fa-map-marker-alt"></i>
                    Bharuch, India
                </span>
            </div>
            <div class="footer-bottom">
                <div class="footer-item">
                    <i class="fas fa-flask"></i>
                    Chemical Engineer
                </div>
                <span class="footer-divider"></span>
                <div class="footer-item">
                    <i class="fas fa-industry"></i>
                    Process & Thermodynamics
                </div>
                <span class="footer-divider"></span>
                <div class="footer-item">
                    <i class="fas fa-copyright"></i>
                    2026
                </div>
            </div>
        </div>
    </div>

    <script>
        // Particle animation
        const canvas = document.getElementById('particles');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resize() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resize();
        window.addEventListener('resize', resize);

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = (Math.random() - 0.5) * 0.3;
                this.speedY = (Math.random() - 0.5) * 0.3;
                this.opacity = Math.random() * 0.5 + 0.1;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                if (this.x > canvas.width) this.x = 0;
                if (this.x < 0) this.x = canvas.width;
                if (this.y > canvas.height) this.y = 0;
                if (this.y < 0) this.y = canvas.height;
            }
            draw() {
                ctx.fillStyle = `rgba(148, 163, 184, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles() {
            particles = [];
            const count = Math.min(window.innerWidth / 10, 100);
            for (let i = 0; i < count; i++) {
                particles.push(new Particle());
            }
        }
        initParticles();

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });

            // Draw connections
            for (let i = 0; i < particles.length; i++) {
                for (let j = i + 1; j < particles.length; j++) {
                    const dx = particles[i].x - particles[j].x;
                    const dy = particles[i].y - particles[j].y;
                    const dist = Math.sqrt(dx * dx + dy * dy);
                    if (dist < 150) {
                        ctx.strokeStyle = `rgba(148, 163, 184, ${0.1 * (1 - dist / 150)})`;
                        ctx.lineWidth = 0.5;
                        ctx.beginPath();
                        ctx.moveTo(particles[i].x, particles[i].y);
                        ctx.lineTo(particles[j].x, particles[j].y);
                        ctx.stroke();
                    }
                }
            }
            requestAnimationFrame(animate);
        }
        animate();

        // Intersection Observer for scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.tool-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
