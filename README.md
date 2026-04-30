<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SYS.NEXUS // CYBERPUNK_OS</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Blender+Pro:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@500;700&family=Orbitron:wght@700;900&display=swap');

@font-face {
  font-family: 'Cyber';
  src: url('https://kshitishkumar.vercel.app/fonts/Cyberpunk.ttf') format('truetype');
  /* Fallback if the above doesn't exist */
}

* { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --cy-yellow: #FCEE0A;
  --cy-red: #FF003C;
  --cy-cyan: #00F0FF;
  --cy-dark: #050505;
  --cy-gray: #111111;
  --cy-blue: #021B2B;
}

body {
  background-color: var(--cy-dark);
  color: #E0E0E0;
  font-family: 'Rajdhani', sans-serif;
  overflow: hidden;
  display: flex;
  height: 100vh;
  width: 100vw;
  background-image: 
    linear-gradient(45deg, var(--cy-gray) 25%, transparent 25%, transparent 75%, var(--cy-gray) 75%, var(--cy-gray)), 
    linear-gradient(45deg, var(--cy-gray) 25%, transparent 25%, transparent 75%, var(--cy-gray) 75%, var(--cy-gray));
  background-size: 20px 20px;
  background-position: 0 0, 10px 10px;
}

/* CRT & Scanlines Overlay */
body::after {
  content: " ";
  display: block;
  position: absolute;
  top: 0; left: 0; bottom: 0; right: 0;
  background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
  z-index: 999;
  background-size: 100% 3px, 6px 100%;
  pointer-events: none;
}

/* Custom Scrollbar */
::-webkit-scrollbar { width: 8px; }
::-webkit-scrollbar-track { background: var(--cy-dark); border-left: 1px solid var(--cy-red); }
::-webkit-scrollbar-thumb { background: var(--cy-red); }

.dashboard-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  position: relative;
  z-index: 10;
}

@media (min-width: 1024px) {
  .dashboard-container { flex-direction: row; }
}

/* LEFT PANEL - CYBERPUNK HUD */
.left {
  width: 100%;
  height: 50vh;
  overflow-y: auto;
  background: rgba(5, 5, 5, 0.85);
  backdrop-filter: blur(5px);
  padding: 0;
  border-bottom: 2px solid var(--cy-yellow);
  position: relative;
  display: flex;
  flex-direction: column;
}

@media (min-width: 1024px) {
  .left {
    width: 450px;
    height: 100vh;
    border-bottom: none;
    border-right: 3px solid var(--cy-yellow);
    box-shadow: 10px 0 30px rgba(252, 238, 10, 0.1);
  }
}

.hud-header {
  background: var(--cy-yellow);
  color: var(--cy-dark);
  padding: 20px 30px;
  clip-path: polygon(0 0, 100% 0, 100% calc(100% - 15px), calc(100% - 15px) 100%, 0 100%);
  margin: 20px;
  position: relative;
  border-left: 5px solid var(--cy-red);
}
.hud-header::after {
  content: "SYS_OVERRIDE";
  position: absolute;
  top: -8px; right: -5px;
  background: var(--cy-red);
  color: #fff;
  font-family: 'Share Tech Mono';
  font-size: 10px;
  padding: 2px 8px;
  letter-spacing: 2px;
  transform: rotate(90deg);
  transform-origin: bottom right;
}

