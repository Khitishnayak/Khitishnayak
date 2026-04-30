
<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&family=Rajdhani:wght@400;600;700&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --cy:#00f5ff;--mg:#ff00ff;--ye:#f5e642;--dk:#040810;--cd:#0b1728;--br:#162033;
}
body{background:#040810;color:#b8d0e8;font-family:'Rajdhani',sans-serif;overflow-x:hidden}

/* LAYOUT: stacked — left info, then full-width scene */
.left{padding:24px 28px 20px;background:#040810}

/* HERO */
.name-glitch{font-family:'Orbitron',monospace;font-size:clamp(1.8rem,6vw,3rem);font-weight:900;color:#00f5ff;text-shadow:0 0 8px #00f5ff,0 0 20px rgba(0,245,255,.3);letter-spacing:3px;position:relative;display:inline-block;animation:flkr 7s infinite}
.name-glitch::before,.name-glitch::after{content:'Khitish Kumar';position:absolute;top:0;left:0;right:0;opacity:.75}
.name-glitch::before{color:#ff00ff;animation:g1 2.8s infinite;clip-path:polygon(0 20%,100% 20%,100% 45%,0 45%)}
.name-glitch::after{color:#f5e642;animation:g2 2.8s infinite;clip-path:polygon(0 60%,100% 60%,100% 82%,0 82%)}
@keyframes g1{0%,100%{transform:translate(0)}25%{transform:translate(-4px,1px)}75%{transform:translate(3px,-1px)}}
@keyframes g2{0%,100%{transform:translate(0)}33%{transform:translate(4px,-2px)}66%{transform:translate(-3px,2px)}}
@keyframes flkr{0%,94%,96%,100%{opacity:1}95%{opacity:.3}}
.sub{font-family:'Share Tech Mono',monospace;font-size:.75rem;color:#ff00ff;letter-spacing:2px;margin-top:6px;text-shadow:0 0 6px #ff00ff}
.nexus-pill{display:inline-flex;align-items:center;gap:7px;margin-top:10px;padding:5px 14px;border:1px solid #ff00ff;background:rgba(255,0,255,.05);font-family:'Share Tech Mono',monospace;font-size:.65rem;color:#ff00ff;animation:pulse 3s ease-in-out infinite}
@keyframes pulse{0%,100%{box-shadow:0 0 6px #ff00ff,0 0 18px rgba(255,0,255,.3)}50%{box-shadow:0 0 18px #ff00ff,0 0 36px rgba(255,0,255,.2)}}
.dot{width:7px;height:7px;border-radius:50%;background:#ff00ff;animation:blink .85s step-end infinite}
@keyframes blink{50%{opacity:.1}}
.typebar{display:inline-flex;align-items:center;gap:7px;margin-top:12px;padding:7px 14px;border:1px solid rgba(0,245,255,.4);background:rgba(0,245,255,.04);font-family:'Share Tech Mono',monospace;font-size:.78rem;color:#00f5ff;box-shadow:0 0 8px rgba(0,245,255,.2)}
.cursor{display:inline-block;width:8px;height:1em;background:#00f5ff;animation:blink 1s step-end infinite}
.portlink{display:inline-block;margin-top:12px;font-family:'Orbitron',monospace;font-size:.65rem;font-weight:700;letter-spacing:2px;color:#00f5ff;text-decoration:none;border-bottom:1px solid #00f5ff;padding-bottom:2px}

.div{display:flex;align-items:center;gap:10px;margin:18px 0 12px}
.dline{flex:1;height:1px;background:linear-gradient(90deg,transparent,#00f5ff,transparent)}
.dtag{font-family:'Share Tech Mono',monospace;font-size:.62rem;color:#00f5ff;white-space:nowrap}
.stitle{font-family:'Orbitron',monospace;font-size:.82rem;font-weight:700;color:#00f5ff;text-shadow:0 0 6px #00f5ff;letter-spacing:2px;margin-bottom:10px}
.stitle span{color:#ff00ff}

.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:7px}
.aitem{display:flex;align-items:flex-start;gap:8px;background:#0b1728;border:1px solid #162033;border-left:3px solid #00f5ff;padding:9px 11px;font-size:.82rem;line-height:1.4;transition:border-color .2s,box-shadow .2s}
.aitem:hover{border-left-color:#ff00ff;box-shadow:0 0 8px rgba(255,0,255,.2)}
.aitem strong{color:#00f5ff;font-family:'Share Tech Mono',monospace;font-size:.65rem;display:block;margin-bottom:2px}

.slabel{font-family:'Share Tech Mono',monospace;font-size:.62rem;color:#ff00ff;letter-spacing:2px;margin-bottom:7px;text-shadow:0 0 5px #ff00ff}
.badges{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:13px}
.badge{padding:4px 10px;border:1px solid #162033;background:#0b1728;font-family:'Orbitron',monospace;font-size:.54rem;font-weight:700;letter-spacing:1px;color:#7a9ab8;cursor:default;transition:all .2s}
.badge:hover{border-color:#00f5ff;color:#00f5ff;box-shadow:0 0 6px rgba(0,245,255,.3);transform:translateY(-2px)}
.badge.m:hover{border-color:#ff00ff;color:#ff00ff;box-shadow:0 0 6px rgba(255,0,255,.3)}
.badge.y:hover{border-color:#f5e642;color:#f5e642}

.stats2{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.scard{background:#0b1728;border:1px solid #162033;padding:10px;text-align:center;position:relative;overflow:hidden;transition:box-shadow .2s}
.scard:hover{box-shadow:0 0 10px rgba(0,245,255,.2)}
.scard::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,#ff00ff,#00f5ff);animation:scantop 3s linear infinite}
@keyframes scantop{0%{opacity:.2}50%{opacity:1}100%{opacity:.2}}
.slbl{font-family:'Share Tech Mono',monospace;font-size:.58rem;color:#ff00ff;letter-spacing:1.5px;margin-bottom:5px}
.scard img,.streak-card img{width:100%;display:block}
.streak-card{background:#0b1728;border:1px solid #162033;padding:10px;margin-top:8px;text-align:center;position:relative;overflow:hidden}
.streak-card::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,#00f5ff,#ff00ff);animation:scantop 4s linear infinite}

.cbts{display:flex;flex-wrap:wrap;gap:7px;margin-top:5px}
.cbtn{display:inline-flex;align-items:center;gap:5px;padding:7px 13px;border:1px solid;font-family:'Orbitron',monospace;font-size:.55rem;font-weight:700;letter-spacing:1.5px;text-decoration:none;text-transform:uppercase;transition:all .22s}
.tw{border-color:#1DA1F2;color:#1DA1F2}.tw:hover{background:#1DA1F2;color:#040810;box-shadow:0 0 12px #1DA1F2}
.li{border-color:#0077B5;color:#0077B5}.li:hover{background:#0077B5;color:#040810}
.ig{border-color:#E4405F;color:#E4405F}.ig:hover{background:#E4405F;color:#040810}
.dc{border-color:#7289DA;color:#7289DA}.dc:hover{background:#7289DA;color:#040810}
.bmc{border-color:#f5e642;color:#f5e642}.bmc:hover{background:#f5e642;color:#040810}

/* SCENE WRAPPER */
.scene-wrap{width:100%;background:#04080f;border-top:1px solid #162033;position:relative;overflow:hidden}
.scene-wrap canvas{display:block;width:100%;height:520px}
.scene-corner{position:absolute;font-family:'Share Tech Mono',monospace;font-size:.62rem;color:#00f5ff;text-shadow:0 0 6px #00f5ff;letter-spacing:1.5px;pointer-events:none;animation:lfloat 4s ease-in-out infinite}
@keyframes lfloat{0%,100%{transform:translateY(0)}50%{transform:translateY(-4px)}}
.scene-corner.mg{color:#ff00ff;text-shadow:0 0 6px #ff00ff;animation-delay:.9s}
.scene-corner.ye{color:#f5e642;animation-delay:1.8s}
</style>

<!-- LEFT INFO PANEL -->
<div class="left">
  <div style="display:flex;align-items:flex-start;justify-content:space-between;flex-wrap:wrap;gap:20px">
    <div style="flex:1;min-width:260px">
      <div class="name-glitch">Khitish Kumar</div>
      <div class="sub">// AI RESEARCHER · TECH VISIONARY · FOUNDER</div>
      <div class="nexus-pill"><span class="dot"></span>NEXUS TECHNOLOGY — THE MIND BEYOND THE MACHINES</div><br>
      <div class="typebar"><span id="tt">Founder of Nexus Technology</span><span class="cursor"></span></div><br>
      <a class="portlink" href="https://kshitishkumar.vercel.app/" target="_blank">▶ EXPLORE PORTFOLIO</a>
    </div>
  </div>

  <div class="div"><div class="dline"></div><div class="dtag">[ SYSTEM.PROFILE ]</div><div class="dline"></div></div>
  <div class="stitle"><span>//</span> ABOUT_ME.exe</div>
  <div class="about-grid">
    <div class="aitem"><span>🔭</span><div><strong>CURRENT_MISSION</strong>BTech CSE — AI/ML Specialization</div></div>
    <div class="aitem"><span>🌱</span><div><strong>LEARNING_MODULES</strong>Advanced Computer Vision & Fullstack Arch</div></div>
    <div class="aitem"><span>🐧</span><div><strong>OS_RUNTIME</strong>Garuda Linux</div></div>
    <div class="aitem"><span>💬</span><div><strong>QUERY_TOPICS</strong>AI · ML · Innovation · Startup Growth</div></div>
    <div class="aitem" style="grid-column:span 2"><span>📫</span><div><strong>UPLINK</strong>kknayak049@gmail.com</div></div>
  </div>

  <div class="div"><div class="dline"></div><div class="dtag">[ TECH.ARSENAL ]</div><div class="dline"></div></div>
  <div class="stitle"><span>//</span> THE_ARSENAL</div>
  <div class="slabel">🤖 AI / MACHINE LEARNING</div>
  <div class="badges"><span class="badge">Python</span><span class="badge m">PyTorch</span><span class="badge">TensorFlow</span><span class="badge m">OpenCV</span><span class="badge">Pandas</span></div>
  <div class="slabel">💻 FULLSTACK & MOBILE DEV</div>
  <div class="badges"><span class="badge y">HTML5</span><span class="badge">CSS3</span><span class="badge y">JavaScript</span><span class="badge m">React</span><span class="badge">React Native</span><span class="badge">C#</span><span class="badge">.NET</span><span class="badge m">Android</span></div>
  <div class="slabel">🗄️ BACKEND, IoT & TOOLS</div>
  <div class="badges"><span class="badge y">Firebase</span><span class="badge m">MongoDB</span><span class="badge">MySQL</span><span class="badge">Arduino</span><span class="badge y">Linux</span><span class="badge">Git</span></div>

  <div class="div"><div class="dline"></div><div class="dtag">[ GITHUB.STATS ]</div><div class="dline"></div></div>
  <div class="stitle"><span>//</span> SYSTEM_DIAGNOSTICS</div>
  <div class="stats2">
    <div class="scard"><div class="slbl">// ACTIVITY LOG</div><img src="https://github-readme-stats.vercel.app/api?username=khitishnayak&show_icons=true&theme=radical&hide_border=true&count_private=true&bg_color=0b1728&title_color=00f5ff&text_color=8ab4d0&icon_color=ff00ff"/></div>
    <div class="scard"><div class="slbl">// LANGUAGE MATRIX</div><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=khitishnayak&layout=compact&theme=radical&hide_border=true&bg_color=0b1728&title_color=00f5ff&text_color=8ab4d0"/></div>
  </div>
  <div class="streak-card"><div class="slbl">// CONTRIBUTION STREAK</div><img src="https://github-readme-streak-stats.herokuapp.com/?user=khitishnayak&theme=radical&hide_border=true&background=0b1728&ring=00f5ff&fire=ff00ff&currStreakLabel=00f5ff"/></div>

  <div class="div"><div class="dline"></div><div class="dtag">[ UPLINK.NETWORK ]</div><div class="dline"></div></div>
  <div class="stitle"><span>//</span> CONNECT & SUPPORT</div>
  <div class="cbts">
    <a class="cbtn tw" href="https://twitter.com/khitishkumarn12" target="_blank">𝕏 Twitter</a>
    <a class="cbtn li" href="https://linkedin.com/in/khitish-kumar-nayak-594051285" target="_blank">in LinkedIn</a>
    <a class="cbtn ig" href="https://instagram.com/alexian_eraa" target="_blank">◈ Instagram</a>
    <a class="cbtn dc" href="https://discord.gg/UYaxjF25b6" target="_blank">⬡ Discord</a>
    <a class="cbtn bmc" href="https://www.buymeacoffee.com/Alexian_Era" target="_blank">☕ Buy Me Coffee</a>
  </div>
</div>

<!-- SCENE PANEL — full width below -->
<div class="scene-wrap">
  <div class="scene-corner" style="top:10px;left:12px">// NEXUS.SYSTEM</div>
  <div class="scene-corner mg" style="top:10px;right:12px">ONLINE ●</div>
  <div class="scene-corner ye" style="bottom:36px;left:12px">CAT.MODE: ACTIVATED</div>
  <div class="scene-corner" style="bottom:36px;right:12px">COFFEE: ∞</div>
  <canvas id="sc"></canvas>
</div>

<script>
/* typing */
const lines=['Founder of Nexus Technology','Building NextGen AI Solutions','BTech CSE · AI/ML Specialization','Garuda Linux Enthusiast','The Next Evolution of AI'];
let li=0,ci=0,del=false;const tel=document.getElementById('tt');
function type(){const w=lines[li];if(!del){tel.textContent=w.slice(0,++ci);if(ci===w.length){del=true;setTimeout(type,1500);return}}else{tel.textContent=w.slice(0,--ci);if(ci===0){del=false;li=(li+1)%lines.length}}setTimeout(type,del?42:78);}
type();

/* scene */
const cv=document.getElementById('sc');
const ctx=cv.getContext('2d');
function resize(){cv.width=cv.offsetWidth;cv.height=cv.offsetHeight||520}
resize();window.addEventListener('resize',resize);

let T=0;

function glow(col,amt){ctx.shadowColor=col;ctx.shadowBlur=amt}
function noGlow(){ctx.shadowColor='transparent';ctx.shadowBlur=0}

function rRect(x,y,w,h,r,fill,stroke,glowCol=null,glowAmt=0){
  ctx.save();if(glowCol){glow(glowCol,glowAmt)}
  ctx.beginPath();ctx.roundRect(x,y,w,h,r);
  ctx.fillStyle=fill;ctx.fill();
  if(stroke){ctx.strokeStyle=stroke;ctx.lineWidth=1.5;ctx.stroke()}
  ctx.restore();
}

function circle(x,y,r,fill,stroke,glowCol,glowAmt=0){
  ctx.save();if(glowCol){glow(glowCol,glowAmt)}
  ctx.beginPath();ctx.arc(x,y,r,0,Math.PI*2);
  ctx.fillStyle=fill;ctx.fill();
  if(stroke){ctx.strokeStyle=stroke;ctx.lineWidth=1.5;ctx.stroke()}
  ctx.restore();
}

function label(t,x,y,col,sz,gAmt=0,font='Share Tech Mono',align='left'){
  ctx.save();ctx.font=`${sz}px "${font}", monospace`;ctx.fillStyle=col;ctx.textAlign=align;
  if(gAmt){glow(col,gAmt)}
  ctx.fillText(t,x,y);ctx.restore();
}

/* ── CYBER BOY ── */
function drawBoy(X,Y){
  const bob=Math.sin(T*2)*4;
  ctx.save();ctx.translate(X,Y+bob);

  // Chair back
  rRect(-45,30,14,80,'#0a1830','#1a3a6a','#1a3a6a',6);
  // Chair seat
  rRect(-42,105,84,14,4,'#0d2040','#1a3a6a','#1a4a8a',8);
  // Chair legs
  rRect(-38,118,10,22,2,'#0a1830','#162030');
  rRect(28,118,10,22,2,'#0a1830','#162030');

  // LEGS
  rRect(-22,90,18,30,4,'#1a2060','#2233aa');
  rRect(4,90,18,30,4,'#1a2060','#2233aa');
  // Shoes
  rRect(-26,116,24,10,3,'#111','#00f5ff','#00f5ff',12);
  rRect(2,116,24,10,3,'#111','#00f5ff','#00f5ff',12);

  // BODY / HOODIE
  rRect(-32,30,64,65,6,'#1a1aee','#3344ff','#4466ff',20);
  // hoodie center zip line
  ctx.save();ctx.strokeStyle='rgba(0,245,255,.4)';ctx.lineWidth=1.5;
  ctx.beginPath();ctx.moveTo(0,30);ctx.lineTo(0,95);ctx.stroke();
  // pocket
  ctx.beginPath();ctx.roundRect(-18,62,36,22,3);ctx.strokeStyle='rgba(0,245,255,.35)';ctx.lineWidth=1;ctx.stroke();
  ctx.restore();
  // NX label on pocket
  label('NX',-10,78,'rgba(0,245,255,.7)',10,'Orbitron');

  // LEFT ARM (typing, angled down)
  ctx.save();ctx.translate(-38,50);ctx.rotate(0.25);
  rRect(-8,0,18,40,4,'#1a1aee','#3344ff');
  // hand
  circle(0,44,9,'rgba(30,50,100,.9)','#00f5ff','#00f5ff',12);
  ctx.restore();

  // RIGHT ARM (holding coffee, lifted slightly)
  const armBob=Math.sin(T*1.5)*0.08;
  ctx.save();ctx.translate(38,48);ctx.rotate(-0.2+armBob);
  rRect(-8,0,18,38,4,'#1a1aee','#3344ff');
  // hand
  circle(0,42,9,'rgba(30,50,100,.9)','#00f5ff','#00f5ff',12);
  ctx.restore();

  // NECK
  rRect(-10,18,20,16,3,'rgba(20,40,90,.9)','rgba(0,245,255,.2)');

  // HEAD
  rRect(-30,-32,60,54,8,'rgba(10,20,55,.97)','#00f5ff','#00f5ff',20);

  // HAIR spikes
  ctx.save();ctx.fillStyle='#080818';ctx.strokeStyle='rgba(0,245,255,.5)';ctx.lineWidth=1.2;
  [[-22,-28,-14,-46],[-12,-30,-4,-50],[0,-31,8,-50],[14,-28,22,-44]].forEach(([x1,y1,x2,y2])=>{
    ctx.save();glow('#00f5ff',8);
    ctx.beginPath();ctx.moveTo(x1,y1);ctx.lineTo(x2,y2);ctx.lineTo(x2+8,y1+2);ctx.closePath();
    ctx.fill();ctx.stroke();ctx.restore();
  });
  ctx.restore();

  // HEADPHONES arc
  ctx.save();ctx.strokeStyle='#00f5ff';ctx.lineWidth=4;glow('#00f5ff',16);
  ctx.beginPath();ctx.arc(0,-16,32,Math.PI*1.12,Math.PI*1.88);ctx.stroke();noGlow();
  // ear cups
  circle(-32,-12,8,'rgba(0,10,30,.9)','#00f5ff','#00f5ff',14);
  circle(32,-12,8,'rgba(0,10,30,.9)','#00f5ff','#00f5ff',14);
  ctx.restore();

  // VISOR
  rRect(-24,-22,48,16,4,'rgba(0,30,50,.85)','#00f5ff','#00f5ff',22);
  // visor animated gradient sheen
  ctx.save();ctx.globalAlpha=0.55+Math.sin(T*3)*0.15;
  const vg=ctx.createLinearGradient(-24,-22,24,-22);
  vg.addColorStop(0,'rgba(0,245,255,.6)');vg.addColorStop(0.5,'rgba(255,0,255,.35)');vg.addColorStop(1,'rgba(0,245,255,.5)');
  ctx.fillStyle=vg;ctx.beginPath();ctx.roundRect(-24,-22,48,16,4);ctx.fill();
  ctx.restore();
  label('NEXUS',-18,-10,'rgba(0,0,0,.85)',8,'Orbitron');

  // EYE glow behind visor
  ctx.save();ctx.globalAlpha=0.7+Math.sin(T*4)*0.15;
  circle(-10,-14,4,'#00f5ff','#00f5ff','#00f5ff',20);
  circle(10,-14,4,'#00f5ff','#00f5ff','#00f5ff',20);
  ctx.restore();

  ctx.restore();
}

/* ── COFFEE ── */
function drawCoffee(X,Y){
  ctx.save();ctx.translate(X,Y);
  // steam
  for(let i=0;i<3;i++){
    const sx=[-10,0,10][i];const phase=T*2.5+i*1.1;
    const sy=Math.sin(phase)*4;
    ctx.save();ctx.globalAlpha=0.45+Math.sin(phase)*0.2;
    ctx.strokeStyle='rgba(180,210,255,.6)';ctx.lineWidth=2;ctx.lineCap='round';
    ctx.beginPath();ctx.moveTo(sx,-8);ctx.bezierCurveTo(sx+5,-18+sy,sx-5,-26+sy,sx+3,-34);
    ctx.stroke();ctx.restore();
  }
  // cup body
  rRect(-22,0,44,36,4,'rgba(20,8,3,.95)','#ff6b35','#ff6b35',18);
  // rim
  rRect(-25,-6,50,8,3,'rgba(25,10,4,.95)','#ff6b35','#ff6b35',12);
  // handle
  ctx.save();ctx.strokeStyle='#ff6b35';ctx.lineWidth=4;glow('#ff6b35',14);
  ctx.beginPath();ctx.arc(26,16,11,Math.PI*0.35,Math.PI*1.65);ctx.stroke();ctx.restore();
  // coffee surface
  ctx.save();
  const cg=ctx.createRadialGradient(0,-2,2,0,-2,18);
  cg.addColorStop(0,'#7a3010');cg.addColorStop(1,'#2a0a00');
  ctx.fillStyle=cg;ctx.beginPath();ctx.ellipse(0,-3,18,5,0,0,Math.PI*2);ctx.fill();
  ctx.restore();
  // latte art swirl
  ctx.save();ctx.globalAlpha=.4;ctx.strokeStyle='#d4885a';ctx.lineWidth=1;
  ctx.beginPath();ctx.arc(0,-3,6,0,Math.PI*1.5);ctx.stroke();
  ctx.beginPath();ctx.arc(3,-4,3,0,Math.PI);ctx.stroke();ctx.restore();
  // label
  label('☕',-11,28,'rgba(255,107,53,.5)',20);
  ctx.restore();
}

/* ── CAT ── */
function drawCat(X,Y){
  ctx.save();ctx.translate(X,Y);
  const purr=Math.sin(T*5)*0.5+0.5;
  const tailA=Math.sin(T*2)*28;

  // TAIL
  ctx.save();ctx.translate(18,50);ctx.rotate((tailA)*Math.PI/180);
  ctx.strokeStyle='#ff00ff';ctx.lineWidth=6;ctx.lineCap='round';glow('#ff00ff',16);
  ctx.beginPath();ctx.moveTo(0,0);ctx.bezierCurveTo(20,-15,40,-5,38,-22);ctx.stroke();
  noGlow();ctx.restore();

  // BODY
  ctx.save();glow('#ff00ff',18);
  ctx.fillStyle='rgba(14,4,28,.97)';ctx.strokeStyle='#ff00ff';ctx.lineWidth=1.5;
  ctx.beginPath();ctx.ellipse(0,24,30,28,0,0,Math.PI*2);ctx.fill();ctx.stroke();ctx.restore();

  // circuit on body
  ctx.save();ctx.strokeStyle='rgba(0,245,255,.3)';ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(-18,18);ctx.lineTo(-6,18);ctx.lineTo(-6,30);ctx.lineTo(10,30);ctx.stroke();
  ctx.beginPath();ctx.arc(-6,18,2.5,0,Math.PI*2);ctx.fillStyle='rgba(0,245,255,.5)';ctx.fill();
  ctx.beginPath();ctx.arc(10,30,2.5,0,Math.PI*2);ctx.fillStyle='rgba(255,0,255,.5)';ctx.fill();
  ctx.restore();

  // NECK
  rRect(-10,0,20,10,3,'rgba(14,4,28,.97)','rgba(255,0,255,.3)');

  // HEAD
  ctx.save();glow('rgba(255,0,255,.4)',16);
  ctx.fillStyle='rgba(14,4,28,.97)';ctx.strokeStyle='#ff00ff';ctx.lineWidth=1.5;
  ctx.beginPath();ctx.ellipse(0,-18,26,22,0,0,Math.PI*2);ctx.fill();ctx.stroke();ctx.restore();

  // EARS
  [[-18,-36],[18,-36]].forEach(([ex,ey])=>{
    ctx.save();glow('rgba(255,0,255,.5)',10);
    ctx.fillStyle='rgba(14,4,28,.97)';ctx.strokeStyle='#ff00ff';ctx.lineWidth=1.2;
    ctx.beginPath();ctx.moveTo(ex-9,ey+14);ctx.lineTo(ex,ey-10);ctx.lineTo(ex+9,ey+14);ctx.closePath();
    ctx.fill();ctx.stroke();
    ctx.fillStyle='rgba(255,0,255,.22)';
    ctx.beginPath();ctx.moveTo(ex-5,ey+10);ctx.lineTo(ex,ey-3);ctx.lineTo(ex+5,ey+10);ctx.closePath();ctx.fill();
    ctx.restore();
  });

  // EYES
  [[-10,-18],[10,-18]].forEach(([ex,ey])=>{
    ctx.save();ctx.globalAlpha=0.7+purr*0.3;
    circle(ex,ey,6,'rgba(0,10,30,.9)','#00f5ff','#00f5ff',20);
    circle(ex,ey,2.5,'#00f5ff',null,'#00f5ff',10);
    ctx.restore();
  });

  // NOSE
  ctx.save();ctx.fillStyle='rgba(255,0,255,.8)';glow('#ff00ff',8);
  ctx.beginPath();ctx.moveTo(-3,-5);ctx.lineTo(0,-9);ctx.lineTo(3,-5);ctx.closePath();ctx.fill();ctx.restore();

  // WHISKERS
  ctx.save();ctx.strokeStyle='rgba(0,245,255,.45)';ctx.lineWidth=1;
  [[-4,-5,-28,-2],[-4,-5,-26,-8],[4,-5,28,-2],[4,-5,26,-8]].forEach(([x1,y1,x2,y2])=>{
    ctx.beginPath();ctx.moveTo(x1,y1);ctx.lineTo(x2,y2);ctx.stroke();
  });
  ctx.restore();

  // CYBER COLLAR
  ctx.save();glow('#00f5ff',14);
  rRect(-18,38,36,10,5,'rgba(0,15,35,.9)','#00f5ff');
  ctx.restore();
  label('NX',-8,47,'rgba(0,245,255,.9)',8,'Orbitron');

  ctx.restore();
}

/* ── MONITOR ── */
function drawMonitor(X,Y){
  ctx.save();ctx.translate(X,Y);

  // stand
  rRect(-12,82,24,16,2,'#0a1830','#1a3a6a','#1a3a6a',8);
  rRect(-28,96,56,6,2,'#0a1830','#1a3a6a');

  // screen outer bezel
  ctx.save();glow('#00f5ff',24);
  rRect(-100,-70,200,156,8,'#040c1a','#00f5ff');
  ctx.restore();

  // screen inner
  ctx.save();
  ctx.beginPath();ctx.roundRect(-92,-62,184,140,5);ctx.clip();
  ctx.fillStyle='#020810';ctx.fillRect(-92,-62,184,140);

  // code content
  const codeLines=[
    ['#ff00ff','import nexus as nx'],
    ['#00f5ff','from brain import AI'],
    ['#888',''],
    ['#f5e642','class Nexi(AI):'],
    ['#00f5ff','  def __init__(self):'],
    ['#00ff88','    self.mode = "cyber"'],
    ['#ff6b35','    self.name = "Nexi"'],
    ['#00f5ff','  def think(self):'],
    ['#ff00ff','    return "\u221e"'],
    ['#f5e642','  def build(self):'],
    ['#00ff88','    nexus.run()'],
  ];
  const activeLine=Math.floor(T*1.2)%codeLines.length;
  codeLines.forEach(([col,code],i)=>{
    const lineY=-55+i*13;
    // active line highlight
    if(i===activeLine){ctx.fillStyle='rgba(0,245,255,.08)';ctx.fillRect(-90,lineY-10,180,13)}
    ctx.save();ctx.font='10px "Share Tech Mono",monospace';ctx.fillStyle=col;ctx.textAlign='left';
    ctx.fillText(code,-86,lineY);ctx.restore();
  });
  // blinking cursor
  if(Math.sin(T*5)>0){
    const curY=-55+activeLine*13;
    const tw=codeLines[activeLine][1].length*6;
    ctx.fillStyle='#00f5ff';ctx.fillRect(-86+tw,curY-9,6,11);
  }
  ctx.restore();

  // screen glow overlay
  ctx.save();ctx.globalAlpha=0.04+Math.sin(T*2)*0.02;
  ctx.fillStyle='#00f5ff';ctx.fillRect(-92,-62,184,140);ctx.restore();

  // corner accents on monitor
  const ac='rgba(0,245,255,.5)';
  [[-100,-70],[ 100,-70],[-100, 86],[ 100, 86]].forEach(([cx,cy])=>{
    const sx=cx<0?1:-1,sy=cy<0?1:-1;
    ctx.save();ctx.strokeStyle=ac;ctx.lineWidth=1.5;glow('#00f5ff',8);
    ctx.beginPath();ctx.moveTo(cx,cy);ctx.lineTo(cx+sx*16,cy);ctx.stroke();
    ctx.beginPath();ctx.moveTo(cx,cy);ctx.lineTo(cx,cy+sy*16);ctx.stroke();
    ctx.restore();
  });

  ctx.restore();
}

/* floating data fragments */
const frags=[
  {x:60,y:20,txt:'01101110',col:'#00f5ff',sz:9,spd:22},
  {x:520,y:80,txt:'AI.run()',col:'#ff00ff',sz:9,spd:18},
  {x:30,y:200,txt:'0xFF00',col:'#f5e642',sz:8,spd:28},
  {x:560,y:300,txt:'∞ LOOP',col:'#00f5ff',sz:9,spd:20},
  {x:80,y:380,txt:'nexus++',col:'#ff00ff',sz:9,spd:16},
  {x:490,y:40,txt:'<cyber>',col:'#00ff88',sz:8,spd:24},
  {x:200,y:450,txt:'CPU:∞',col:'#ff6b35',sz:9,spd:14},
  {x:420,y:410,txt:'v1.nexus',col:'#00f5ff',sz:8,spd:19},
];

/* hex grid bg */
function hexPath(cx,cy,r){
  ctx.beginPath();
  for(let i=0;i<6;i++){const a=Math.PI/3*i-Math.PI/6;i===0?ctx.moveTo(cx+r*Math.cos(a),cy+r*Math.sin(a)):ctx.lineTo(cx+r*Math.cos(a),cy+r*Math.sin(a))}
  ctx.closePath();
}
function drawHex(){
  const positions=[{x:.05,y:.1},{x:.92,y:.05},{x:.05,y:.85},{x:.92,y:.9},{x:.5,y:.02},{x:.5,y:.97},{x:.25,y:.5},{x:.75,y:.5}];
  const W=cv.width,H=cv.height;
  positions.forEach(({x,y},i)=>{
    ctx.save();ctx.globalAlpha=0.05+Math.sin(T+i)*0.025;
    hexPath(x*W,y*H,32);ctx.strokeStyle='#00f5ff';ctx.lineWidth=1;ctx.stroke();ctx.restore();
  });
}

/* data rings */
function dataRing(cx,cy,r,col,spd,off=0){
  ctx.save();ctx.translate(cx,cy);ctx.rotate(T*spd+off);
  ctx.strokeStyle=col;ctx.lineWidth=1;ctx.globalAlpha=.25;ctx.setLineDash([10,16]);
  ctx.beginPath();ctx.arc(0,0,r,0,Math.PI*2);ctx.stroke();ctx.setLineDash([]);
  for(let i=0;i<6;i++){
    const a=Math.PI*2/6*i;
    ctx.save();ctx.globalAlpha=.8;glow(col,10);ctx.fillStyle=col;
    ctx.beginPath();ctx.arc(Math.cos(a)*r,Math.sin(a)*r,2.5,0,Math.PI*2);ctx.fill();ctx.restore();
  }
  ctx.restore();
}

/* scan beam */
let scanY=0;
function scanBeam(){
  const H=cv.height;
  const sg=ctx.createLinearGradient(0,scanY-20,0,scanY+20);
  sg.addColorStop(0,'rgba(0,245,255,0)');sg.addColorStop(.5,'rgba(0,245,255,.05)');sg.addColorStop(1,'rgba(0,245,255,0)');
  ctx.fillStyle=sg;ctx.fillRect(0,scanY-20,cv.width,40);
  scanY+=1.4;if(scanY>H+20)scanY=-20;
}

function draw(){
  const W=cv.width,H=cv.height;
  ctx.clearRect(0,0,W,H);
  ctx.fillStyle='#040810';ctx.fillRect(0,0,W,H);

  // grid
  ctx.save();ctx.strokeStyle='rgba(0,245,255,.03)';ctx.lineWidth=1;
  for(let x=0;x<W;x+=38){ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,H);ctx.stroke()}
  for(let y=0;y<H;y+=38){ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(W,y);ctx.stroke()}
  ctx.restore();

  drawHex();
  scanBeam();

  // center of scene
  const cx=W/2,cy=H/2-20;

  // rings behind everything
  dataRing(cx,cy,Math.min(W,H)*.42,'#00f5ff',.12);
  dataRing(cx,cy,Math.min(W,H)*.3,'#ff00ff',-.18,.5);

  // floating frags
  frags.forEach((f,i)=>{
    const fy=((f.y - T*f.spd)%H+H)%H;
    ctx.save();ctx.globalAlpha=.45+Math.sin(T*1.5+i)*.2;
    label(f.txt,f.x,fy,f.col,f.sz,5);ctx.restore();
  });

  // ── DRAW CHARACTERS ──
  // Monitor top-center
  drawMonitor(cx, cy-120);
  // Boy center-slightly-left
  drawBoy(cx-20, cy+20);
  // Coffee to the right of boy's hand
  drawCoffee(cx+130, cy+100);
  // Cat lower-left
  drawCat(cx-160, cy+110);

  // corner bracket accents
  const bCol='rgba(0,245,255,.2)',bLen=28;
  [[0,0],[W,0],[0,H],[W,H]].forEach(([x,y])=>{
    const sx=x===0?1:-1,sy=y===0?1:-1;
    ctx.save();ctx.strokeStyle=bCol;ctx.lineWidth=1.5;
    ctx.beginPath();ctx.moveTo(x,y);ctx.lineTo(x+sx*bLen,y);ctx.stroke();
    ctx.beginPath();ctx.moveTo(x,y);ctx.lineTo(x,y+sy*bLen);ctx.stroke();
    ctx.restore();
  });

  // status bar
  ctx.save();ctx.fillStyle='rgba(0,10,25,.85)';ctx.fillRect(0,H-26,W,26);
  ctx.strokeStyle='rgba(0,245,255,.18)';ctx.lineWidth=.5;ctx.beginPath();ctx.moveTo(0,H-26);ctx.lineTo(W,H-26);ctx.stroke();
  const d=new Date();
  const ts=`${d.getHours().toString().padStart(2,'0')}:${d.getMinutes().toString().padStart(2,'0')}:${d.getSeconds().toString().padStart(2,'0')}`;
  label(`SYS ${ts} | NEXI.ONLINE | NEXUS.TECH | CPU:OK | RAM:OK`,10,H-9,'rgba(0,245,255,.5)',8.5,0);
  ctx.restore();

  T+=0.016;requestAnimationFrame(draw);
}
draw();
setInterval(()=>{},1000);
</script>
