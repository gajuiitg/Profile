<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Gajanand Yadav — Chemical Engineer, Process & Thermodynamics. Engineering calculators for PSV sizing, thermodynamic properties, hydraulics, control valves and data export.">
    <title>Gajanand Yadav · Process Engineer</title>
    <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 32 32'%3E%3Crect width='32' height='32' rx='4' fill='%230a0d10'/%3E%3Ccircle cx='16' cy='16' r='9' fill='none' stroke='%2322d3ee' stroke-width='2'/%3E%3Ccircle cx='16' cy='16' r='3' fill='%234ade80'/%3E%3C/svg%3E">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@500;600;700&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #0a0d10;
            --bg-panel: #12181f;
            --bg-panel-2: #171f27;
            --line: rgba(230, 237, 241, 0.07);
            --line-strong: rgba(230, 237, 241, 0.14);
            --text: #e6edf1;
            --text-dim: #7c8a94;
            --cyan: #22d3ee;
            --green: #4ade80;
            --amber: #fbbf24;
            --red: #f87171;
            --violet: #a78bfa;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        html { scroll-behavior: smooth; }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            line-height: 1.6;
            position: relative;
        }

        /* Mimic-panel grid backdrop */
        .grid-bg {
            position: fixed;
            inset: 0;
            z-index: -2;
            background-image:
                linear-gradient(var(--line) 1px, transparent 1px),
                linear-gradient(90deg, var(--line) 1px, transparent 1px);
            background-size: 42px 42px;
            mask-image: radial-gradient(ellipse 80% 60% at 50% 0%, black 40%, transparent 90%);
            -webkit-mask-image: radial-gradient(ellipse 80% 60% at 50% 0%, black 40%, transparent 90%);
        }

        .scanline {
            position: fixed;
            inset: 0;
            z-index: -1;
            pointer-events: none;
            background: repeating-linear-gradient(
                to bottom,
                rgba(255,255,255,0.012) 0px,
                rgba(255,255,255,0.012) 1px,
                transparent 1px,
                transparent 3px
            );
        }

        .container { max-width: 1160px; margin: 0 auto; padding: 0 1.5rem 3rem; }

        /* Status bar */
        .statusbar {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 1rem;
            flex-wrap: wrap;
            padding: 0.7rem 1.5rem;
            background: var(--bg-panel);
            border-bottom: 1px solid var(--line-strong);
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.78rem;
            color: var(--text-dim);
            letter-spacing: 0.02em;
        }

        .statusbar-left { display: flex; align-items: center; gap: 0.6rem; }

        .led {
            width: 8px; height: 8px; border-radius: 50%;
            background: var(--green);
            box-shadow: 0 0 6px var(--green), 0 0 2px var(--green);
            animation: pulse 2.4s ease-in-out infinite;
            flex-shrink: 0;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.35; }
        }

        .statusbar strong { color: var(--green); font-weight: 500; }
        .statusbar-mid { color: var(--text-dim); }
        .statusbar-right { display: flex; align-items: center; gap: 1.4rem; }
        #clock { color: var(--cyan); }

        @media (max-width: 640px) {
            .statusbar-mid { display: none; }
        }

        /* Hero */
        .hero {
            padding: 3.2rem 0 2.5rem;
            border-bottom: 1px solid var(--line);
        }

        .eyebrow {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.72rem;
            letter-spacing: 0.15em;
            color: var(--cyan);
            text-transform: uppercase;
            margin-bottom: 0.9rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .eyebrow::before {
            content: '';
            width: 18px;
            height: 1px;
            background: var(--cyan);
        }

        .name {
            font-family: 'Rajdhani', sans-serif;
            font-size: clamp(2.4rem, 6vw, 3.6rem);
            font-weight: 700;
            letter-spacing: -0.01em;
            color: var(--text);
            line-height: 1.05;
            margin-bottom: 0.6rem;
        }

        .role {
            font-size: 1.1rem;
            color: var(--text-dim);
            margin-bottom: 1.6rem;
        }

        .role span { color: var(--text); font-weight: 500; }

        .capsules {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
        }

        .capsule {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.74rem;
            padding: 0.4rem 0.8rem;
            border: 1px solid var(--line-strong);
            border-radius: 3px;
            color: var(--text-dim);
            background: var(--bg-panel);
            letter-spacing: 0.02em;
        }

        /* Section header */
        .section { margin-top: 3rem; }

        .section-header {
            display: flex;
            align-items: baseline;
            gap: 0.9rem;
            margin-bottom: 1.8rem;
        }

        .section-tag {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.72rem;
            color: var(--text-dim);
            border: 1px solid var(--line-strong);
            padding: 0.15rem 0.5rem;
            border-radius: 3px;
        }

        .section-title {
            font-family: 'Rajdhani', sans-serif;
            font-size: 1.5rem;
            font-weight: 600;
            letter-spacing: 0.01em;
            text-transform: uppercase;
        }

        .section-line {
            flex: 1;
            height: 1px;
            background: var(--line-strong);
        }

        /* Tool grid / faceplates */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.1rem;
        }

        .tool-card {
            background: var(--bg-panel);
            border: 1px solid var(--line-strong);
            border-radius: 8px;
            padding: 1.3rem 1.4rem 1.4rem;
            position: relative;
            transition: border-color 0.25s ease, transform 0.25s ease, box-shadow 0.25s ease;
        }

        .tool-card::before {
            content: '';
            position: absolute;
            top: -1px; left: -1px;
            width: calc(100% + 2px);
            height: 3px;
            border-radius: 8px 8px 0 0;
            background: var(--accent, var(--cyan));
        }

        .tool-card:hover {
            transform: translateY(-3px);
            border-color: var(--accent, var(--cyan));
            box-shadow: 0 12px 28px -12px rgba(0,0,0,0.55);
        }

        .tool-topline {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 0.9rem;
        }

        .tool-tagno {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.72rem;
            color: var(--accent, var(--cyan));
            letter-spacing: 0.03em;
        }

        .tool-led {
            width: 6px; height: 6px; border-radius: 50%;
            background: var(--accent, var(--cyan));
            box-shadow: 0 0 5px var(--accent, var(--cyan));
            animation: pulse 2.8s ease-in-out infinite;
        }

        .tool-header {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            margin-bottom: 0.8rem;
        }

        .tool-icon {
            width: 40px; height: 40px;
            border-radius: 6px;
            display: flex; align-items: center; justify-content: center;
            font-size: 1.05rem;
            background: color-mix(in srgb, var(--accent, var(--cyan)) 14%, transparent);
            border: 1px solid color-mix(in srgb, var(--accent, var(--cyan)) 30%, transparent);
            color: var(--accent, var(--cyan));
            flex-shrink: 0;
        }

        .tool-name {
            font-family: 'Rajdhani', sans-serif;
            font-size: 1.2rem;
            font-weight: 600;
        }

        .tool-desc {
            color: var(--text-dim);
            font-size: 0.9rem;
            line-height: 1.55;
            margin-bottom: 1.2rem;
            min-height: 3.3em;
        }

        .tool-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 0.7rem;
            padding-top: 0.9rem;
            border-top: 1px dashed var(--line);
        }

        .tool-tags { display: flex; gap: 0.4rem; flex-wrap: wrap; }

        .tool-tag {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.68rem;
            padding: 0.22rem 0.55rem;
            border-radius: 3px;
            background: rgba(255,255,255,0.03);
            color: var(--text-dim);
            border: 1px solid var(--line);
        }

        .launch-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.45rem;
            background: transparent;
            color: var(--accent, var(--cyan));
            text-decoration: none;
            padding: 0.45rem 0.9rem;
            border-radius: 4px;
            font-family: 'JetBrains Mono', monospace;
            font-weight: 600;
            font-size: 0.76rem;
            letter-spacing: 0.05em;
            text-transform: uppercase;
            border: 1px solid var(--accent, var(--cyan));
            transition: background 0.2s ease, color 0.2s ease;
        }

        .launch-btn:hover {
            background: var(--accent, var(--cyan));
            color: var(--bg);
        }

        .launch-btn i { font-size: 0.7rem; }

        /* Footer */
        .footer {
            margin-top: 3.5rem;
            padding: 1.8rem 0 0.5rem;
            border-top: 1px solid var(--line);
        }

        .footer-panel {
            background: var(--bg-panel);
            border: 1px solid var(--line-strong);
            border-radius: 8px;
            padding: 1.4rem 1.6rem;
            display: flex;
            flex-wrap: wrap;
            gap: 1.4rem 2.2rem;
            align-items: center;
            justify-content: space-between;
        }

        .footer-id {
            font-family: 'Rajdhani', sans-serif;
            font-size: 1.15rem;
            font-weight: 600;
        }

        .footer-id .sub {
            display: block;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.7rem;
            color: var(--text-dim);
            font-weight: 400;
            letter-spacing: 0.04em;
            margin-top: 0.2rem;
        }

        .footer-fields {
            display: flex;
            flex-wrap: wrap;
            gap: 1.3rem;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.78rem;
        }

        .footer-fields a, .footer-fields span {
            color: var(--text-dim);
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.4rem;
        }

        .footer-fields a:hover { color: var(--cyan); }
        .footer-fields i { color: var(--cyan); font-size: 0.75rem; }

        .footer-meta {
            text-align: center;
            margin-top: 1.2rem;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.7rem;
            color: var(--text-dim);
            opacity: 0.6;
        }

        @media (max-width: 560px) {
            .footer-panel { flex-direction: column; align-items: flex-start; }
        }

        /* Entrance */
        .fade-in { opacity: 0; transform: translateY(16px); animation: fadeInUp 0.6s ease forwards; }
        .fade-in-delay-1 { animation-delay: 0.05s; }
        .fade-in-delay-2 { animation-delay: 0.15s; }
        @keyframes fadeInUp { to { opacity: 1; transform: translateY(0); } }

        @media (prefers-reduced-motion: reduce) {
            .led, .tool-led { animation: none; }
            .fade-in { animation: none; opacity: 1; transform: none; }
            html { scroll-behavior: auto; }
        }

        a:focus-visible, .launch-btn:focus-visible {
            outline: 2px solid var(--cyan);
            outline-offset: 2px;
        }
    </style>