.name-glitch {
  font-family: 'Orbitron', sans-serif;
  font-size: 2.2rem;
  font-weight: 900;
  text-transform: uppercase;
  margin-bottom: 5px;
  letter-spacing: 2px;
  position: relative;
}
/* CSS Glitch Effect */
.name-glitch::before, .name-glitch::after {
  content: 'KHITISH KUMAR';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: var(--cy-yellow);
}
.name-glitch::before {
  left: 2px;
  text-shadow: -2px 0 var(--cy-red);
  clip: rect(24px, 550px, 90px, 0);
  animation: glitch-anim 3s infinite linear alternate-reverse;
}
.name-glitch::after {
  left: -2px;
  text-shadow: -2px 0 var(--cy-cyan);
  clip: rect(85px, 550px, 140px, 0);
  animation: glitch-anim 2.5s infinite linear alternate-reverse;
}
@keyframes glitch-anim {
  0% { clip: rect(10px, 9999px, 83px, 0); transform: skew(0.2deg); }
  5% { clip: rect(61px, 9999px, 12px, 0); transform: skew(0.5deg); }
  10% { clip: rect(20px, 9999px, 50px, 0); transform: skew(0.1deg); }
  15% { clip: rect(98px, 9999px, 80px, 0); transform: skew(0.3deg); }
  20% { clip: rect(4px, 9999px, 15px, 0); transform: skew(0deg); }
  25% { clip: rect(55px, 9999px, 70px, 0); transform: skew(0.4deg); }
  30% { clip: rect(35px, 9999px, 20px, 0); transform: skew(0deg); }
  100% { clip: rect(35px, 9999px, 20px, 0); transform: skew(0deg); }
}

.sub {
  font-family: 'Share Tech Mono', monospace;
  font-size: 0.9rem;
  font-weight: bold;
  letter-spacing: 1px;
}

.cy-btn {
  display: inline-block;
  margin-top: 15px;
  padding: 10px 20px;
  background: var(--cy-cyan);
  color: var(--cy-dark);
  font-family: 'Orbitron', sans-serif;
  font-weight: bold;
  text-transform: uppercase;
  text-decoration: none;
  clip-path: polygon(15px 0, 100% 0, 100% calc(100% - 15px), calc(100% - 15px) 100%, 0 100%, 0 15px);
  position: relative;
  transition: all 0.2s;
}
.cy-btn:hover {
  background: var(--cy-red);
  color: #fff;
  transform: translate(2px, -2px);
  box-shadow: -5px 5px 0 rgba(255,0,60,0.4);
}
.cy-btn::after {
  content: 'R2';
  position: absolute;
  bottom: 2px; right: 4px;
  font-size: 8px;
  opacity: 0.5;
}

/* SECTION CONTAINERS */
.section-wrapper { padding: 0 30px 30px 30px; }
.section-title {
  font-family: 'Orbitron', sans-serif;
  font-size: 1.2rem;
  color: var(--cy-cyan);
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  border-bottom: 1px solid var(--cy-cyan);
  padding-bottom: 5px;
  text-transform: uppercase;
}
.section-title::before {
  content: "▶";
  color: var(--cy-red);
  margin-right: 10px;
  font-size: 0.9rem;
}

