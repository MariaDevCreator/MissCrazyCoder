<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MissCrazyCoder - GitHub Banner</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Share+Tech+Mono&family=Rajdhani:wght@400;600&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #0a0a0f;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    font-family: 'Share Tech Mono', monospace;
  }

  .banner {
    width: 1280px;
    height: 400px;
    position: relative;
    overflow: hidden;
    background: linear-gradient(135deg, #020212 0%, #0d0a1f 40%, #0a0d20 70%, #050215 100%);
    border-radius: 12px;
    border: 1px solid rgba(120, 60, 255, 0.3);
  }

  /* Animated grid floor */
  .grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(80, 30, 200, 0.12) 1px, transparent 1px),
      linear-gradient(90deg, rgba(80, 30, 200, 0.12) 1px, transparent 1px);
    background-size: 40px 40px;
    animation: gridShift 8s linear infinite;
  }

  @keyframes gridShift {
    0% { background-position: 0 0; }
    100% { background-position: 40px 40px; }
  }

  /* Deep space nebula glow */
  .nebula {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 80% at 70% 50%, rgba(100, 30, 255, 0.18) 0%, transparent 60%),
      radial-gradient(ellipse 40% 60% at 20% 40%, rgba(0, 160, 255, 0.15) 0%, transparent 55%),
      radial-gradient(ellipse 30% 40% at 85% 20%, rgba(255, 60, 180, 0.10) 0%, transparent 50%);
  }

  /* Scan lines */
  .scanlines {
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.08) 2px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 50;
  }

  /* Left panel: coder figure area */
  .left-panel {
    position: absolute;
    left: 0;
    top: 0;
    width: 440px;
    height: 100%;
  }

  /* Desk surface */
  .desk {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 90px;
    background: linear-gradient(180deg, rgba(20,10,50,0.9) 0%, rgba(10,5,30,1) 100%);
    border-top: 1px solid rgba(120,60,255,0.5);
    box-shadow: 0 -5px 30px rgba(100,30,255,0.3);
  }

  /* Monitor screens */
  .monitor-group {
    position: absolute;
    bottom: 80px;
    left: 20px;
    display: flex;
    gap: 8px;
    align-items: flex-end;
  }

  .monitor {
    border-radius: 4px;
    background: #030315;
    border: 1px solid rgba(100, 50, 255, 0.6);
    box-shadow:
      0 0 20px rgba(80, 30, 255, 0.4),
      0 0 60px rgba(80, 30, 255, 0.15),
      inset 0 0 20px rgba(0,0,0,0.8);
    overflow: hidden;
    position: relative;
    flex-shrink: 0;
  }

  .monitor-main {
    width: 180px;
    height: 120px;
  }

  .monitor-side {
    width: 120px;
    height: 90px;
  }

  .monitor-stand {
    height: 12px;
    background: linear-gradient(180deg, rgba(80,40,160,0.8), rgba(40,20,80,0.8));
    border-radius: 0 0 4px 4px;
    width: 40px;
    margin: 0 auto;
    border: 1px solid rgba(100,50,200,0.3);
    border-top: none;
  }

  .monitor-wrap {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  /* Code on monitor */
  .code-screen {
    padding: 6px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 5px;
    line-height: 1.6;
    color: rgba(100, 255, 180, 0.8);
    animation: codeScroll 4s linear infinite;
    height: 100%;
    overflow: hidden;
  }

  .code-screen .line { display: block; white-space: nowrap; }
  .code-screen .kw { color: #a57fff; }
  .code-screen .fn { color: #60d0ff; }
  .code-screen .str { color: #ffd080; }
  .code-screen .cm { color: rgba(100,255,180,0.4); }
  .code-screen .num { color: #ff8060; }

  @keyframes codeScroll {
    0% { transform: translateY(0); }
    100% { transform: translateY(-40%); }
  }

  /* Side monitor - terminal style */
  .terminal-screen {
    padding: 5px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 5px;
    line-height: 1.7;
    color: rgba(0, 220, 100, 0.9);
    background: #000a02;
    height: 100%;
  }

  .terminal-screen .cmd { color: #00ff88; }
  .terminal-screen .out { color: rgba(0,200,100,0.6); }
  .terminal-screen .cursor {
    display: inline-block;
    width: 4px;
    height: 7px;
    background: #00ff88;
    animation: blink 1s step-end infinite;
    vertical-align: middle;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* Character silhouette */
  .character {
    position: absolute;
    bottom: 78px;
    left: 230px;
    width: 120px;
    height: 180px;
    z-index: 10;
  }

  .character svg {
    width: 100%;
    height: 100%;
    filter: drop-shadow(0 0 20px rgba(140, 80, 255, 0.8)) drop-shadow(0 0 40px rgba(80, 180, 255, 0.4));
  }

  /* Keyboard on desk */
  .keyboard {
    position: absolute;
    bottom: 18px;
    left: 210px;
    width: 140px;
    height: 36px;
    background: linear-gradient(180deg, rgba(60,30,120,0.9), rgba(30,15,70,0.9));
    border-radius: 4px;
    border: 1px solid rgba(120,80,255,0.5);
    box-shadow: 0 0 15px rgba(100,50,255,0.3);
  }

  .keyboard::after {
    content: '';
    position: absolute;
    inset: 4px 6px;
    background: repeating-linear-gradient(
      90deg,
      rgba(120,80,255,0.2) 0px, rgba(120,80,255,0.2) 8px,
      transparent 8px, transparent 10px
    ),
    repeating-linear-gradient(
      0deg,
      rgba(120,80,255,0.2) 0px, rgba(120,80,255,0.2) 6px,
      transparent 6px, transparent 8px
    );
    border-radius: 2px;
  }

  /* Right panel: text and tech icons */
  .right-panel {
    position: absolute;
    right: 0;
    top: 0;
    width: 840px;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 30px 50px 30px 60px;
  }

  /* Floating code snippets */
  .float-code {
    position: absolute;
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: rgba(100, 200, 255, 0.25);
    white-space: nowrap;
    pointer-events: none;
    animation: floatUp 6s ease-in-out infinite;
  }

  @keyframes floatUp {
    0%, 100% { transform: translateY(0) rotate(var(--rot)); opacity: 0.2; }
    50% { transform: translateY(-12px) rotate(var(--rot)); opacity: 0.35; }
  }

  .fc1 { top: 30px; right: 520px; --rot: -3deg; animation-delay: 0s; color: rgba(140,100,255,0.3); }
  .fc2 { top: 80px; right: 200px; --rot: 2deg; animation-delay: 1.2s; color: rgba(0,200,255,0.25); }
  .fc3 { top: 160px; right: 440px; --rot: -1deg; animation-delay: 2.4s; }
  .fc4 { bottom: 100px; right: 320px; --rot: 4deg; animation-delay: 0.8s; color: rgba(255,100,200,0.2); }
  .fc5 { bottom: 50px; right: 120px; --rot: -2deg; animation-delay: 3s; }
  .fc6 { top: 50px; right: 80px; --rot: 1deg; animation-delay: 1.8s; color: rgba(100,255,180,0.2); }

  /* Header tag line */
  .tag-line {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: rgba(100, 200, 255, 0.7);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 8px;
    animation: fadeSlide 1s ease both;
  }

  @keyframes fadeSlide {
    from { opacity: 0; transform: translateX(-20px); }
    to { opacity: 1; transform: translateX(0); }
  }

  /* Main name */
  .name {
    font-family: 'Orbitron', monospace;
    font-size: 62px;
    font-weight: 900;
    line-height: 1;
    letter-spacing: -1px;
    background: linear-gradient(135deg, #c084fc 0%, #818cf8 30%, #38bdf8 60%, #34d399 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    position: relative;
    animation: fadeSlide 1.2s ease 0.2s both;
    filter: drop-shadow(0 0 30px rgba(140, 80, 255, 0.5));
    margin-bottom: 10px;
  }

  .name::after {
    content: 'MissCrazyCoder';
    position: absolute;
    left: 2px;
    top: 2px;
    background: linear-gradient(135deg, rgba(200,100,255,0.15), rgba(0,200,255,0.15));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    z-index: -1;
  }

  /* Glitch effect on hover */
  .name:hover {
    animation: glitch 0.3s ease infinite;
  }

  @keyframes glitch {
    0%,100% { filter: drop-shadow(0 0 30px rgba(140, 80, 255, 0.5)); transform: translate(0); }
    20% { filter: drop-shadow(-3px 0 rgba(0,255,255,0.8)) drop-shadow(3px 0 rgba(255,0,200,0.8)); transform: translate(2px, -1px); }
    40% { filter: drop-shadow(3px 0 rgba(0,255,255,0.8)) drop-shadow(-3px 0 rgba(255,0,200,0.8)); transform: translate(-2px, 1px); }
    60% { filter: drop-shadow(-2px 0 rgba(255,0,200,0.6)); transform: translate(1px); }
    80% { filter: drop-shadow(2px 0 rgba(0,255,255,0.6)); transform: translate(-1px); }
  }

  /* Tagline */
  .tagline {
    font-family: 'Rajdhani', sans-serif;
    font-size: 18px;
    font-weight: 600;
    letter-spacing: 8px;
    color: transparent;
    background: linear-gradient(90deg, rgba(192,132,252,0.9), rgba(56,189,248,0.9), rgba(52,211,153,0.9));
    -webkit-background-clip: text;
    background-clip: text;
    text-transform: uppercase;
    margin-bottom: 24px;
    animation: fadeSlide 1.2s ease 0.4s both;
  }

  .tagline .dot {
    color: rgba(255,150,80,0.9);
    -webkit-text-fill-color: rgba(255,150,80,0.9);
    margin: 0 4px;
  }

  /* Tech stack pills row */
  .tech-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 20px;
    animation: fadeSlide 1.2s ease 0.6s both;
  }

  .tech-pill {
    display: flex;
    align-items: center;
    gap: 5px;
    padding: 4px 10px;
    border-radius: 3px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    letter-spacing: 1px;
    border: 1px solid;
    transition: all 0.3s ease;
    cursor: default;
    position: relative;
    overflow: hidden;
  }

  .tech-pill::before {
    content: '';
    position: absolute;
    inset: 0;
    background: currentColor;
    opacity: 0;
    transition: opacity 0.3s;
  }

  .tech-pill:hover::before { opacity: 0.15; }

  .tp-java { color: #f89820; border-color: rgba(248,152,32,0.4); background: rgba(248,152,32,0.08); }
  .tp-spring { color: #6db33f; border-color: rgba(109,179,63,0.4); background: rgba(109,179,63,0.08); }
  .tp-docker { color: #2496ed; border-color: rgba(36,150,237,0.4); background: rgba(36,150,237,0.08); }
  .tp-k8s { color: #326ce5; border-color: rgba(50,108,229,0.4); background: rgba(50,108,229,0.08); }
  .tp-aws { color: #ff9900; border-color: rgba(255,153,0,0.4); background: rgba(255,153,0,0.08); }
  .tp-git { color: #f05032; border-color: rgba(240,80,50,0.4); background: rgba(240,80,50,0.08); }
  .tp-micro { color: #c084fc; border-color: rgba(192,132,252,0.4); background: rgba(192,132,252,0.08); }
  .tp-cloud { color: #38bdf8; border-color: rgba(56,189,248,0.4); background: rgba(56,189,248,0.08); }

  .pill-icon { font-size: 12px; }

  /* Stats row */
  .stats-row {
    display: flex;
    gap: 24px;
    animation: fadeSlide 1.2s ease 0.8s both;
  }

  .stat {
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .stat-num {
    font-family: 'Orbitron', monospace;
    font-size: 20px;
    font-weight: 700;
    color: rgba(140, 100, 255, 1);
    line-height: 1;
  }

  .stat-label {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: rgba(150, 150, 200, 0.6);
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .stat-sep {
    width: 1px;
    height: 36px;
    background: linear-gradient(180deg, transparent, rgba(100,60,255,0.5), transparent);
    align-self: center;
  }

  /* Neon edge glow on banner */
  .edge-glow {
    position: absolute;
    inset: 0;
    border-radius: 12px;
    box-shadow:
      inset 0 0 60px rgba(100,30,255,0.15),
      inset 0 0 120px rgba(0,100,255,0.08);
    pointer-events: none;
    z-index: 40;
  }

  /* Vertical neon line separator */
  .v-line {
    position: absolute;
    left: 440px;
    top: 10%;
    bottom: 10%;
    width: 1px;
    background: linear-gradient(180deg,
      transparent 0%,
      rgba(120, 60, 255, 0.6) 20%,
      rgba(0, 180, 255, 0.8) 50%,
      rgba(120, 60, 255, 0.6) 80%,
      transparent 100%
    );
    box-shadow: 0 0 8px rgba(100, 60, 255, 0.8), 0 0 20px rgba(0, 180, 255, 0.4);
    z-index: 20;
  }

  /* Particle dots */
  .particles {
    position: absolute;
    inset: 0;
    pointer-events: none;
  }

  .particle {
    position: absolute;
    width: 2px;
    height: 2px;
    border-radius: 50%;
    background: rgba(140, 80, 255, 0.8);
    animation: particlePulse var(--dur) ease-in-out infinite var(--delay);
  }

  @keyframes particlePulse {
    0%,100% { opacity: 0.2; transform: scale(1); }
    50% { opacity: 0.9; transform: scale(2); }
  }

  /* Corner decorations */
  .corner {
    position: absolute;
    width: 40px;
    height: 40px;
    z-index: 30;
  }

  .corner-tl {
    top: 8px; left: 8px;
    border-top: 2px solid rgba(120,80,255,0.8);
    border-left: 2px solid rgba(120,80,255,0.8);
    border-radius: 4px 0 0 0;
  }

  .corner-tr {
    top: 8px; right: 8px;
    border-top: 2px solid rgba(0,180,255,0.8);
    border-right: 2px solid rgba(0,180,255,0.8);
    border-radius: 0 4px 0 0;
  }

  .corner-bl {
    bottom: 8px; left: 8px;
    border-bottom: 2px solid rgba(0,180,255,0.8);
    border-left: 2px solid rgba(0,180,255,0.8);
    border-radius: 0 0 0 4px;
  }

  .corner-br {
    bottom: 8px; right: 8px;
    border-bottom: 2px solid rgba(120,80,255,0.8);
    border-right: 2px solid rgba(120,80,255,0.8);
    border-radius: 0 0 4px 0;
  }

  /* Cloud / AI decorative rings */
  .tech-ring {
    position: absolute;
    border-radius: 50%;
    border: 1px solid;
    animation: ringPulse 3s ease-in-out infinite;
  }

  @keyframes ringPulse {
    0%,100% { opacity: 0.3; transform: scale(1); }
    50% { opacity: 0.6; transform: scale(1.05); }
  }

  .ring1 {
    width: 80px; height: 80px;
    top: 20px; right: 460px;
    border-color: rgba(120,80,255,0.4);
    animation-delay: 0s;
  }

  .ring2 {
    width: 50px; height: 50px;
    top: 30px; right: 470px;
    border-color: rgba(0,180,255,0.3);
    animation-delay: 0.5s;
  }

  .ring3 {
    width: 30px; height: 30px;
    top: 40px; right: 480px;
    border-color: rgba(200,100,255,0.5);
    animation-delay: 1s;
  }

  /* Binary rain far bg */
  .binary-col {
    position: absolute;
    top: 0;
    bottom: 0;
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    color: rgba(80, 200, 100, 0.08);
    overflow: hidden;
    writing-mode: vertical-rl;
    letter-spacing: 6px;
    animation: binFall linear infinite;
  }

  @keyframes binFall {
    from { transform: translateY(-100%); }
    to { transform: translateY(100%); }
  }

  /* GitHub handle bottom */
  .github-handle {
    position: absolute;
    bottom: 14px;
    right: 50px;
    font-family: 'Share Tech Mono', monospace;
    font-size: 10px;
    color: rgba(100, 150, 255, 0.5);
    letter-spacing: 2px;
    z-index: 20;
  }

  /* Status indicator */
  .status-dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    background: #22c55e;
    margin-right: 5px;
    animation: statusPulse 2s ease-in-out infinite;
    vertical-align: middle;
  }

  @keyframes statusPulse {
    0%,100% { box-shadow: 0 0 0 0 rgba(34,197,94,0.6); }
    50% { box-shadow: 0 0 0 4px rgba(34,197,94,0); }
  }

</style>
</head>
<body>

<div class="banner">

  <!-- Binary rain columns (decorative bg) -->
  <div class="binary-col" style="left:5%; animation-duration:12s;">01001101 01101001</div>
  <div class="binary-col" style="left:12%; animation-duration:9s; animation-delay:-3s;">10110011 00110101</div>
  <div class="binary-col" style="left:60%; animation-duration:14s; animation-delay:-6s;">01011010 11001101</div>
  <div class="binary-col" style="left:75%; animation-duration:10s; animation-delay:-2s;">00111011 10101010</div>
  <div class="binary-col" style="left:90%; animation-duration:11s; animation-delay:-5s;">11010100 01101100</div>

  <!-- Grid + Nebula bg -->
  <div class="grid-bg"></div>
  <div class="nebula"></div>

  <!-- Particles -->
  <div class="particles">
    <div class="particle" style="top:15%;left:48%;--dur:2.1s;--delay:0s;"></div>
    <div class="particle" style="top:70%;left:52%;--dur:2.8s;--delay:0.5s;background:rgba(0,180,255,0.8);"></div>
    <div class="particle" style="top:35%;left:55%;--dur:1.9s;--delay:1s;background:rgba(255,100,200,0.8);"></div>
    <div class="particle" style="top:55%;left:44%;--dur:2.4s;--delay:1.5s;"></div>
    <div class="particle" style="top:25%;left:72%;--dur:3s;--delay:0.3s;background:rgba(0,255,150,0.6);"></div>
    <div class="particle" style="top:80%;left:35%;--dur:2.2s;--delay:0.8s;background:rgba(0,180,255,0.8);"></div>
    <div class="particle" style="top:10%;left:82%;--dur:2.6s;--delay:1.2s;"></div>
    <div class="particle" style="top:60%;left:88%;--dur:1.8s;--delay:0.6s;background:rgba(255,180,80,0.7);"></div>
  </div>

  <!-- Tech rings (AI/cloud visual motif) -->
  <div class="tech-ring ring1"></div>
  <div class="tech-ring ring2"></div>
  <div class="tech-ring ring3"></div>

  <!-- LEFT PANEL: Desk scene -->
  <div class="left-panel">

    <!-- Monitor group -->
    <div class="monitor-group">
      <!-- Side monitor left -->
      <div class="monitor-wrap">
        <div class="monitor monitor-side">
          <div class="terminal-screen">
            <span class="cmd">$ kubectl get pods</span><br>
            <span class="out">NAME          READY</span><br>
            <span class="out">api-pod-1     1/1</span><br>
            <span class="out">db-pod-2      1/1</span><br>
            <span class="out">$ docker ps</span><br>
            <span class="out">CONTAINER ID</span><br>
            <span class="out">a8f2c 3306/tcp</span><br>
            <span class="cmd">$ git status</span><br>
            <span class="out">On branch main</span><br>
            <span class="cursor"></span>
          </div>
        </div>
        <div class="monitor-stand"></div>
      </div>

      <!-- Main monitor center -->
      <div class="monitor-wrap">
        <div class="monitor monitor-main">
          <div class="code-screen">
            <span class="line"><span class="cm">// MissCrazyCoder</span></span>
            <span class="line"><span class="kw">@RestController</span></span>
            <span class="line"><span class="kw">@Service</span></span>
            <span class="line"><span class="kw">public class</span> <span class="fn">ApiService</span> {</span>
            <span class="line">  <span class="kw">private final</span> <span class="fn">CloudClient</span> aws;</span>
            <span class="line"></span>
            <span class="line">  <span class="kw">@GetMapping</span>(<span class="str">"/api/v1"</span>)</span>
            <span class="line">  <span class="kw">public</span> <span class="fn">Response</span> handle() {</span>
            <span class="line">    <span class="kw">return</span> aws.<span class="fn">deploy</span>(</span>
            <span class="line">      <span class="fn">new</span> <span class="fn">MicroService</span>(</span>
            <span class="line">        <span class="str">"prod"</span>, <span class="num">8080</span>));</span>
            <span class="line">  }</span>
            <span class="line">}</span>
            <span class="line"><span class="cm">// Docker: building...</span></span>
            <span class="line"><span class="fn">FROM</span> openjdk:<span class="num">17</span></span>
            <span class="line"><span class="fn">COPY</span> app.jar /app/</span>
            <span class="line"><span class="fn">RUN</span> ./gradlew build</span>
            <span class="line"><span class="kw">@SpringBootApp</span></span>
            <span class="line"><span class="fn">k8s.deploy</span>(<span class="str">"cluster"</span>)</span>
          </div>
        </div>
        <div class="monitor-stand"></div>
      </div>
    </div>

    <!-- Keyboard -->
    <div class="keyboard"></div>

    <!-- Desk surface -->
    <div class="desk"></div>

    <!-- Character: stylized female coder silhouette (SVG) -->
    <div class="character">
      <svg viewBox="0 0 100 160" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="bodyGrad" x1="0%" y1="0%" x2="100%" y2="100%">
            <stop offset="0%" stop-color="#c084fc"/>
            <stop offset="50%" stop-color="#818cf8"/>
            <stop offset="100%" stop-color="#38bdf8"/>
          </linearGradient>
          <linearGradient id="hairGrad" x1="0%" y1="0%" x2="100%" y2="100%">
            <stop offset="0%" stop-color="#a855f7"/>
            <stop offset="100%" stop-color="#7c3aed"/>
          </linearGradient>
          <linearGradient id="glowGrad" x1="0%" y1="0%" x2="0%" y2="100%">
            <stop offset="0%" stop-color="rgba(192,132,252,0.6)"/>
            <stop offset="100%" stop-color="rgba(56,189,248,0.0)"/>
          </linearGradient>
          <filter id="glow">
            <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
            <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
          </filter>
        </defs>

        <!-- Body glow aura -->
        <ellipse cx="50" cy="90" rx="35" ry="55" fill="url(#glowGrad)" opacity="0.4"/>

        <!-- Legs -->
        <rect x="36" y="118" width="10" height="38" rx="4" fill="url(#bodyGrad)" opacity="0.85"/>
        <rect x="54" y="118" width="10" height="38" rx="4" fill="url(#bodyGrad)" opacity="0.85"/>

        <!-- Shoes -->
        <ellipse cx="41" cy="156" rx="8" ry="4" fill="#1e1040"/>
        <ellipse cx="59" cy="156" rx="8" ry="4" fill="#1e1040"/>

        <!-- Torso / hoodie -->
        <path d="M30 75 Q28 95 30 118 L70 118 Q72 95 70 75 Q60 70 50 68 Q40 70 30 75Z"
              fill="url(#bodyGrad)" filter="url(#glow)"/>

        <!-- Hoodie details -->
        <path d="M50 68 L50 90 M46 76 L54 76" stroke="rgba(255,255,255,0.2)" stroke-width="1" fill="none"/>

        <!-- Left arm (reaching toward keyboard) -->
        <path d="M30 78 Q15 90 12 108 Q16 112 20 110 Q26 96 34 86Z"
              fill="url(#bodyGrad)" opacity="0.9"/>
        <!-- Hand left -->
        <ellipse cx="16" cy="111" rx="5" ry="4" fill="#c084fc" opacity="0.9"/>

        <!-- Right arm (raised/relaxed) -->
        <path d="M70 78 Q82 82 88 75 Q88 68 84 66 Q78 72 68 80Z"
              fill="url(#bodyGrad)" opacity="0.9"/>
        <!-- Hand right -->
        <ellipse cx="87" cy="71" rx="5" ry="4" fill="#c084fc" opacity="0.9"/>

        <!-- Neck -->
        <rect x="46" y="58" width="8" height="12" rx="3" fill="#c084fc"/>

        <!-- Head -->
        <ellipse cx="50" cy="46" rx="20" ry="22" fill="#c084fc" filter="url(#glow)"/>

        <!-- Hair — long, flowing down -->
        <path d="M30 38 Q25 30 28 18 Q34 8 50 6 Q66 8 72 18 Q75 30 70 38
                 Q72 55 68 70 Q60 80 55 82 L55 60 Q68 55 70 38
                 Q66 30 50 28 Q34 30 30 38Z"
              fill="url(#hairGrad)" opacity="0.95"/>

        <!-- Hair highlights -->
        <path d="M32 20 Q38 10 50 8" stroke="rgba(216,180,254,0.4)" stroke-width="1.5" fill="none"/>

        <!-- Face features -->
        <!-- Eyes (glasses style) -->
        <rect x="38" y="42" width="8" height="5" rx="2.5" fill="none" stroke="#38bdf8" stroke-width="1.2" opacity="0.9"/>
        <rect x="54" y="42" width="8" height="5" rx="2.5" fill="none" stroke="#38bdf8" stroke-width="1.2" opacity="0.9"/>
        <line x1="46" y1="44" x2="54" y2="44" stroke="#38bdf8" stroke-width="1" opacity="0.7"/>
        <!-- Eye shine -->
        <circle cx="41" cy="43" r="1" fill="rgba(255,255,255,0.8)"/>
        <circle cx="57" cy="43" r="1" fill="rgba(255,255,255,0.8)"/>
        <!-- Pupils -->
        <circle cx="42" cy="44" r="1.5" fill="#1e0b3a"/>
        <circle cx="58" cy="44" r="1.5" fill="#1e0b3a"/>

        <!-- Nose -->
        <path d="M49 50 Q50 53 51 50" stroke="rgba(200,150,255,0.4)" stroke-width="1" fill="none"/>

        <!-- Smile -->
        <path d="M45 55 Q50 59 55 55" stroke="rgba(255,200,255,0.7)" stroke-width="1.5" fill="none" stroke-linecap="round"/>

        <!-- Headphones -->
        <path d="M30 42 Q30 24 50 24 Q70 24 70 42" stroke="#818cf8" stroke-width="3" fill="none" stroke-linecap="round"/>
        <rect x="26" y="40" width="8" height="10" rx="3" fill="#7c3aed" stroke="#a78bfa" stroke-width="0.5"/>
        <rect x="66" y="40" width="8" height="10" rx="3" fill="#7c3aed" stroke="#a78bfa" stroke-width="0.5"/>

        <!-- Screen glow on face -->
        <ellipse cx="50" cy="50" rx="18" ry="20" fill="rgba(56,189,248,0.06)"/>
      </svg>
    </div>

  </div>

  <!-- Vertical separator -->
  <div class="v-line"></div>

  <!-- Floating code snippets -->
  <div class="float-code fc1">git commit -m "feat: deploy to k8s"</div>
  <div class="float-code fc2">@SpringBootApplication</div>
  <div class="float-code fc3">docker build -t app:latest .</div>
  <div class="float-code fc4">aws eks create-cluster</div>
  <div class="float-code fc5">kubectl apply -f deployment.yaml</div>
  <div class="float-code fc6">System.out.println("Hello Cloud");</div>

  <!-- RIGHT PANEL: Branding -->
  <div class="right-panel">

    <div class="tag-line">
      <span class="status-dot"></span>
      // software_engineer.java
    </div>

    <div class="name">MissCrazyCoder</div>

    <div class="tagline">
      Code <span class="dot">•</span> Create <span class="dot">•</span> Innovate
    </div>

    <!-- Tech stack pills -->
    <div class="tech-row">
      <div class="tech-pill tp-java"><span class="pill-icon">☕</span> Java</div>
      <div class="tech-pill tp-spring"><span class="pill-icon">🌿</span> Spring Boot</div>
      <div class="tech-pill tp-micro"><span class="pill-icon">⚡</span> Microservices</div>
      <div class="tech-pill tp-docker"><span class="pill-icon">🐳</span> Docker</div>
      <div class="tech-pill tp-k8s"><span class="pill-icon">☸</span> Kubernetes</div>
      <div class="tech-pill tp-aws"><span class="pill-icon">☁</span> AWS</div>
      <div class="tech-pill tp-git"><span class="pill-icon">⑂</span> Git</div>
      <div class="tech-pill tp-cloud"><span class="pill-icon">🔗</span> Cloud Native</div>
    </div>

    <!-- Stats -->
    <div class="stats-row">
      <div class="stat">
        <div class="stat-num">∞</div>
        <div class="stat-label">commits</div>
      </div>
      <div class="stat-sep"></div>
      <div class="stat">
        <div class="stat-num">24/7</div>
        <div class="stat-label">building</div>
      </div>
      <div class="stat-sep"></div>
      <div class="stat">
        <div class="stat-num">100%</div>
        <div class="stat-label">passion</div>
      </div>
      <div class="stat-sep"></div>
      <div class="stat">
        <div class="stat-num">☁️ K8s</div>
        <div class="stat-label">deployed</div>
      </div>
    </div>

  </div>

  <!-- Scan lines overlay -->
  <div class="scanlines"></div>

  <!-- Edge glow -->
  <div class="edge-glow"></div>

  <!-- Corner decorations -->
  <div class="corner corner-tl"></div>
  <div class="corner corner-tr"></div>
  <div class="corner corner-bl"></div>
  <div class="corner corner-br"></div>

  <!-- GitHub handle bottom left -->
  <div class="github-handle">github.com/MissCrazyCoder</div>

</div>

</body>
</html>