</head>
<body>
    <div class="grid-bg"></div>
    <div class="scanline"></div>

    <div class="statusbar">
        <div class="statusbar-left">
            <span class="led"></span>
            <strong>SYSTEM NORMAL</strong>
        </div>
        <div class="statusbar-mid">UNIT: GCU &middot; DAHEJ MANUFACTURING DIVISION</div>
        <div class="statusbar-right">
            <span id="clock">--:--:--</span>
        </div>
    </div>

    <div class="container">
        <!-- Hero -->
        <div class="hero fade-in fade-in-delay-1">
            <div class="eyebrow">Process Engineering &middot; Personal Toolkit</div>
            <h1 class="name">Gajanand Yadav</h1>
            <div class="role">Chemical Engineer &mdash; <span>Process &amp; Thermodynamics</span></div>
            <div class="capsules">
                <span class="capsule">Process Simulation</span>
                <span class="capsule">Thermodynamics</span>
                <span class="capsule">Control Valves</span>
                <span class="capsule">Reliability</span>
            </div>
        </div>

        <!-- Tools -->
        <div class="section fade-in fade-in-delay-2">
            <div class="section-header">
                <span class="section-tag">05 ACTIVE</span>
                <div class="section-title">Engineering Tools</div>
                <div class="section-line"></div>
            </div>

            <div class="tools-grid">
                <!-- PSV-cal -->
                <div class="tool-card" style="--accent: var(--red);">
                    <div class="tool-topline">
                        <span class="tool-tagno">TAG: PSV-2101</span>
                        <span class="tool-led"></span>
                    </div>
                    <div class="tool-header">
                        <div class="tool-icon"><i class="fas fa-exclamation-triangle"></i></div>
                        <div class="tool-name">PSV-cal</div>
                    </div>
                    <div class="tool-desc">
                        API RP 520/521 pressure safety valve sizing across all relief scenarios &mdash; fire, blocked outlet, control valve failure and more.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">PSV SIZING</span>
                            <span class="tool-tag">SAFETY</span>
                        </div>
                        <a href="https://gajuiitg.github.io/PSV-cal/" target="_blank" rel="noopener" class="launch-btn">Launch <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>

                <!-- Thermocal -->
                <div class="tool-card" style="--accent: var(--amber);">
                    <div class="tool-topline">
                        <span class="tool-tagno">TAG: TI-3040</span>
                        <span class="tool-led"></span>
                    </div>
                    <div class="tool-header">
                        <div class="tool-icon"><i class="fas fa-thermometer-half"></i></div>
                        <div class="tool-name">Thermocal</div>
                    </div>
                    <div class="tool-desc">
                        Density, GCV/NCV, viscosity and saturation temperature for H&#8322;, CH&#8324;, C&#8322;H&#8326;, C&#8322;H&#8324;, C&#8323;H&#8326;, C&#8323;H&#8328;, C&#8324;H&#8321;&#8320;, N&#8322;, O&#8322;, H&#8322;O.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">GCV &middot; NCV</span>
                            <span class="tool-tag">DENSITY</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Thermocal/" target="_blank" rel="noopener" class="launch-btn">Launch <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>

                <!-- Hydraulic -->
                <div class="tool-card" style="--accent: var(--cyan);">
                    <div class="tool-topline">
                        <span class="tool-tagno">TAG: PDIT-1187</span>
                        <span class="tool-led"></span>
                    </div>
                    <div class="tool-header">
                        <div class="tool-icon"><i class="fas fa-water"></i></div>
                        <div class="tool-name">Hydraulic</div>
                    </div>
                    <div class="tool-desc">
                        Pressure drop and erosion velocity for pipelines, from minimum bore up to 64&Prime; diameter.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">64&Prime; PIPE</span>
                            <span class="tool-tag">PRESSURE DROP</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Hydraulic/" target="_blank" rel="noopener" class="launch-btn">Launch <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>

                <!-- CV-calculation -->
                <div class="tool-card" style="--accent: var(--violet);">
                    <div class="tool-topline">
                        <span class="tool-tagno">TAG: FCV-2209</span>
                        <span class="tool-led"></span>
                    </div>
                    <div class="tool-header">
                        <div class="tool-icon"><i class="fas fa-sliders-h"></i></div>
                        <div class="tool-name">CV-calculation</div>
                    </div>
                    <div class="tool-desc">
                        Control valve Cv sizing with plant control-valve curve generation for existing installed valves.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">VALVE CURVE</span>
                            <span class="tool-tag">FLOW CONTROL</span>
                        </div>
                        <a href="https://gajuiitg.github.io/CV-calculation/" target="_blank" rel="noopener" class="launch-btn">Launch <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>

                <!-- Dataexport -->
                <div class="tool-card" style="--accent: var(--green);">
                    <div class="tool-topline">
                        <span class="tool-tagno">TAG: HIS-4401</span>
                        <span class="tool-led"></span>
                    </div>
                    <div class="tool-header">
                        <div class="tool-icon"><i class="fas fa-file-export"></i></div>
                        <div class="tool-name">Dataexport</div>
                    </div>
                    <div class="tool-desc">
                        Fast, reliable extraction of trend archive data for process analysis and reporting.
                    </div>
                    <div class="tool-footer">
                        <div class="tool-tags">
                            <span class="tool-tag">TREND EXPORT</span>
                            <span class="tool-tag">DATA ANALYSIS</span>
                        </div>
                        <a href="https://gajuiitg.github.io/Dataexport/" target="_blank" rel="noopener" class="launch-btn">Launch <i class="fas fa-arrow-right"></i></a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div class="footer">
            <div class="footer-panel">
                <div class="footer-id">
                    Gajanand Yadav
                    <span class="sub">CHEMICAL ENGINEER &middot; PROCESS &amp; THERMODYNAMICS</span>
                </div>
                <div class="footer-fields">
                    <a href="mailto:gajanandiitg@gmail.com"><i class="fas fa-envelope"></i>gajanandiitg@gmail.com</a>
                    <a href="tel:+918369354472"><i class="fas fa-phone-alt"></i>+91 8369354472</a>
                    <span><i class="fas fa-map-marker-alt"></i>Bharuch, India</span>
                </div>
            </div>
            <div class="footer-meta">&copy; 2026 &middot; Built &amp; maintained by Gajanand Yadav</div>
        </div>
    </div>

    <script>
        function tick() {
            const now = new Date();
            const opts = { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: false, timeZone: 'Asia/Kolkata' };
            document.getElementById('clock').textContent = now.toLocaleTimeString('en-GB', opts) + ' IST';
        }
        tick();
        setInterval(tick, 1000);
    </script>
</body>
</html>