/* ABOUT GRID */
.about-grid { display: flex; flex-direction: column; gap: 10px; }
.aitem {
  display: flex;
  justify-content: space-between;
  background: var(--cy-gray);
  border-left: 4px solid var(--cy-yellow);
  padding: 10px 15px;
  font-family: 'Share Tech Mono', monospace;
  font-size: 0.85rem;
  position: relative;
}
.aitem::before {
  content: ""; position: absolute; top: 0; right: 0; width: 10px; height: 10px;
  border-top: 2px solid var(--cy-red); border-right: 2px solid var(--cy-red);
}
.aitem span.lbl { color: var(--cy-cyan); font-weight: bold; }
.aitem span.val { color: #fff; text-align: right; }

/* BADGES / ARSENAL */
.badge-container { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 15px; }
.cy-badge {
  background: transparent;
  border: 1px solid var(--cy-cyan);
  color: var(--cy-cyan);
  padding: 5px 10px;
  font-family: 'Rajdhani', sans-serif;
  font-weight: 700;
  font-size: 0.8rem;
  text-transform: uppercase;
  clip-path: polygon(5px 0, 100% 0, 100% calc(100% - 5px), calc(100% - 5px) 100%, 0 100%, 0 5px);
  transition: 0.2s;
  cursor: default;
}
.cy-badge:hover { background: var(--cy-cyan); color: var(--cy-dark); }
.cy-badge.red { border-color: var(--cy-red); color: var(--cy-red); }
.cy-badge.red:hover { background: var(--cy-red); color: #fff; }
.cy-badge.yel { border-color: var(--cy-yellow); color: var(--cy-yellow); }
.cy-badge.yel:hover { background: var(--cy-yellow); color: var(--cy-dark); }

/* STATS CARDS */
.stats-grid { display: flex; flex-direction: column; gap: 15px; }
.stat-img {
  width: 100%;
  border: 2px solid var(--cy-gray);
  filter: grayscale(100%) contrast(120%) brightness(80%);
  transition: filter 0.3s;
  clip-path: polygon(0 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%);
}
.stat-img:hover { filter: grayscale(0%) contrast(100%) brightness(100%); border-color: var(--cy-red); }

/* SCENE PANEL */
.scene-wrap {
  flex: 1;
  background: radial-gradient(circle at center, #0a0a0a 0%, #000000 100%);
  position: relative;
  overflow: hidden;
  height: 50vh;
}
@media (min-width: 1024px) { .scene-wrap { height: 100vh; } }
.scene-wrap canvas { display: block; width: 100%; height: 100%; }

/* SCENE OVERLAYS */
.hud-element {
  position: absolute;
  font-family: 'Share Tech Mono', monospace;
  color: var(--cy-red);
  font-size: 0.8rem;
  pointer-events: none;
  z-index: 5;
}
.hud-tl { top: 20px; left: 20px; border-top: 2px solid var(--cy-red); border-left: 2px solid var(--cy-red); padding: 5px; }
.hud-tr { top: 20px; right: 20px; text-align: right; color: var(--cy-cyan); }
.hud-bl { bottom: 60px; left: 20px; }
.hud-br { bottom: 60px; right: 20px; color: var(--cy-yellow); }

.warning-bar {
  position: absolute;
  top: 50%; left: 0; width: 100%;
  height: 40px;
  background: rgba(255, 0, 60, 0.1);
  border-top: 1px solid var(--cy-red);
  border-bottom: 1px solid var(--cy-red);
  display: flex;
  align-items: center;
  overflow: hidden;
  z-index: 2;
  opacity: 0.5;
  transform: translateY(-50%);
}
.warning-text {
  color: var(--cy-red);
  font-family: 'Orbitron', sans-serif;
  font-weight: 900;
  font-size: 1.5rem;
  letter-spacing: 10px;
  white-space: nowrap;
  animation: marquee 10s linear infinite;
}
@keyframes marquee { 0% { transform: translateX(100vw); } 100% { transform: translateX(-100%); } }

/* BOTTOM BAR */
.system-status {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 40px;
  background: var(--cy-yellow);
  color: var(--cy-dark);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
  font-family: 'Orbitron', sans-serif;
  font-weight: 900;
  font-size: 0.8rem;
  z-index: 20;
  border-top: 3px solid #fff;
}
.sys-time { background: var(--cy-dark); color: var(--cy-cyan); padding: 2px 10px; border-radius: 2px; }

</style>
</head>
<body>

<div class="dashboard-container">
  <!-- LEFT HUD PANEL -->
  <div class="left">
    
    <div class="hud-header">
      <div class="name-glitch">Khitish Kumar</div>
      <div class="sub">AI.ARCHITECT // FULLSTACK.ENG</div>
      <a class="cy-btn" href="https://kshitishkumar.vercel.app/" target="_blank">INITIATE_PORTFOLIO</a>
    </div>

    <div class="section-wrapper">
      <div class="section-title">SYSTEM.PROFILE</div>
      <div class="about-grid">
        <div class="aitem"><span class="lbl">MISSION</span><span class="val">BTech CSE — AI/ML</span></div>
        <div class="aitem"><span class="lbl">MODULES</span><span class="val">Computer Vision Arch</span></div>
        <div class="aitem"><span class="lbl">OS_CORE</span><span class="val">Garuda Linux [Arch]</span></div>
        <div class="aitem"><span class="lbl">UPLINK</span><span class="val">kknayak049@gmail.com</span></div>
      </div>
    </div>

    <div class="section-wrapper">
      <div class="section-title">COMBAT.ARSENAL</div>
      <div class="badge-container">
        <span class="cy-badge">Python</span>
        <span class="cy-badge red">PyTorch</span>
        <span class="cy-badge yel">TensorFlow</span>
        <span class="cy-badge">OpenCV</span>
        <span class="cy-badge red">Pandas</span>
      </div>
      <div class="badge-container">
        <span class="cy-badge yel">HTML5</span>
        <span class="cy-badge">CSS3</span>
        <span class="cy-badge yel">JavaScript</span>
        <span class="cy-badge red">React</span>
        <span class="cy-badge">React Native</span>
        <span class="cy-badge yel">C# .NET</span>
      </div>
      <div class="badge-container">
        <span class="cy-badge red">Firebase</span>
        <span class="cy-badge yel">MongoDB</span>
        <span class="cy-badge">MySQL</span>
        <span class="cy-badge">Linux</span>
        <span class="cy-badge red">Git</span>
      </div>
    </div>

    <div class="section-wrapper">
      <div class="section-title">NETWORK.DIAGNOSTICS</div>
      <div class="stats-grid">
        <img class="stat-img" src="https://github-readme-stats.vercel.app/api?username=khitishnayak&show_icons=true&theme=radical&hide_border=true&count_private=true&bg_color=111111&title_color=FCEE0A&text_color=E0E0E0&icon_color=FF003C" alt="GitHub Stats" />
        <img class="stat-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=khitishnayak&layout=compact&theme=radical&hide_border=true&bg_color=111111&title_color=00F0FF&text_color=E0E0E0" alt="Top Languages" />
        <img class="stat-img" src="https://github-readme-streak-stats.herokuapp.com/?user=khitishnayak&theme=radical&hide_border=true&background=111111&ring=FCEE0A&fire=FF003C&currStreakLabel=00F0FF" alt="GitHub Streak" />
      </div>
    </div>

    <div class="section-wrapper">
      <div class="section-title">COMM.LINKS</div>
      <div class="badge-container">
        <a href="https://twitter.com/khitishkumarn12" target="_blank" class="cy-badge">X.CORE</a>
        <a href="https://linkedin.com/in/khitish-kumar-nayak-594051285" target="_blank" class="cy-badge yel">LINKEDIN</a>
        <a href="https://instagram.com/alexian_eraa" target="_blank" class="cy-badge red">INSTA.NET</a>
        <a href="https://discord.gg/UYaxjF25b6" target="_blank" class="cy-badge">DISCORD.HUB</a>
      </div>
    </div>
    
    <div style="height: 50px;"></div>
  </div>

  <!-- SCENE PANEL -->
  <div class="scene-wrap">
    <div class="warning-bar"><div class="warning-text">WARNING // SYSTEM OVERRIDE // UNAUTHORIZED ACCESS DETECTED // NEURAL LINK ESTABLISHED</div></div>
    
    <div class="hud-element hud-tl">REC<br><span style="color:#fff">●</span></div>
    <div class="hud-element hud-tr">TARGET_LOCK<br>[ ACQUIRED ]</div>
    <div class="hud-element hud-bl">SEC_LVL: OMEGA<br>MEM_USAGE: 99%</div>
    <div class="hud-element hud-br">A.I. STATUS:<br>SENTIENT</div>
    
    <canvas id="sc"></canvas>
    
    <div class="system-status">
      <div>V_2.0.77 <span class="sys-time" id="sys-time">00:00:00</span></div>
      <div>NEXUS_OS ACTIVE</div>
      <div style="color: var(--cy-red);">[ CONNECTION_SECURE ]</div>
    </div>
  </div>
</div>

<script>
/* System Time Update */
function updateTime() {
  const d = new Date();
  document.getElementById('sys-time').textContent = d.getHours().toString().padStart(2, '0') + ':' + 
                                                    d.getMinutes().toString().padStart(2, '0') + ':' + 
                                                    d.getSeconds().toString().padStart(2, '0') + ':' + 
                                                    d.getMilliseconds().toString().padStart(3, '0').substring(0,2);
}
setInterval(updateTime, 50);

/* Canvas Scene */
const cv = document.getElementById('sc');
const ctx = cv.getContext('2d');

function resize() {
  cv.width = cv.offsetWidth;
  cv.height = cv.offsetHeight;
}
resize();
window.addEventListener('resize', resize);

let T = 0;

function rRect(x, y, w, h, r, fill, stroke) {
  ctx.save();
  ctx.beginPath();
  ctx.roundRect(x, y, w, h, r);
  ctx.fillStyle = fill;
  ctx.fill();
  if (stroke) {
    ctx.strokeStyle = stroke;
    ctx.lineWidth = 2;
    ctx.stroke();
  }
  ctx.restore();
}

/* ── CYBER BOY (Aggressive Style) ── */
function drawBoy(X, Y) {
  const bob = Math.sin(T * 2) * 5;
  ctx.save();
  ctx.translate(X, Y + bob);

  // Glitch offset
  let gx = 0;
  if (Math.random() > 0.95) gx = (Math.random() - 0.5) * 15;
  ctx.translate(gx, 0);

  // Chair
  rRect(-55, 10, 20, 100, 0, '#111', '#FCEE0A');
  rRect(-50, 110, 100, 15, 0, '#222', '#FF003C');

  // LEGS
  rRect(-25, 95, 20, 35, 0, '#0a0a0a', '#00F0FF');
  rRect(5, 95, 20, 35, 0, '#0a0a0a', '#00F0FF');
  // Shoes (Cyberpunk Boots)
  ctx.fillStyle = '#FF003C';
  ctx.beginPath(); ctx.moveTo(-30, 130); ctx.lineTo(-5, 130); ctx.lineTo(-15, 115); ctx.lineTo(-30, 115); ctx.fill();
  ctx.beginPath(); ctx.moveTo(5, 130); ctx.lineTo(30, 130); ctx.lineTo(20, 115); ctx.lineTo(5, 115); ctx.fill();

  // BODY (Tech Jacket)
  rRect(-38, 30, 76, 75, 0, '#1a1a1a', '#FCEE0A');
  // Jacket details
  ctx.fillStyle = '#FCEE0A';
  ctx.fillRect(10, 40, 20, 5);
  ctx.fillRect(-25, 80, 50, 5);
  ctx.fillStyle = '#FF003C';
  ctx.fillRect(-30, 40, 15, 20);

  // LEFT ARM
  ctx.save();
  ctx.translate(-45, 55); ctx.rotate(0.3);
  rRect(-10, 0, 20, 48, 0, '#222', '#FCEE0A');
  // Cybernetic Hand
  ctx.fillStyle = '#00F0FF'; ctx.fillRect(-10, 48, 20, 15);
  ctx.restore();

  // RIGHT ARM
  ctx.save();
  ctx.translate(45, 50); ctx.rotate(-0.2);
  rRect(-10, 0, 20, 45, 0, '#222', '#FCEE0A');
  // Hand holding weapon/device
  ctx.fillStyle = '#00F0FF'; ctx.fillRect(-10, 45, 20, 15);
  ctx.fillStyle = '#FF003C'; ctx.fillRect(-20, 50, 40, 5);
  ctx.restore();

  // NECK
  rRect(-12, 15, 24, 18, 0, '#000', '#00F0FF');

  // HEAD
  rRect(-35, -40, 70, 60, 0, '#111', '#FCEE0A');

  // CYBER MASK (Replaces face)
  ctx.fillStyle = '#000';
  ctx.beginPath(); ctx.moveTo(-35, -10); ctx.lineTo(35, -10); ctx.lineTo(20, 20); ctx.lineTo(-20, 20); ctx.fill();
  
  // GLOWING VISOR SLIT
  ctx.shadowColor = '#FF003C'; ctx.shadowBlur = 20;
  ctx.fillStyle = '#FF003C';
  ctx.fillRect(-25, -5, 50, 6);
  ctx.shadowBlur = 0;

  // NEON CABLES
  ctx.strokeStyle = '#00F0FF'; ctx.lineWidth = 3;
  ctx.beginPath(); ctx.moveTo(35, -20); ctx.quadraticCurveTo(50, 10, 35, 40); ctx.stroke();
  ctx.beginPath(); ctx.moveTo(-35, -20); ctx.quadraticCurveTo(-50, 10, -35, 40); ctx.stroke();

  ctx.restore();
}

/* ── MONITOR (Holographic Projection) ── */
function drawMonitor(X, Y) {
  ctx.save(); ctx.translate(X, Y);

  // Hologram Base
  ctx.fillStyle = '#FCEE0A';
  ctx.beginPath(); ctx.moveTo(-40, 130); ctx.lineTo(40, 130); ctx.lineTo(30, 140); ctx.lineTo(-30, 140); ctx.fill();

  // Projection Cone
  const grad = ctx.createLinearGradient(0, 130, 0, -85);
  grad.addColorStop(0, 'rgba(0, 240, 255, 0.4)');
  grad.addColorStop(1, 'rgba(0, 240, 255, 0)');
  ctx.fillStyle = grad;
  ctx.beginPath(); ctx.moveTo(-30, 130); ctx.lineTo(-120, -85); ctx.lineTo(120, -85); ctx.lineTo(30, 130); ctx.fill();

  // Screen Bounds
  ctx.strokeStyle = '#00F0FF'; ctx.lineWidth = 2;
  ctx.strokeRect(-120, -85, 240, 190);
  
  // Glitch rects on screen
  if (Math.random() > 0.8) {
    ctx.fillStyle = 'rgba(255, 0, 60, 0.5)';
    ctx.fillRect(-120 + Math.random()*200, -85 + Math.random()*150, Math.random()*100, Math.random()*20);
  }

  // Code content
  const codeLines = [
    'OVERRIDE_AUTH_KEY: *********',
    'UPLOADING_VIRUS... [99%]',
    '> INITIALIZING_CYBER_DECK',
    '> BYPASSING_ICE_PROTOCOLS',
    'ACCESS_GRANTED.',
    '',
    'RUNNING_SCRIPT: DESTROY_CORP'
  ];
  
  ctx.font = '14px "Share Tech Mono", monospace';
  ctx.fillStyle = '#FCEE0A';
  ctx.textAlign = 'left';
  
  codeLines.forEach((code, i) => {
    ctx.fillText(code, -110, -50 + i * 20);
  });

  ctx.restore();
}

function drawGrid() {
  const W = cv.width, H = cv.height;
  ctx.save();
  ctx.strokeStyle = 'rgba(255, 0, 60, 0.15)';
  ctx.lineWidth = 2;
  
  // Perspective grid effect
  ctx.translate(W/2, H/2 + 100);
  
  for(let i=0; i<20; i++) {
    let y = Math.pow(i, 1.5) * 5;
    ctx.beginPath(); ctx.moveTo(-W, y); ctx.lineTo(W, y); ctx.stroke();
  }
  for(let i=-20; i<20; i++) {
    ctx.beginPath(); ctx.moveTo(0, 0); ctx.lineTo(i*100, H); ctx.stroke();
  }
  ctx.restore();
}

function draw() {
  const W = cv.width, H = cv.height;
  ctx.clearRect(0, 0, W, H);
  
  // Deep background
  ctx.fillStyle = 'rgba(5,5,5,0.8)';
  ctx.fillRect(0,0,W,H);

  drawGrid();

  const cx = W / 2, cy = H / 2;

  // Background neon circle (Sun)
  ctx.save();
  ctx.shadowColor = '#FF003C';
  ctx.shadowBlur = 50;
  ctx.fillStyle = '#FF003C';
  ctx.beginPath(); ctx.arc(cx, cy - 50, 150, 0, Math.PI*2); ctx.fill();
  
  // Cutouts in the sun (Synthwave style)
  ctx.globalCompositeOperation = 'destination-out';
  for(let i=0; i<10; i++) {
    ctx.fillRect(cx - 160, cy + 20 + i*15, 320, 5 + i*2);
  }
  ctx.globalCompositeOperation = 'source-over';
  ctx.restore();

  // Draw Elements
  drawMonitor(cx - 150, cy - 80);
  drawBoy(cx + 80, cy + 20);

  // Random glitch blocks
  if (Math.random() > 0.9) {
    ctx.fillStyle = Math.random() > 0.5 ? '#FCEE0A' : '#00F0FF';
    ctx.fillRect(Math.random()*W, Math.random()*H, Math.random()*200, Math.random()*10);
  }

  T += 0.02;
  requestAnimationFrame(draw);
}
draw();
</script>
</body>
</html>

