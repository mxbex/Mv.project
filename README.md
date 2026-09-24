<!DOCTYPE html>
<html lang="ru" data-theme="dark" data-accent="green">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MV.Project | Устав Фонда SCP</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700;800&family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
:root{
  --accent:#00ff88;
  --accent-dim:#00cc66;
  --accent-deep:#009944;
  --accent-rgb:0,255,136;
  --bg:#05070a;
  --bg-2:#080b10;
  --panel:rgba(13,17,23,.72);
  --panel-solid:#0d1117;
  --panel-2:rgba(17,22,29,.85);
  --border:rgba(255,255,255,.06);
  --border-strong:rgba(255,255,255,.1);
  --text:#c4ccd6;
  --text-dim:#7d8896;
  --text-bright:#eef3f8;
  --ease:cubic-bezier(.22,.68,.32,1);
  --ease-out:cubic-bezier(.16,1,.3,1);
  --shadow-lg:0 24px 60px -12px rgba(0,0,0,.75);
  --shadow-glow:0 0 40px rgba(var(--accent-rgb),.15);
  --grid-gap:16px;
  --font-mono:'JetBrains Mono','Consolas','Courier New',monospace;
  --font-sans:'Inter',-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;
}
html[data-accent="cyan"]{--accent:#00ccff;--accent-dim:#00a3cc;--accent-deep:#007a99;--accent-rgb:0,204,255;}
html[data-accent="blue"]{--accent:#4a90d9;--accent-dim:#3a74ad;--accent-deep:#2a5881;--accent-rgb:74,144,217;}
html[data-accent="purple"]{--accent:#b366ff;--accent-dim:#9013fe;--accent-deep:#6d0ebd;--accent-rgb:179,102,255;}
html[data-accent="magenta"]{--accent:#ff44dd;--accent-dim:#cc33b0;--accent-deep:#992284;--accent-rgb:255,68,221;}
html[data-accent="pink"]{--accent:#ff69b4;--accent-dim:#e04d9a;--accent-deep:#b33a7a;--accent-rgb:255,105,180;}
html[data-accent="red"]{--accent:#ff4444;--accent-dim:#cc3333;--accent-deep:#992222;--accent-rgb:255,68,68;}
html[data-accent="orange"]{--accent:#ff8800;--accent-dim:#cc6d00;--accent-deep:#995200;--accent-rgb:255,136,0;}
html[data-accent="amber"]{--accent:#ffaa00;--accent-dim:#cc8800;--accent-deep:#996600;--accent-rgb:255,170,0;}
html[data-accent="yellow"]{--accent:#ffdd00;--accent-dim:#ccb100;--accent-deep:#998500;--accent-rgb:255,221,0;}
html[data-accent="lime"]{--accent:#aaff00;--accent-dim:#88cc00;--accent-deep:#669900;--accent-rgb:170,255,0;}
html[data-accent="white"]{--accent:#fff;--accent-dim:#ccc;--accent-deep:#999;--accent-rgb:255,255,255;}

html[data-theme="light"]{
  --bg:#f0f2f6;
  --bg-2:#e8ebf0;
  --panel:rgba(255,255,255,.78);
  --panel-solid:#ffffff;
  --panel-2:rgba(255,255,255,.92);
  --border:rgba(0,0,0,.07);
  --border-strong:rgba(0,0,0,.12);
  --text:#3a4453;
  --text-dim:#6b7686;
  --text-bright:#0d1117;
  --shadow-lg:0 24px 60px -12px rgba(20,30,50,.18);
  --shadow-glow:0 0 40px rgba(var(--accent-rgb),.12);
}

*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
html,body{width:100%;min-height:100%;}
body{
  font-family:var(--font-sans);
  background:var(--bg);
  color:var(--text);
  line-height:1.75;
  overflow-x:hidden;
  font-size:15px;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
  transition:background-color .5s var(--ease),color .5s var(--ease);
}
::selection{background:rgba(var(--accent-rgb),.28);color:var(--text-bright);}
::-webkit-scrollbar{width:11px;height:11px;}
::-webkit-scrollbar-track{background:transparent;}
::-webkit-scrollbar-thumb{
  background:linear-gradient(180deg,rgba(var(--accent-rgb),.5),rgba(var(--accent-rgb),.2));
  border-radius:6px;
  border:3px solid var(--bg);
}
::-webkit-scrollbar-thumb:hover{background:var(--accent);}

/* ============ SCROLL PROGRESS ============ */
.scroll-progress{
  position:fixed;top:0;left:0;height:2px;width:0%;
  background:linear-gradient(90deg,var(--accent),#00ccff,var(--accent));
  background-size:200% 100%;
  z-index:2000;pointer-events:none;
  box-shadow:0 0 18px rgba(var(--accent-rgb),.9),0 0 6px var(--accent);
  animation:gs 3s linear infinite;
}
@keyframes gs{0%{background-position:0% 50%;}100%{background-position:200% 50%;}}

/* ============ AURORA BACKGROUND ============ */
.aurora{
  position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden;
}
.aurora::before,.aurora::after{
  content:'';position:absolute;border-radius:50%;filter:blur(120px);opacity:.35;
  will-change:transform;
}
.aurora::before{
  width:60vw;height:60vw;top:-20vw;left:-15vw;
  background:radial-gradient(circle,rgba(var(--accent-rgb),.5),transparent 65%);
  animation:aurora1 22s ease-in-out infinite alternate;
}
.aurora::after{
  width:55vw;height:55vw;bottom:-25vw;right:-15vw;
  background:radial-gradient(circle,rgba(var(--accent-rgb),.32),transparent 65%);
  animation:aurora2 26s ease-in-out infinite alternate;
}
html[data-theme="light"] .aurora::before,
html[data-theme="light"] .aurora::after{opacity:.18;}
@keyframes aurora1{0%{transform:translate(0,0) scale(1);}100%{transform:translate(15vw,10vh) scale(1.25);}}
@keyframes aurora2{0%{transform:translate(0,0) scale(1.1);}100%{transform:translate(-12vw,-8vh) scale(.9);}}

/* ============ PARALLAX ============ */
.parallax-bg{position:fixed;top:0;left:0;width:100%;height:100vh;pointer-events:none;z-index:0;overflow:hidden;}
.parallax-layer{position:absolute;top:0;left:0;width:100%;user-select:none;pointer-events:none;will-change:transform;}
.parallax-line{font-weight:800;white-space:nowrap;letter-spacing:30px;padding:50px 0;text-align:center;font-family:var(--font-sans);}
.parallax-layer.back .parallax-line{font-size:6em;color:rgba(var(--accent-rgb),.022);}
.parallax-layer.middle .parallax-line{font-size:8em;color:rgba(var(--accent-rgb),.014);}

/* ============ WATERMARK ============ */
.watermark-overlay{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:1;overflow:hidden;}
.watermark-overlay .wm{
  position:absolute;color:rgba(var(--accent-rgb),.035);font-weight:800;
  font-size:1.4em;letter-spacing:8px;white-space:nowrap;
  transform:rotate(-35deg);user-select:none;pointer-events:none;
  text-transform:uppercase;font-family:var(--font-sans);
}

/* ============ SIDEBAR ============ */
.sidebar{
  position:fixed;top:0;left:0;width:300px;height:100vh;
  background:linear-gradient(180deg,rgba(8,11,16,.96),rgba(5,7,10,.98));
  backdrop-filter:blur(24px) saturate(1.2);
  -webkit-backdrop-filter:blur(24px) saturate(1.2);
  border-right:1px solid var(--border-strong);
  padding:26px 0;overflow-y:auto;z-index:1000;
  box-shadow:8px 0 48px rgba(0,0,0,.6);
  transition:background .5s var(--ease),transform .4s var(--ease);
}
.sidebar::before{
  content:'';position:absolute;top:0;right:0;width:1px;height:100%;
  background:linear-gradient(180deg,transparent,var(--accent),transparent);
  opacity:.5;
}
html[data-theme="light"] .sidebar{
  background:linear-gradient(180deg,rgba(255,255,255,.92),rgba(248,250,252,.96));
  box-shadow:8px 0 48px rgba(20,30,50,.08);
}
.sidebar::-webkit-scrollbar{width:5px;}
.sidebar::-webkit-scrollbar-thumb{background:rgba(var(--accent-rgb),.3);border-radius:3px;border:none;}
.sidebar::-webkit-scrollbar-thumb:hover{background:var(--accent);}
.sidebar::-webkit-scrollbar-track{background:transparent;}

.sidebar-logo{padding:0 26px 26px;border-bottom:1px solid var(--border);margin-bottom:22px;position:relative;}
.sidebar-logo .name{
  font-family:var(--font-sans);
  font-size:1.55em;font-weight:900;letter-spacing:4px;
  background:linear-gradient(120deg,var(--accent),var(--text-bright),var(--accent));
  background-size:200% auto;-webkit-background-clip:text;background-clip:text;
  -webkit-text-fill-color:transparent;display:block;margin-bottom:12px;
  animation:gs 5s linear infinite;
}
.sidebar-logo .classif{
  display:inline-flex;align-items:center;gap:6px;
  background:linear-gradient(135deg,#ff2a2a,#cc0000);
  color:#fff;padding:4px 12px;font-size:.62em;letter-spacing:2.5px;
  font-weight:800;border-radius:6px;
  box-shadow:0 4px 16px rgba(255,42,42,.4);
  animation:blink 2.4s infinite;font-family:var(--font-sans);
}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:.55;}}

.sidebar-nav{padding:0 14px;}
.nav-section{margin-bottom:4px;}
.nav-section-header{
  display:flex;align-items:center;gap:10px;
  color:var(--text-dim);text-decoration:none;
  padding:11px 14px;margin:2px 0;border-radius:10px;
  font-size:.82em;letter-spacing:.8px;font-weight:600;
  transition:.28s var(--ease);
  border:1px solid transparent;cursor:pointer;user-select:none;
  font-family:var(--font-sans);
}
.nav-section-header:hover{
  background:rgba(var(--accent-rgb),.06);
  color:var(--accent);
  border-color:rgba(var(--accent-rgb),.12);
}
.nav-section-header .arrow{font-size:.6em;transition:transform .35s var(--ease);margin-left:auto;opacity:.6;}
.nav-section-header.open .arrow{transform:rotate(90deg);color:var(--accent);opacity:1;}
.nav-section-header.open{color:var(--accent);}
.nav-section-header .label{flex:1;}

.nav-sub{
  max-height:0;overflow:hidden;
  transition:max-height .5s var(--ease),opacity .3s var(--ease);
  padding-left:12px;margin-left:20px;
  border-left:1px solid var(--border-strong);opacity:0;
}
html[data-theme="light"] .nav-sub{border-left-color:rgba(0,0,0,.08);}
.nav-sub.open{max-height:1400px;opacity:1;}
.nav-sub a{
  display:block;color:var(--text-dim);text-decoration:none;
  padding:8px 14px;margin:2px 0;border-radius:8px;
  font-size:.76em;letter-spacing:.3px;
  transition:.25s var(--ease);
  border-left:2px solid transparent;font-family:var(--font-sans);
}
.nav-sub a:hover{
  background:rgba(var(--accent-rgb),.07);color:var(--accent);
  border-left-color:var(--accent-dim);padding-left:18px;
}
.nav-sub a.active{
  background:rgba(var(--accent-rgb),.1);color:var(--accent);
  border-left-color:var(--accent);font-weight:600;
}

/* ============ MAIN CONTENT ============ */
.main-content{
  margin-left:300px;padding:48px 40px 40px;
  min-height:100vh;width:calc(100% - 300px);
  position:relative;z-index:10;
  max-width:1500px;
}
.menu-toggle{
  display:none;position:fixed;top:16px;left:16px;z-index:1100;
  background:var(--accent);color:#000;border:none;
  padding:12px 16px;border-radius:12px;font-weight:800;cursor:pointer;
  font-size:1.1em;box-shadow:0 8px 24px rgba(var(--accent-rgb),.4);
  transition:.3s var(--ease);
}
.menu-toggle:hover{transform:scale(1.06);}
@media(max-width:1000px){
  .sidebar{transform:translateX(-100%);}
  .sidebar.open{transform:translateX(0);}
  .main-content{margin-left:0;padding:80px 16px 40px;width:100%;}
  .menu-toggle{display:block;}
}

/* ============ SEARCH ============ */
.search-box{position:fixed;top:22px;right:28px;width:360px;z-index:1300;}
.search-icon{position:absolute;left:16px;top:50%;transform:translateY(-50%);font-size:.9em;pointer-events:none;opacity:.5;z-index:2;}
.search-box input{
  width:100%;padding:13px 44px 13px 46px;
  background:var(--panel);border:1px solid var(--border-strong);
  border-radius:14px;color:var(--text-bright);
  font-family:var(--font-sans);font-size:.85em;letter-spacing:.4px;
  outline:none;transition:.3s var(--ease);
  backdrop-filter:blur(20px) saturate(1.3);
  -webkit-backdrop-filter:blur(20px) saturate(1.3);
  box-shadow:0 8px 32px rgba(0,0,0,.3);
}
html[data-theme="light"] .search-box input{box-shadow:0 8px 32px rgba(20,30,50,.08);}
.search-box input::placeholder{color:var(--text-dim);}
.search-box input:focus{
  border-color:var(--accent);
  box-shadow:0 0 0 4px rgba(var(--accent-rgb),.1),0 8px 32px rgba(0,0,0,.4),0 0 30px rgba(var(--accent-rgb),.15);
}
.search-clear{
  position:absolute;right:12px;top:50%;transform:translateY(-50%);
  width:26px;height:26px;border-radius:50%;
  background:rgba(var(--accent-rgb),.15);color:var(--accent);
  border:none;cursor:pointer;font-size:.75em;
  display:none;align-items:center;justify-content:center;
  transition:.25s var(--ease);
}
.search-clear:hover{background:var(--accent);color:#000;transform:translateY(-50%) scale(1.1);}
.search-box.has-value .search-clear{display:flex;}
.search-results{
  position:absolute;top:calc(100% + 10px);left:0;right:0;
  background:var(--panel);border:1px solid var(--border-strong);
  border-radius:16px;max-height:440px;overflow-y:auto;
  display:none;opacity:0;transform:translateY(-8px);
  transition:opacity .28s var(--ease),transform .28s var(--ease);
  backdrop-filter:blur(24px) saturate(1.4);
  -webkit-backdrop-filter:blur(24px) saturate(1.4);
  box-shadow:0 28px 64px rgba(0,0,0,.65),0 0 0 1px rgba(var(--accent-rgb),.08);
}
html[data-theme="light"] .search-results{box-shadow:0 28px 64px rgba(20,30,50,.18);}
.search-results.show{display:block;opacity:1;transform:none;}
.search-item{
  display:block;padding:12px 18px 12px 30px;
  color:var(--text);text-decoration:none;
  border-bottom:1px solid var(--border);font-size:.82em;
  cursor:pointer;position:relative;transition:.2s var(--ease);
  font-family:var(--font-sans);
}
.search-item:last-child{border-bottom:none;}
.search-item::before{
  content:'▸';position:absolute;left:12px;top:50%;
  transform:translateY(-50%);color:var(--accent);opacity:0;transition:.2s;
}
.search-item:hover,.search-item.active{
  background:rgba(var(--accent-rgb),.08);color:var(--text-bright);padding-left:36px;
}
.search-item:hover::before,.search-item.active::before{opacity:1;}
.search-tag{
  display:inline-block;color:var(--accent-dim);font-size:.68em;
  letter-spacing:1.5px;text-transform:uppercase;margin-right:8px;
  padding:2px 8px;background:rgba(var(--accent-rgb),.08);
  border-radius:6px;font-weight:700;font-family:var(--font-sans);
}
.search-item mark{background:rgba(var(--accent-rgb),.25);color:var(--accent);padding:1px 3px;border-radius:4px;}
@media(max-width:1000px){
  .search-box{top:16px;right:16px;width:calc(100% - 100px);max-width:340px;}
}

/* ============ SETTINGS ============ */
.settings-wrap{position:fixed;top:80px;right:28px;z-index:1290;}
.settings-toggle{
  width:44px;height:44px;border-radius:14px;
  background:var(--panel);border:1px solid var(--border-strong);
  color:var(--accent);font-size:1.15em;line-height:1;
  cursor:pointer;display:flex;align-items:center;justify-content:center;
  transition:transform .5s var(--ease),box-shadow .3s var(--ease),background .3s;
  backdrop-filter:blur(20px) saturate(1.3);
  -webkit-backdrop-filter:blur(20px) saturate(1.3);
  box-shadow:0 8px 32px rgba(0,0,0,.3);
}
html[data-theme="light"] .settings-toggle{box-shadow:0 8px 32px rgba(20,30,50,.08);}
.settings-toggle:hover{
  transform:rotate(90deg) scale(1.08);
  box-shadow:0 0 30px rgba(var(--accent-rgb),.5);
  border-color:var(--accent);
}
.settings-toggle.active{transform:rotate(180deg);background:rgba(var(--accent-rgb),.12);border-color:var(--accent);}
.settings-panel{
  position:absolute;top:calc(100% + 12px);right:0;width:320px;
  background:var(--panel);border:1px solid var(--border-strong);
  border-radius:18px;padding:20px;
  opacity:0;transform:translateY(-10px) scale(.96);
  pointer-events:none;
  transition:opacity .3s var(--ease),transform .3s var(--ease);
  backdrop-filter:blur(28px) saturate(1.4);
  -webkit-backdrop-filter:blur(28px) saturate(1.4);
  box-shadow:0 28px 72px rgba(0,0,0,.7),0 0 0 1px rgba(var(--accent-rgb),.08),0 0 60px rgba(var(--accent-rgb),.06);
}
html[data-theme="light"] .settings-panel{box-shadow:0 28px 72px rgba(20,30,50,.2);}
.settings-panel.show{opacity:1;transform:none;pointer-events:auto;}
.settings-title{
  color:var(--accent);font-size:.72em;letter-spacing:3px;
  font-weight:800;text-transform:uppercase;
  padding-bottom:14px;margin-bottom:18px;
  border-bottom:1px solid var(--border);
  display:flex;align-items:center;gap:10px;font-family:var(--font-sans);
}
.settings-group{margin-bottom:20px;}
.settings-label{
  color:var(--text-dim);font-size:.66em;letter-spacing:2.5px;
  text-transform:uppercase;margin-bottom:10px;font-weight:700;
  font-family:var(--font-sans);
}
.theme-options{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.theme-btn{
  padding:11px 12px;background:rgba(255,255,255,.03);
  border:1px solid var(--border-strong);border-radius:12px;
  color:var(--text-dim);font-family:var(--font-sans);
  font-size:.76em;letter-spacing:.5px;font-weight:600;
  cursor:pointer;transition:.28s var(--ease);
  display:flex;align-items:center;justify-content:center;gap:7px;
}
html[data-theme="light"] .theme-btn{background:rgba(0,0,0,.02);}
.theme-btn:hover{border-color:var(--accent);color:var(--accent);transform:translateY(-2px);}
.theme-btn.active{
  border-color:var(--accent);color:var(--accent);
  background:rgba(var(--accent-rgb),.12);
  box-shadow:0 0 20px rgba(var(--accent-rgb),.2);
}
.color-grid{display:grid;grid-template-columns:repeat(6,1fr);gap:9px;}
.color-swatch{
  width:100%;aspect-ratio:1;border-radius:50%;
  border:2px solid rgba(255,255,255,.08);
  cursor:pointer;padding:0;transition:transform .25s var(--ease),box-shadow .25s;
  position:relative;
}
.color-swatch:hover{transform:scale(1.18);box-shadow:0 0 20px currentColor;}
.color-swatch.active{
  border-color:#fff;
  box-shadow:0 0 0 2px var(--accent),0 0 16px var(--accent);
  transform:scale(1.12);
}
.settings-reset{
  width:100%;padding:11px;background:rgba(255,255,255,.03);
  border:1px solid var(--border-strong);border-radius:12px;
  color:var(--text-dim);font-family:var(--font-sans);
  font-size:.72em;letter-spacing:1.5px;cursor:pointer;
  transition:.28s var(--ease);text-transform:uppercase;font-weight:700;
}
html[data-theme="light"] .settings-reset{background:rgba(0,0,0,.02);}
.settings-reset:hover{color:#ff6666;border-color:#ff4444;background:rgba(255,0,0,.08);}
@media(max-width:1000px){.settings-wrap{top:70px;right:16px;}.settings-panel{width:280px;}}

/* ============ HEADER ============ */
.header{
  text-align:center;padding:60px 20px 50px;
  border-bottom:1px solid var(--border-strong);
  margin-bottom:60px;position:relative;overflow:hidden;
  border-radius:24px;
  background:radial-gradient(ellipse at 50% 0%,rgba(var(--accent-rgb),.06),transparent 70%);
}
.header::after{
  content:'';position:absolute;bottom:0;left:-100%;width:60%;height:1px;
  background:linear-gradient(90deg,transparent,var(--accent),transparent);
  animation:sh 5s ease-in-out infinite;
}
@keyframes sh{0%{left:-60%;}60%,100%{left:120%;}}
.classification{
  display:inline-flex;align-items:center;gap:8px;
  background:linear-gradient(135deg,#ff2a2a,#cc0000);
  color:#fff;padding:9px 26px;font-weight:800;
  letter-spacing:4px;font-size:.8em;margin-bottom:32px;
  border-radius:10px;
  box-shadow:0 8px 32px rgba(255,0,0,.35),0 0 0 1px rgba(255,255,255,.1) inset;
  animation:blink 2.4s infinite;font-family:var(--font-sans);
}
h1{
  font-family:var(--font-sans);
  font-size:clamp(2.4em,7vw,5em);font-weight:900;
  background:linear-gradient(120deg,var(--accent),var(--text-bright),var(--accent-dim),var(--accent));
  background-size:300% auto;-webkit-background-clip:text;background-clip:text;
  -webkit-text-fill-color:transparent;
  letter-spacing:8px;margin-bottom:18px;
  animation:gs 7s linear infinite;
  filter:drop-shadow(0 0 40px rgba(var(--accent-rgb),.25));
  line-height:1.1;
}
.subtitle{
  color:var(--accent);font-size:clamp(.85em,1.8vw,1.05em);
  letter-spacing:5px;font-weight:600;text-transform:uppercase;
  font-family:var(--font-sans);
}
.codename{color:var(--text-dim);font-size:.85em;margin-top:18px;letter-spacing:1.5px;font-family:var(--font-mono);}

/* ============ TYPOGRAPHY ============ */
h2{
  font-family:var(--font-sans);
  color:var(--text-bright);
  font-size:clamp(1.4em,3vw,2em);font-weight:800;
  margin:70px 0 30px;padding:22px 28px 22px 32px;
  border-left:4px solid var(--accent);
  background:linear-gradient(90deg,rgba(var(--accent-rgb),.09),transparent 70%);
  border-radius:0 16px 16px 0;
  letter-spacing:1px;
  scroll-margin-top:30px;position:relative;
  transition:.35s var(--ease);
  display:flex;align-items:center;gap:14px;
}
h2::before{
  content:'';position:absolute;left:-4px;top:20%;bottom:20%;
  width:4px;background:var(--accent);
  box-shadow:0 0 24px var(--accent),0 0 8px var(--accent);
  border-radius:2px;
}
h2:hover{
  padding-left:40px;
  background:linear-gradient(90deg,rgba(var(--accent-rgb),.15),transparent 70%);
}
h3{
  font-family:var(--font-sans);
  color:var(--accent-dim);
  font-size:clamp(1.05em,2.2vw,1.35em);font-weight:700;
  margin:40px 0 20px;padding-left:20px;
  border-left:3px solid var(--accent-dim);
  letter-spacing:.6px;scroll-margin-top:30px;
  transition:.35s var(--ease);
  display:flex;align-items:center;gap:10px;
}
h3:hover{border-left-color:var(--accent);padding-left:28px;color:var(--accent);}
h4{
  font-family:var(--font-sans);
  color:var(--accent);font-size:1.05em;font-weight:700;
  margin:26px 0 14px;letter-spacing:.5px;
}
p{margin:14px 0;color:var(--text);}
strong{color:var(--accent);font-weight:700;}
ul,ol{padding-left:28px;margin:18px 0;}
li{padding:7px 0 7px 8px;color:var(--text);border-bottom:1px solid transparent;transition:.25s var(--ease);}
li:hover{color:var(--text-bright);border-bottom-color:rgba(var(--accent-rgb),.2);padding-left:14px;}

/* ============ GRIDS ============ */
.two-col-grid,.code-grid,.clearance-grid{
  display:grid;grid-template-columns:repeat(2,minmax(0,1fr));
  gap:var(--grid-gap);margin:22px 0;width:100%;align-items:start;
}
@media(max-width:1200px){.two-col-grid,.code-grid,.clearance-grid{grid-template-columns:1fr;}}

/* ============ TABLES ============ */
.data-table{
  width:100%;border-collapse:separate;border-spacing:0;
  background:var(--panel);border:1px solid var(--border-strong);
  font-size:.88em;table-layout:auto;border-radius:14px;overflow:hidden;
  transition:.35s var(--ease);font-family:var(--font-sans);
}
html[data-theme="light"] .data-table{background:rgba(255,255,255,.9);}
.data-table th{
  background:linear-gradient(180deg,rgba(var(--accent-rgb),.1),rgba(var(--accent-rgb),.04));
  color:var(--accent);padding:16px 18px;text-align:left;
  font-weight:800;letter-spacing:1.5px;
  border-bottom:2px solid rgba(var(--accent-rgb),.3);
  text-transform:uppercase;font-size:.78em;
}
html[data-theme="light"] .data-table th{color:#1a1a1a;background:linear-gradient(180deg,rgba(var(--accent-rgb),.14),rgba(var(--accent-rgb),.06));}
.data-table td{
  padding:14px 18px;border-bottom:1px solid var(--border);
  color:var(--text);vertical-align:top;line-height:1.7;transition:.25s var(--ease);
}
html[data-theme="light"] .data-table td{color:#333;}
.data-table tr:last-child td{border-bottom:none;}
.data-table tbody tr{transition:.25s var(--ease);}
.data-table tbody tr:hover td{background:rgba(var(--accent-rgb),.05);color:var(--text-bright);}
html[data-theme="light"] .data-table tbody tr:hover td{background:rgba(var(--accent-rgb),.07);color:#000;}
.data-table tbody tr:hover td:first-child{box-shadow:inset 3px 0 0 var(--accent);}
.data-table strong{color:var(--accent);}

.table-wrap{
  background:var(--panel);border-radius:16px;overflow:hidden;
  margin:18px 0;width:100%;border:1px solid var(--border-strong);
  transition:.35s var(--ease);
}
html[data-theme="light"] .table-wrap{background:rgba(255,255,255,.9);}
.table-wrap:hover{
  border-color:rgba(var(--accent-rgb),.3);
  box-shadow:0 16px 48px rgba(0,0,0,.4),0 0 0 1px rgba(var(--accent-rgb),.1);
}
html[data-theme="light"] .table-wrap:hover{box-shadow:0 16px 48px rgba(20,30,50,.12);}

/* ============ CODE CARDS ============ */
.code-card{
  padding:26px;border-radius:18px;
  background:var(--panel-2);border:1px solid;border-top-width:3px;
  transition:.4s var(--ease);position:relative;overflow:hidden;isolation:isolate;
  backdrop-filter:blur(16px) saturate(1.2);
  -webkit-backdrop-filter:blur(16px) saturate(1.2);
}
html[data-theme="light"] .code-card{background:rgba(255,255,255,.92);}
.code-card::after{
  content:'';position:absolute;top:0;left:-120%;width:60%;height:100%;
  background:linear-gradient(100deg,transparent,rgba(255,255,255,.07),transparent);
  transform:skewX(-18deg);transition:left .8s var(--ease);pointer-events:none;
}
.code-card:hover::after{left:140%;}
.code-card:hover{
  transform:translateY(-8px);
  box-shadow:0 24px 64px rgba(0,0,0,.6),0 0 0 1px rgba(var(--accent-rgb),.15);
}
html[data-theme="light"] .code-card:hover{box-shadow:0 24px 64px rgba(20,30,50,.15);}
.code-card h4{font-size:1.3em;margin-bottom:14px;letter-spacing:2px;font-family:var(--font-sans);}
.code-card p{font-size:.9em;color:var(--text-dim);margin-bottom:10px;}
.code-red{border-color:rgba(255,0,0,.4);border-top-color:#ff0000;background:linear-gradient(135deg,var(--panel-2),rgba(255,0,0,.05));}
.code-red h4{color:#ff4444;text-shadow:0 0 20px rgba(255,0,0,.4);}
.code-black{border-color:rgba(80,80,80,.4);border-top-color:#555;background:linear-gradient(135deg,var(--panel-2),rgba(60,60,60,.06));}
.code-black h4{color:#999;text-shadow:0 0 20px rgba(150,150,150,.4);}
.code-green{border-color:rgba(var(--accent-rgb),.4);border-top-color:var(--accent);background:linear-gradient(135deg,var(--panel-2),rgba(var(--accent-rgb),.05));}
.code-green h4{color:var(--accent);text-shadow:0 0 20px rgba(var(--accent-rgb),.4);}
.code-blue{border-color:rgba(74,144,217,.4);border-top-color:#4a90d9;background:linear-gradient(135deg,var(--panel-2),rgba(74,144,217,.05));}
.code-blue h4{color:#4a90d9;text-shadow:0 0 20px rgba(74,144,217,.4);}
.code-superblue{border-color:rgba(0,204,255,.4);border-top-color:#00ccff;background:linear-gradient(135deg,var(--panel-2),rgba(0,204,255,.05));}
.code-superblue h4{color:#00ccff;text-shadow:0 0 20px rgba(0,204,255,.4);}
.code-yellow{border-color:rgba(255,204,0,.4);border-top-color:#ffcc00;background:linear-gradient(135deg,var(--panel-2),rgba(255,204,0,.05));}
.code-yellow h4{color:#ffcc00;text-shadow:0 0 20px rgba(255,204,0,.4);}
.code-purple{border-color:rgba(144,19,254,.4);border-top-color:#9013fe;background:linear-gradient(135deg,var(--panel-2),rgba(144,19,254,.05));}
.code-purple h4{color:#b366ff;text-shadow:0 0 20px rgba(144,19,254,.4);}
.code-white{border-color:rgba(204,204,204,.3);border-top-color:#ccc;background:linear-gradient(135deg,var(--panel-2),rgba(200,200,200,.05));}
.code-white h4{color:#ddd;text-shadow:0 0 20px rgba(200,200,200,.3);}
.code-gray{border-color:rgba(136,136,136,.4);border-top-color:#888;background:linear-gradient(135deg,var(--panel-2),rgba(136,136,136,.06));}
.code-gray h4{color:#aaa;text-shadow:0 0 20px rgba(150,150,150,.4);}
.code-silver{border-color:rgba(192,192,192,.4);border-top-color:#c0c0c0;background:linear-gradient(135deg,var(--panel-2),rgba(192,192,192,.05));}
.code-silver h4{color:#c0c0c0;text-shadow:0 0 20px rgba(192,192,192,.4);}
.code-clean{border-color:rgba(224,224,224,.3);border-top-color:#e0e0e0;background:linear-gradient(135deg,var(--panel-2),rgba(224,224,224,.04));}
.code-clean h4{color:#e0e0e0;text-shadow:0 0 20px rgba(224,224,224,.3);}
.code-superclean{border-color:rgba(255,105,180,.4);border-top-color:#ff69b4;background:linear-gradient(135deg,var(--panel-2),rgba(255,105,180,.05));}
.code-superclean h4{color:#ff69b4;text-shadow:0 0 20px rgba(255,105,180,.4);}

/* ============ ALERTS ============ */
.alert{
  padding:20px 26px;border-radius:14px;margin:22px 0;
  border-left:4px solid;font-size:.92em;
  transition:.35s var(--ease);
  backdrop-filter:blur(12px);
  -webkit-backdrop-filter:blur(12px);
  background:var(--panel);
}
.alert:hover{transform:translateX(6px);}
.alert-danger{background:linear-gradient(90deg,rgba(255,0,0,.08),rgba(255,0,0,.03));border-color:#ff0000;color:#ff9999;}
.alert-info{background:linear-gradient(90deg,rgba(var(--accent-rgb),.07),rgba(var(--accent-rgb),.02));border-color:var(--accent);color:var(--accent-dim);}
.alert-warning{background:linear-gradient(90deg,rgba(255,170,0,.08),rgba(255,170,0,.03));border-color:#ffaa00;color:#ffcc66;}

/* ============ SECTIONS ============ */
.section{
  margin:26px 0;padding:28px;background:var(--panel);
  border-radius:18px;border:1px solid var(--border-strong);
  transition:.35s var(--ease);
  backdrop-filter:blur(16px) saturate(1.2);
  -webkit-backdrop-filter:blur(16px) saturate(1.2);
}
html[data-theme="light"] .section{background:rgba(255,255,255,.92);}
.section:hover{
  border-color:rgba(var(--accent-rgb),.25);
  box-shadow:0 12px 40px rgba(0,0,0,.3),0 0 0 1px rgba(var(--accent-rgb),.08);
}
html[data-theme="light"] .section:hover{box-shadow:0 12px 40px rgba(20,30,50,.1);}

/* ============ FOOTER ============ */
.footer{
  text-align:center;margin-top:80px;padding:50px 20px;
  border-top:1px solid var(--border-strong);
  color:var(--text-dim);font-size:.82em;letter-spacing:1px;
  background:var(--panel);border-radius:20px;
  transition:background .5s var(--ease);
  backdrop-filter:blur(16px);
  -webkit-backdrop-filter:blur(16px);
}

/* ============ BUTTONS ============ */
.discord,.telegram,.youtube{
  display:inline-flex;align-items:center;gap:10px;
  color:#fff;padding:16px 36px;border-radius:14px;
  text-decoration:none;font-weight:800;margin:8px;
  transition:.35s var(--ease);letter-spacing:1.5px;font-size:.9em;
  position:relative;overflow:hidden;
  box-shadow:0 8px 32px rgba(0,0,0,.3);
  font-family:var(--font-sans);
}
.discord::after,.telegram::after,.youtube::after{
  content:'';position:absolute;top:0;left:-120%;width:60%;height:100%;
  background:linear-gradient(100deg,transparent,rgba(255,255,255,.4),transparent);
  transform:skewX(-18deg);
}
.discord:hover::after,.telegram:hover::after,.youtube:hover::after{animation:btnShine .9s var(--ease);}
@keyframes btnShine{to{left:150%;}}
.discord{background:linear-gradient(135deg,#5865F2,#4752c4);}
.discord:hover{transform:translateY(-4px) scale(1.04);box-shadow:0 16px 48px rgba(88,101,242,.6);}
.telegram{background:linear-gradient(135deg,#0088cc,#006699);}
.telegram:hover{transform:translateY(-4px) scale(1.04);box-shadow:0 16px 48px rgba(0,136,204,.6);}
.youtube{background:linear-gradient(135deg,#ff0000,#cc0000);}
.youtube:hover{transform:translateY(-4px) scale(1.04);box-shadow:0 16px 48px rgba(255,0,0,.6);}

.center{text-align:center;}

/* ============ ACCORDION ============ */
.acc{
  background:var(--panel);border:1px solid var(--border-strong);
  border-radius:16px;overflow:hidden;align-self:start;
  transition:.4s var(--ease);
  backdrop-filter:blur(16px);
  -webkit-backdrop-filter:blur(16px);
}
html[data-theme="light"] .acc{background:rgba(255,255,255,.92);}
.acc:hover{border-color:rgba(var(--accent-rgb),.3);transform:translateY(-3px);}
.acc.open{
  border-color:rgba(var(--accent-rgb),.45);
  box-shadow:0 20px 56px rgba(0,0,0,.5),0 0 0 1px rgba(var(--accent-rgb),.12);
}
html[data-theme="light"] .acc.open{box-shadow:0 20px 56px rgba(20,30,50,.12);}
.acc-head{
  width:100%;text-align:left;cursor:pointer;
  color:var(--accent);font-family:var(--font-sans);
  font-size:.95em;font-weight:700;letter-spacing:.5px;
  background:rgba(var(--accent-rgb),.04);
  border:none;border-left:4px solid var(--accent);
  padding:18px 22px;display:flex;align-items:center;gap:12px;
  transition:.3s var(--ease);
}
html[data-theme="light"] .acc-head{background:rgba(var(--accent-rgb),.05);}
.acc-head:hover{background:rgba(var(--accent-rgb),.09);padding-left:28px;}
.acc.open .acc-head{border-left-color:#ffaa00;color:#ffaa00;background:rgba(255,170,0,.06);}
.acc-head .acc-arrow{margin-left:auto;font-size:.65em;transition:transform .4s var(--ease);}
.acc.open .acc-head .acc-arrow{transform:rotate(90deg);}
.acc-body{display:grid;grid-template-rows:0fr;transition:grid-template-rows .5s var(--ease);}
.acc.open .acc-body{grid-template-rows:1fr;}
.acc-inner{overflow:hidden;}
.acc-inner>*{padding:0 22px;}
.acc-inner>*:first-child{padding-top:18px;}
.acc-inner>*:last-child{padding-bottom:18px;}

/* ============ HIGHLIGHT ============ */
.highlight{
  background:rgba(var(--accent-rgb),.12);padding:2px 10px;
  border-radius:6px;color:var(--accent);font-weight:600;
}
.critical{
  background:rgba(255,0,0,.15);padding:2px 10px;
  border-radius:6px;color:#ff6666;font-weight:700;
}

/* ============ DIVIDER ============ */
.divider{
  height:1px;border:none;margin:60px 0;
  background:linear-gradient(90deg,transparent,rgba(var(--accent-rgb),.5),transparent);
  opacity:.6;
}

/* ============ CLEARANCE CARDS ============ */
.clearance-card{
  padding:26px;border-radius:18px;
  border:1px solid;border-top-width:3px;
  background:var(--panel-2);
  transition:.4s var(--ease);position:relative;overflow:hidden;
  backdrop-filter:blur(16px) saturate(1.2);
  -webkit-backdrop-filter:blur(16px) saturate(1.2);
}
html[data-theme="light"] .clearance-card{background:rgba(255,255,255,.92);}
.clearance-card::after{
  content:'';position:absolute;top:0;left:0;right:0;height:100%;
  background:radial-gradient(circle at top right,rgba(var(--accent-rgb),.08),transparent 60%);
  opacity:0;transition:opacity .4s;pointer-events:none;
}
.clearance-card:hover::after{opacity:1;}
.clearance-card:hover{
  transform:translateY(-8px);
  box-shadow:0 24px 64px rgba(0,0,0,.6),0 0 0 1px rgba(var(--accent-rgb),.12);
}
html[data-theme="light"] .clearance-card:hover{box-shadow:0 24px 64px rgba(20,30,50,.15);}
.clearance-card h4{font-size:1.35em;margin-bottom:14px;letter-spacing:2px;font-family:var(--font-sans);}
.clearance-card p{font-size:.88em;color:var(--text-dim);}

.level-1{border-color:rgba(102,102,102,.5);border-top-color:#777;}
.level-1 h4{color:#aaa;}
.level-2{border-color:rgba(245,166,35,.5);border-top-color:#f5a623;}
.level-2 h4{color:#f5a623;}
.level-3{border-color:rgba(208,2,27,.5);border-top-color:#d0021b;}
.level-3 h4{color:#ff4444;}
.level-4{border-color:rgba(144,19,254,.5);border-top-color:#9013fe;}
.level-4 h4{color:#b366ff;}
.level-5{border-color:rgba(var(--accent-rgb),.5);border-top-color:var(--accent);}
.level-5 h4{color:var(--accent);}
.level-a{border-color:rgba(255,0,0,.5);border-top-color:#ff0000;}
.level-a h4{color:#ff4444;}
.level-b{border-color:rgba(255,136,0,.5);border-top-color:#ff8800;}
.level-b h4{color:#ff8800;}
.level-c{border-color:rgba(0,204,255,.5);border-top-color:#00ccff;}
.level-c h4{color:#00ccff;}
.level-d{border-color:rgba(102,102,102,.5);border-top-color:#777;}
.level-d h4{color:#aaa;}
.level-e{border-color:rgba(144,19,254,.5);border-top-color:#9013fe;}
.level-e h4{color:#b366ff;}

/* ============ PRIV / ITEM / SCP CARDS ============ */
.priv-card,.item-card,.scp-card{
  padding:26px;border-radius:18px;
  background:var(--panel-2);border:1px solid;
  transition:.4s var(--ease);position:relative;overflow:hidden;
  backdrop-filter:blur(16px) saturate(1.2);
  -webkit-backdrop-filter:blur(16px) saturate(1.2);
}
html[data-theme="light"] .priv-card,
html[data-theme="light"] .item-card,
html[data-theme="light"] .scp-card{background:rgba(255,255,255,.92);}
.priv-card::after,.item-card::after,.scp-card::after{
  content:'';position:absolute;top:0;left:-120%;width:60%;height:100%;
  background:linear-gradient(100deg,transparent,rgba(255,255,255,.07),transparent);
  transform:skewX(-18deg);transition:left .9s var(--ease);pointer-events:none;
}
.priv-card:hover::after,.item-card:hover::after,.scp-card:hover::after{left:140%;}
.priv-card:hover,.item-card:hover,.scp-card:hover{
  transform:translateY(-8px);
  box-shadow:0 24px 64px rgba(0,0,0,.6),0 0 40px rgba(var(--accent-rgb),.08);
}
html[data-theme="light"] .priv-card:hover,
html[data-theme="light"] .item-card:hover,
html[data-theme="light"] .scp-card:hover{box-shadow:0 24px 64px rgba(20,30,50,.15);}
.priv-card h4,.scp-card h4{color:var(--accent);font-size:1.2em;margin-bottom:14px;letter-spacing:1.5px;font-family:var(--font-sans);}
.item-card h4{font-size:1.2em;margin-bottom:14px;letter-spacing:1.5px;font-family:var(--font-sans);}
.item-yes{border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);}
.item-yes h4{color:var(--accent);}
.item-no{border-color:rgba(255,0,0,.35);border-top:3px solid #ff0000;}
.item-no h4{color:#ff6666;}
.item-arrest{border-color:rgba(255,170,0,.35);border-top:3px solid #ffaa00;}
.item-arrest h4{color:#ffaa00;}
.item-execute{border-color:rgba(208,2,27,.35);border-top:3px solid #d0021b;}
.item-execute h4{color:#ff3333;}

/* ============ BADGES ============ */
.hp-badge{
  display:inline-flex;align-items:center;gap:6px;
  background:rgba(255,0,0,.12);border:1px solid rgba(255,68,68,.4);
  color:#ff8888;padding:5px 14px;border-radius:8px;
  font-size:.8em;font-weight:700;margin-bottom:14px;letter-spacing:1px;
  font-family:var(--font-mono);
}
.evacuated-badge{
  display:inline-flex;align-items:center;gap:6px;
  background:rgba(255,170,0,.12);border:1px solid rgba(255,170,0,.4);
  color:#ffcc66;padding:5px 14px;border-radius:8px;
  font-size:.8em;font-weight:700;margin-bottom:14px;letter-spacing:1px;
  animation:blink 2.4s infinite;font-family:var(--font-sans);
}

/* ============ REVEAL ============ */
.reveal{
  opacity:0;transform:translateY(36px);
  transition:opacity .9s var(--ease-out),transform .9s var(--ease-out);
  will-change:opacity,transform;
}
.reveal.in{opacity:1;transform:none;}

/* ============ TO TOP ============ */
.to-top{
  position:fixed;right:28px;bottom:28px;width:54px;height:54px;
  border-radius:16px;
  background:linear-gradient(135deg,var(--accent),var(--accent-deep));
  color:#000;border:none;cursor:pointer;font-size:1.3em;font-weight:800;
  display:flex;align-items:center;justify-content:center;z-index:1500;
  opacity:0;transform:translateY(24px) scale(.8);pointer-events:none;
  transition:.45s var(--ease);
  box-shadow:0 8px 32px rgba(var(--accent-rgb),.45),0 0 0 1px rgba(255,255,255,.1) inset;
}
.to-top.show{opacity:1;transform:none;pointer-events:auto;}
.to-top:hover{
  transform:translateY(-5px) scale(1.08);
  box-shadow:0 16px 48px rgba(var(--accent-rgb),.7),0 0 40px rgba(var(--accent-rgb),.4);
}
@media(max-width:1000px){.to-top{right:16px;bottom:16px;width:48px;height:48px;}}

/* ============ REDUCED MOTION ============ */
@media(prefers-reduced-motion:reduce){
  *,*::before,*::after{animation:none !important;transition:none !important;}
  .reveal{opacity:1;transform:none;}
  .parallax-bg,.watermark-overlay{display:none;}
  .aurora{display:none;}
}
</style>
</head>
<body>

<div class="scroll-progress" id="scrollProgress"></div>

<div class="aurora"></div>

<div class="parallax-bg">
  <div class="parallax-layer back" id="layer-back"></div>
  <div class="parallax-layer middle" id="layer-middle"></div>
</div>

<div class="watermark-overlay" id="watermark-overlay"></div>

<!-- SETTINGS -->
<div class="settings-wrap" id="settingsWrap">
  <button class="settings-toggle" id="settingsToggle" type="button" aria-label="Настройки">⚙</button>
  <div class="settings-panel" id="settingsPanel">
    <div class="settings-title"><span>⚙</span> Кастомизация</div>
    <div class="settings-group">
      <div class="settings-label">Тема</div>
      <div class="theme-options">
        <button class="theme-btn" data-theme="dark" type="button">🌙 Тёмная</button>
        <button class="theme-btn" data-theme="light" type="button">☀ Светлая</button>
      </div>
    </div>
    <div class="settings-group">
      <div class="settings-label">Основной цвет</div>
      <div class="color-grid" id="colorGrid"></div>
    </div>
    <button class="settings-reset" id="settingsReset" type="button">Сбросить</button>
  </div>
</div>

<button class="menu-toggle" onclick="document.querySelector('.sidebar').classList.toggle('open')">☰</button>

<div class="search-box" id="searchBox">
  <span class="search-icon">🔍</span>
  <input type="text" id="searchInput" placeholder="Поиск по уставу..." autocomplete="off" spellcheck="false">
  <button class="search-clear" id="searchClear" type="button" aria-label="Очистить">✕</button>
  <div class="search-results" id="searchResults"></div>
</div>

<aside class="sidebar">
  <div class="sidebar-logo">
    <span class="name">MV.PROJECT</span>
    <span class="classif">⚠ LEVEL 5 ⚠</span>
  </div>
  <nav class="sidebar-nav">
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>🚨</span><span class="label">КОДЫ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#codes">Все коды угроз</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>🔐</span><span class="label">ДОПУСК</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#clearance">Уровни 1-5</a><a href="#classes-personnel">Классы A-E</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>🛡️</span><span class="label">МОГ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#mtf">Основные МОГ</a><a href="#mtf-dop">Дополнительные МОГ</a><a href="#mtf-tg">Тактические группы</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>📋</span><span class="label">ПРОТОКОЛЫ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#prot-p-l">Протоколы P-L</a><a href="#prot-p-s">Протоколы P-S</a><a href="#prot-p-b">Протоколы P-B</a><a href="#prot-p-i">Протоколы P-I</a><a href="#prot-p-e">Протоколы P-E</a><a href="#prot-kir">Изоляционные коды</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>⭐</span><span class="label">ПРИВИЛЕГИИ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#priv-obligations">Обязанности админа</a><a href="#priv-forbidden">Запреты</a><a href="#priv-lies">Наказания за враньё</a><a href="#priv-confidential">Конфиденциальность</a><a href="#priv-others">Админство на других</a><a href="#priv-hierarchy">Иерархия</a><a href="#priv-punish">Виды взысканий</a><a href="#priv-rights">Права админов</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>👔</span><span class="label">ФОРМА</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#uniform">Что можно носить</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>🎒</span><span class="label">ПРЕДМЕТЫ И АРЕСТ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#items-can">Что можно носить</a><a href="#items-cant">Что нельзя носить</a><a href="#items-arrest">Арест персонала</a><a href="#items-execute">Расстрел класса D</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>📜</span><span class="label">ОБЩИЕ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#general">Принципы и возраст</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>🎭</span><span class="label">RP</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#rp">Все RP-правила</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>👥</span><span class="label">КЛАССЫ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#classes">Игровые классы</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>🧬</span><span class="label">SCP</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#scp">Основные SCP</a><a href="#scp953">SCP-953</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>⚙️</span><span class="label">SCP-914</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#scp914">Правила 914</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>📢</span><span class="label">ИНТЕРКОМ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#intercom">Правила интеркома</a><a href="#chat">Правила чата</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>⏱️</span><span class="label">БАНЫ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#bans">Сроки наказаний</a></div>
    </div>
    <div class="nav-section">
      <div class="nav-section-header" onclick="toggleSection(this)"><span>📩</span><span class="label">АПЕЛЛЯЦИЯ</span><span class="arrow">▶</span></div>
      <div class="nav-sub"><a href="#appeal">Процедура апелляции</a></div>
    </div>
  </nav>
</aside>

<main class="main-content">

  <div class="header">
    <div class="classification">⚠ CLASSIFIED — LEVEL 5 CLEARANCE ⚠</div>
    <h1>MV.PROJECT</h1>
    <p class="subtitle">SCP FOUNDATION | MEDIUM ROLEPLAY</p>
    <p class="codename">Уставной документ №SCP-RP-01 «ЗАСЛОН» | Участок 11 | Возрастной рейтинг: 13+</p>
  </div>

  <div class="alert alert-danger reveal">
    <strong>⛔ ВНИМАНИЕ:</strong> Данный устав обязателен к прочтению каждому сотруднику Участка. Заходя на сервер <strong>MV.Project</strong>, вы автоматически соглашаетесь с правилами. <span class="critical">Незнание правил не освобождает от ответственности.</span>
  </div>

  <h2 id="codes" class="reveal">🚨 Раздел I. Цветовые коды угроз</h2>
  <p class="reveal">Коды угроз — стандартная система оповещения Фонда. Персонал обязан знать их значение.</p>

  <div class="alert alert-info reveal">
    <strong>📢 Общие правила при ЛЮБОМ коде:</strong>
    <ul>
      <li>Персонал обязан слушаться <strong>СБ или любую МОГ</strong>.</li>
      <li>Разрешён <strong>расстрел класса D</strong> при угрозе жизни персонала.</li>
      <li><strong>Ложное объявление кода — НЕ повод для бана</strong>, это повод для интересного РП.</li>
    </ul>
  </div>

  <div class="code-grid">
    <div class="code-card code-green reveal"><h4>🟢 КОД ЗЕЛЁНЫЙ</h4><p><strong>Био-угроза / Заражение</strong></p><p>Опасность, связанная с био-угрозой, инфекцией или источником заражения.</p><p><strong>Указания:</strong> Избегайте контакта с источниками. Не покидайте Участок.</p><p><strong>МОГ:</strong> Бета-7 «Шляпные болванчики»</p></div>
    <div class="code-card code-blue reveal"><h4>🔵 КОД СИНИЙ</h4><p><strong>Побег разумного объекта</strong></p><p>Побег объекта с интеллектом ниже человеческого.</p><p><strong>Указания:</strong> Следуйте указаниям охраны.</p><p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p></div>
    <div class="code-card code-superblue reveal"><h4>🔷 КОД СУПЕРСИНИЙ</h4><p><strong>Побег разумного объекта (высокий интеллект)</strong></p><p>Побег объекта с интеллектом, равным или превышающим человеческий.</p><p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p></div>
    <div class="code-card code-yellow reveal"><h4>🟡 КОД ЖЁЛТЫЙ</h4><p><strong>Меметическая / когнитивная угроза</strong></p><p>Присутствие меметической или информационной угрозы.</p><p><strong>МОГ:</strong> Эта-10, Эта-11</p></div>
    <div class="code-card code-red reveal"><h4>🔴 КОД КРАСНЫЙ</h4><p><strong>Агрессивная сущность (АНС)</strong></p><p>Побег опасной агрессивной сущности.</p><p><strong>МОГ:</strong> Ню-7, Эта-5, Гамма-5</p></div>
    <div class="code-card code-black reveal"><h4>⚫ КОД ЧЁРНЫЙ</h4><p><strong>Нарушение содержания НЛУ</strong></p><p>Нарушение содержания Неликвидируемой Угрозы.</p><p><strong>⚠️ ВАЖНО:</strong> <span class="critical">Эвакуация ЗАПРЕЩЕНА!</span> Код чёрный может быть и на SCP-106 — покидание комплекса смертельно опасно.</p><p><strong>МОГ:</strong> Эпсилон-11, Сигма-23</p></div>
    <div class="code-card code-white reveal"><h4>⚪ КОД БЕЛЫЙ</h4><p><strong>Вторжение сил захвата</strong></p><p>Вторжение высокоорганизованных сил захвата.</p><p><strong>МОГ:</strong> Все ММОГ уровня батальона</p></div>
    <div class="code-card code-gray reveal"><h4>🌫️ КОД СЕРЫЙ</h4><p><strong>Внутренняя угроза</strong></p><p>Аналог БЕЛОГО, но угроза изнутри Участка.</p><p><strong>МОГ:</strong> Все ММОГ уровня батальона</p></div>
    <div class="code-card code-purple reveal"><h4>🟣 КОД ПУРПУРНЫЙ</h4><p><strong>Экстрамерная угроза</strong></p><p>Нарушения пространства, времени, причинности.</p><p><strong>МОГ:</strong> Дзета-9, Лямбда-5, Мю-13</p></div>
    <div class="code-card code-clean reveal"><h4>⬜ КОД ЧИСТЫЙ</h4><p><strong>НОУС</strong></p><p>Нарушение Удержания Объекта Содержания — известная сущность, но неизвестно какая именно.</p><p><strong>МОГ:</strong> Отсутствуют</p></div>
    <div class="code-card code-superclean reveal"><h4>💗 КОД СУПЕРЧИСТЫЙ</h4><p><strong>Неизвестная аномальная угроза</strong></p><p>Обозначает неизвестную аномальную угрозу.</p><p><strong>МОГ:</strong> Отсутствуют</p></div>
    <div class="code-card code-silver reveal"><h4>🥈 КОД ХЛАДНОЕ СЕРЕБРО</h4><p><strong>Фатальный сбой Фонда</strong></p><p>Событие, ведущее к краху Фонда.</p><p><strong>МОГ:</strong> Отсутствуют</p></div>
  </div>

  <hr class="divider">

  <h2 id="clearance" class="reveal">🔐 Раздел II. Уровни допуска персонала</h2>
  <div class="clearance-grid">
    <div class="clearance-card level-1 reveal"><h4>УРОВЕНЬ 1</h4><p><strong>Неважный персонал</strong></p><ul><li>Уборщики</li><li>Обслуживающий персонал</li><li>Стажёры без допуска</li></ul><p style="margin-top:10px;color:#ff6666;">Доступ: только общественные зоны. Сопровождение обязательно.</p><p><strong>Протоколы:</strong> не имеет права использовать.</p></div>
    <div class="clearance-card level-2 reveal"><h4>УРОВЕНЬ 2</h4><p><strong>Младший персонал</strong></p><ul><li>Капрал СБ</li><li>Младший НС</li><li>Инженер</li></ul><p style="margin-top:10px;color:#ff6666;">Доступ: Лёгкая зона, подсобные помещения.</p><p><strong>Протоколы:</strong> P-S-1.</p></div>
    <div class="clearance-card level-3 reveal"><h4>УРОВЕНЬ 3</h4><p><strong>Старший персонал</strong></p><ul><li>Сержант СБ</li><li>Лейтенант СБ</li><li>Старший НС</li><li>НС</li></ul><p style="margin-top:10px;color:#ff6666;">Доступ: Лёгкая и Тяжёлая зоны.</p><p><strong>Протоколы:</strong> P-L-1, P-L-2, P-L-3, P-S-1, P-S-2, P-S-3.</p></div>
    <div class="clearance-card level-4 reveal"><h4>УРОВЕНЬ 4</h4><p><strong>Командование</strong></p><ul><li>Директор Участка</li><li>Представитель КпЭ</li><li>Агент ГАРШ-O4</li><li>ГНС</li><li>ГСБ</li><li><strong>Капитан МОГ</strong></li></ul><p style="margin-top:10px;color:#ff6666;">Доступ: все зоны Участка.</p><p><strong>Протоколы:</strong> все P-L, P-S, P-B, P-I, P-E.</p></div>
    <div class="clearance-card level-5 reveal"><h4>УРОВЕНЬ 5</h4><p><strong>Совет О5</strong></p><ul><li>Совет О5</li><li>Председатель КпЭ</li><li>Инспектор КпЭ</li><li>Старший агент ГАРШ-O4</li><li>Суд-O3</li></ul><p style="margin-top:10px;color:#ff6666;">Доступ: полный доступ.</p><p><strong>Протоколы:</strong> все, включая CAP-1 — CAP-7.</p></div>
  </div>

  <hr class="divider">

  <h2 id="classes-personnel" class="reveal">👤 Раздел III. Классы персонала</h2>
  <div class="clearance-grid">
    <div class="clearance-card level-a reveal"><h4>КЛАСС A</h4><p><strong>Стратегически важный персонал</strong></p><ul><li>Члены Совета О5</li><li>Высшее руководство Фонда</li></ul><p><strong>Запрещено:</strong> Прямой доступ к аномалиям. Выход из защищённых зон.</p><p><strong>Разрешено:</strong> Работа в защищённых зонах.</p></div>
    <div class="clearance-card level-b reveal"><h4>КЛАСС B</h4><p><strong>Важный персонал</strong></p><ul><li>Руководители отделов</li><li>Старшие научные сотрудники</li><li>Ключевые инженеры</li></ul><p><strong>Запрещено:</strong> Доступ к аномалиям без карантина.</p><p><strong>Разрешено:</strong> Доступ к карантинным аномалиям.</p></div>
    <div class="clearance-card level-c reveal"><h4>КЛАСС C</h4><p><strong>Прямой доступ</strong></p><ul><li>Научные сотрудники</li><li>Охрана</li><li>Инженеры</li></ul><p><strong>Запрещено:</strong> Контакт с опасными аномалиями.</p><p><strong>Разрешено:</strong> Работа с безопасными аномалиями.</p></div>
    <div class="clearance-card level-d reveal"><h4>КЛАСС D</h4><p><strong>Расходный персонал</strong></p><ul><li>Заключённые</li><li>Испытуемые</li></ul><p><strong>Запрещено:</strong> Контакт с классами A и B. Побег.</p><p><strong>Разрешено:</strong> Участие в тестах.</p></div>
    <div class="clearance-card level-e reveal"><h4>КЛАСС E</h4><p><strong>Временное обозначение</strong></p><ul><li>Полевые агенты</li><li>Пострадавшие от аномалий</li></ul><p><strong>Запрещено:</strong> Возврат к работе до обследования.</p><p><strong>Разрешено:</strong> Карантин и наблюдение.</p></div>
  </div>

  <hr class="divider">

  <h2 id="mtf" class="reveal">🛡️ Раздел IV. Мобильные Оперативные Группы (МОГ)</h2>
  <h3 class="reveal">Основные МОГ</h3>
  <div class="table-wrap reveal">
    <table class="data-table">
      <tr><th>Отряд</th><th>Позывной</th><th>Специализация</th></tr>
      <tr><td><strong>Ню-7</strong></td><td>«Удар молота»</td><td>Подавление нарушений содержания.</td></tr>
      <tr><td><strong>Эта-10</strong></td><td>«Не вижу зла»</td><td>Меметические угрозы.</td></tr>
      <tr><td><strong>Эта-11</strong></td><td>«Дикие твари»</td><td>Звуковые аномалии.</td></tr>
      <tr><td><strong>Бета-7</strong></td><td>«Шляпные болванчики»</td><td>Био-угрозы.</td></tr>
      <tr><td><strong>Эпсилон-11</strong></td><td>«Девятихвостая лиса»</td><td>Поимка беглых SCP.</td></tr>
      <tr><td><strong>Дзета-9</strong></td><td>«Кротокрысы»</td><td>Пространственно-временные аномалии.</td></tr>
      <tr><td><strong>Лямбда-5</strong></td><td>«Белые кролики»</td><td>Экстрамерные угрозы.</td></tr>
      <tr><td><strong>Мю-13</strong></td><td>«Охотники за привидениями»</td><td>Нематериальные сущности.</td></tr>
    </table>
  </div>
  <h3 id="mtf-dop" class="reveal">Дополнительные МОГ</h3>
  <div class="table-wrap reveal">
    <table class="data-table">
      <tr><th>Отряд</th><th>Позывной</th><th>Специализация</th></tr>
      <tr><td><strong>Альфа-1</strong></td><td>«Багряная десница»</td><td>Охрана Совета О5.</td></tr>
      <tr><td><strong>Альфа-9</strong></td><td>«Последняя надежда»</td><td>Сдерживание SCP.</td></tr>
      <tr><td><strong>Гамма-5</strong></td><td>«Ложный след»</td><td>Дезинформация.</td></tr>
      <tr><td><strong>Гамма-13</strong></td><td>«Законники Азимова»</td><td>ИИ-аномалии.</td></tr>
      <tr><td><strong>Лямбда-12</strong></td><td>«Санстанция»</td><td>Паразиты.</td></tr>
      <tr><td><strong>Мю-3</strong></td><td>«Богатые Аукционеры»</td><td>Ликвидация групп.</td></tr>
      <tr><td><strong>Мю-4</strong></td><td>«Отладчики»</td><td>Неполадки систем.</td></tr>
      <tr><td><strong>Омега-1</strong></td><td>«Левая рука закона»</td><td>Внутренние разбирательства.</td></tr>
      <tr><td><strong>Сигма-66</strong></td><td>«Шестнадцать тонн»</td><td>Тяжёлое вооружение.</td></tr>
      <tr><td><strong>Тау-5</strong></td><td>«Самсара»</td><td>Религиозные аномалии.</td></tr>
      <tr><td><strong>Эпсилон-9</strong></td><td>«Пожиратели огня»</td><td>Термальные угрозы.</td></tr>
    </table>
  </div>
  <h3 id="mtf-tg" class="reveal">Тактические группы (ТГ)</h3>
  <div class="table-wrap reveal">
    <table class="data-table">
      <tr><th>Группа</th><th>Позывной</th><th>Специализация</th></tr>
      <tr><td><strong>ОБР «Курс»</strong></td><td>Тактическая группа</td><td>Сдерживание SCP, разведка.</td></tr>
      <tr><td><strong>ТГ «Птицы»</strong></td><td>Тактическая группа</td><td>Сдерживание SCP-106.</td></tr>
      <tr><td><strong>ТГ «Резонанс»</strong></td><td>Тактическая группа</td><td>Ликвидация угроз.</td></tr>
      <tr><td><strong>ТГ «Пожарники»</strong></td><td>Инженерная ТГ</td><td>Пожары, техподдержка.</td></tr>
      <tr><td><strong>Санитарная ТГ</strong></td><td>Медицинская группа</td><td>Помощь пострадавшим.</td></tr>
    </table>
  </div>

  <hr class="divider">

  <h2 id="protocols" class="reveal">📋 Раздел V. Протоколы и изоляционные коды</h2>
  <p class="reveal">Использование протоколов разрешено только персоналу с соответствующим уровнем допуска.</p>
  <h3 id="prot-p-l" class="reveal">Протоколы P-L (блокировка) — УД 3+</h3>
  <div class="table-wrap reveal"><table class="data-table"><tr><th>Протокол</th><th>Описание</th><th>УД</th></tr><tr><td><strong>P-L-1</strong></td><td>Блокировка гермо-ворот A и B.</td><td>3+</td></tr><tr><td><strong>P-L-2</strong></td><td>Блокировка всех КПП.</td><td>3+</td></tr><tr><td><strong>P-L-3</strong></td><td>Блокировка всех дверей.</td><td>3+</td></tr></table></div>
  <h3 id="prot-p-s" class="reveal">Протоколы P-S (SCP) — УД 2+</h3>
  <div class="table-wrap reveal"><table class="data-table"><tr><th>Протокол</th><th>Описание</th><th>УД</th></tr><tr><td><strong>P-S-1</strong></td><td>Отслеживание SCP-объектов.</td><td>2+</td></tr><tr><td><strong>P-S-2</strong></td><td>Отслеживание статуса SCP.</td><td>3+</td></tr><tr><td><strong>P-S-3</strong></td><td>Активация тесла-ворот.</td><td>3+</td></tr><tr><td><strong>P-S-4</strong></td><td>Сканирование комплекса.</td><td>3+</td></tr><tr><td><strong>P-S-5</strong></td><td>Полный блэкаут комплекса.</td><td>3+</td></tr></table></div>
  <h3 id="prot-p-b" class="reveal">Протоколы P-B (био-безопасность) — УД 3+</h3>
  <div class="table-wrap reveal"><table class="data-table"><tr><th>Протокол</th><th>Описание</th><th>УД</th></tr><tr><td><strong>P-B-1</strong></td><td>Запечатывание заражённых комнат.</td><td>3+</td></tr><tr><td><strong>P-B-2</strong></td><td>Запечатывание камер содержания.</td><td>3+</td></tr><tr><td><strong>P-B-3</strong></td><td>Деконтаминация ЛЗС.</td><td>3+</td></tr><tr><td><strong>P-B-4</strong></td><td>Деконтаминация ТЗС.</td><td>3+</td></tr><tr><td><strong>P-B-5</strong></td><td>Подрыв комплекса.</td><td>4+</td></tr><tr><td><strong>P-B-6</strong></td><td>Подрыв комплекса и периметра.</td><td>4+</td></tr></table></div>
  <h3 id="prot-p-i" class="reveal">Протоколы P-I (вторжение) — УД 3+</h3>
  <div class="table-wrap reveal"><table class="data-table"><tr><th>Протокол</th><th>Описание</th><th>УД</th></tr><tr><td><strong>P-I-1</strong></td><td>Уничтожение техники у комплекса.</td><td>3+</td></tr><tr><td><strong>P-I-2</strong></td><td>Блокировка мест взлома.</td><td>3+</td></tr><tr><td><strong>P-I-3</strong></td><td>Уничтожение персонала в зоне.</td><td>4+</td></tr></table></div>
  <h3 id="prot-p-e" class="reveal">Протоколы P-E (пожаротушение) — УД 3+</h3>
  <div class="table-wrap reveal"><table class="data-table"><tr><th>Протокол</th><th>Описание</th><th>УД</th></tr><tr><td><strong>P-E-1</strong></td><td>Тушение в одной комнате; нет угрозы жизни.</td><td>3+</td></tr><tr><td><strong>P-E-2</strong></td><td>Тушение в одной комнате; есть угроза.</td><td>3+</td></tr><tr><td><strong>P-E-3</strong></td><td>Тушение в одной комнате; угроза взрыва.</td><td>3+</td></tr><tr><td><strong>P-E-4</strong></td><td>Тушение в нескольких комнатах; нет угрозы.</td><td>3+</td></tr><tr><td><strong>P-E-5</strong></td><td>Тушение в нескольких комнатах; есть угроза.</td><td>3+</td></tr><tr><td><strong>P-E-6</strong></td><td>Тушение в целой зоне; большая угроза.</td><td>4+</td></tr><tr><td><strong>P-E-7</strong></td><td>Тушение в КС SCP «Безопасный».</td><td>3+</td></tr><tr><td><strong>P-E-8</strong></td><td>Тушение в КС SCP «Евклид».</td><td>3+</td></tr><tr><td><strong>P-E-9</strong></td><td>Тушение в КС SCP «Кетер».</td><td>4+</td></tr></table></div>
  <h3 id="prot-kir" class="reveal">Изоляционные коды (КИР)</h3>
  <div class="table-wrap reveal"><table class="data-table"><tr><th>Код</th><th>Значение</th></tr><tr><td><strong>Чёрный</strong></td><td>Полная изоляция комплекса. <span class="critical">Эвакуация запрещена!</span></td></tr><tr><td><strong>Серый</strong></td><td>Внутренняя угроза.</td></tr><tr><td><strong>Белый</strong></td><td>Внешнее вторжение.</td></tr><tr><td><strong>Суперсиний</strong></td><td>Побег разумного SCP (высокий интеллект).</td></tr><tr><td><strong>Синий</strong></td><td>Побег разумного SCP.</td></tr><tr><td><strong>Красный</strong></td><td>Агрессивная сущность.</td></tr><tr><td><strong>Зелёный</strong></td><td>Био-угроза.</td></tr><tr><td><strong>Пурпурный</strong></td><td>Экстрамерная угроза.</td></tr><tr><td><strong>Жёлтый</strong></td><td>Меметическая угроза.</td></tr><tr><td><strong>Чистый</strong></td><td>НОУС.</td></tr><tr><td><strong>Суперчистый</strong></td><td>Неизвестная аномальная угроза.</td></tr><tr><td><strong>Хладное серебро</strong></td><td>Фатальный сбой Фонда.</td></tr><tr><td><strong>Розовый</strong></td><td>Дополнительный код.</td></tr></table></div>

  <hr class="divider">

  <h2 id="privileges" class="reveal">⭐ Раздел VI. Правила привилегий и администрации</h2>
  <p class="reveal">Администрация сервера — это <strong>лицо проекта</strong>.</p>
  <div class="alert alert-danger reveal"><strong>⛔ ВАЖНО:</strong> Нарушение правил привилегий = понижение, ЧСА или снятие.</div>
  <div class="two-col-grid">
    <div class="priv-card reveal" id="priv-obligations"><h4>✅ Что ОБЯЗАН делать админ</h4><ul><li>Быть активным (3–4 раза в неделю).</li><li>Знать правила наизусть.</li><li>Реагировать на жалобы.</li><li>Использовать команды по назначению.</li><li>Быть вежливым.</li><li>Помогать новичкам.</li><li>Соблюдать иерархию.</li><li>Фиксировать наказания.</li></ul></div>
    <div class="priv-card reveal" id="priv-forbidden" style="border-color:rgba(255,0,0,.35);"><h4 style="color:#ff6666;">❌ Что ЗАПРЕЩЕНО админу</h4><ul><li>Оскорблять игроков или коллег.</li><li>Злоупотреблять полномочиями.</li><li>Игнорировать игроков.</li><li>Читерить или использовать софт.</li><li>Использовать команды в личных целях.</li><li>Сливать информацию из админ-чата.</li><li>Кормить читеров.</li><li>Создавать конфликты на публике.</li><li>Отсутствовать 7+ дней.</li></ul></div>
    <div class="priv-card reveal" id="priv-lies" style="border-color:rgba(255,170,0,.35);"><h4 style="color:#ffaa00;">⚠️ Наказания за враньё</h4><ul><li><strong>1-е:</strong> строгий выговор.</li><li><strong>2-е:</strong> временный ЧСА (3–7 дней).</li><li><strong>3-е:</strong> понижение или пожизненный ЧСА.</li></ul></div>
    <div class="priv-card reveal" id="priv-confidential" style="border-color:rgba(255,0,0,.35);"><h4 style="color:#ff6666;">🚫 Конфиденциальность переписок</h4><ul><li>Запрещено публиковать скриншоты админ-чата.</li><li>Запрещено пересылать личные сообщения.</li><li>Запрещено рассказывать игрокам об обсуждениях.</li><li><strong>Даже для обжалования</strong> нельзя показывать переписки.</li><li><strong>Наказание:</strong> ПОЖИЗНЕННЫЙ ЧСА.</li></ul></div>
    <div class="priv-card reveal" id="priv-others" style="border-color:rgba(144,19,254,.35);"><h4 style="color:#c07aff;">🛡️ Админство на других серверах</h4><ul><li>Запрещено быть админом на других серверах.</li><li>Конфликт интересов.</li><li><strong>Наказание:</strong> пожизненный ЧСА.</li></ul></div>
    <div class="priv-card reveal" id="priv-hierarchy" style="border-color:rgba(var(--accent-rgb),.35);"><h4>👑 Иерархия должностей</h4><ul><li><strong>Высший состав:</strong> Владелец, Со-владелец, Гл. Админ, Зам., HR, Dev.</li><li><strong>Кураторы:</strong> Ст. куратор и кураторы отделов.</li><li><strong>Ивент-отдел:</strong> Гл. ивентолог, ивентолог.</li><li><strong>Администраторы:</strong> Ст. админ, админ, мл. админ.</li><li><strong>Модераторы:</strong> Ст. модер, модер, мл. модер.</li><li><strong>Помощники:</strong> Ст. помощник, помощник, мл. помощник.</li><li><strong>Стажёры:</strong> Ст. стажёр, стажёр, кандидат, испытательный.</li><li><strong>Контент-мейкеры:</strong> Гл. КМ, ст. КМ, КМ, видео-оператор, стример, летсплейщик.</li></ul></div>
    <div class="priv-card reveal" id="priv-punish" style="border-color:rgba(245,166,35,.35);"><h4 style="color:#f5a623;">⚖️ Виды взысканий</h4><ul><li><strong>Выговор устный</strong> — мелкие нарушения.</li><li><strong>Выговор письменный</strong> — грубые или повторные.</li><li><strong>Временный ЧСА</strong> — систематические (3–30 дней).</li><li><strong>Понижение</strong> — неисполнение обязанностей.</li><li><strong>Пожизненный ЧСА</strong> — за читерство, слив, оскорбления, враньё (3+), админство на других.</li></ul></div>
    <div class="priv-card reveal" id="priv-rights" style="border-color:rgba(0,204,255,.35);"><h4 style="color:#00ccff;">📋 Права администрации</h4><ul><li>Право на ошибку, если готов её признать.</li><li>Право на защиту своей позиции.</li><li>Право обратиться к старшему или владельцу.</li><li>Право на апелляцию наказания.</li></ul></div>
  </div>

  <hr class="divider">

  <h2 id="uniform" class="reveal">👔 Раздел VII. Что можно носить и делать</h2>
  <div class="two-col-grid">
    <div class="reveal"><h3>✅ Что можно носить сотрудникам</h3><div class="table-wrap"><table class="data-table"><tr><th>Должность</th><th>Разрешено</th></tr><tr><td><strong>Уборщики</strong></td><td>Спецодежда, перчатки, фонарь, пропуск 1 УД</td></tr><tr><td><strong>Капрал СБ</strong></td><td>Форма СБ, дубинка, FSP-9, бронежилет</td></tr><tr><td><strong>Мл. НС / Инженер</strong></td><td>Халат, очки, планшет, инструменты</td></tr><tr><td><strong>Сержант / Лейтенант СБ</strong></td><td>Форма СБ, CrossVec, бронежилет, наручники</td></tr><tr><td><strong>Ст. НС / НС</strong></td><td>Халат, очки, планшет, пропуск 3 УД</td></tr><tr><td><strong>Директор / ГСБ / ГНС</strong></td><td>Официальная форма, Revolver, пропуск 4 УД</td></tr><tr><td><strong>Совет О5 / КпЭ</strong></td><td>Официальная форма, Revolver, полный допуск</td></tr><tr><td><strong>Капитан МОГ</strong></td><td>Тактическая форма, MTF E-11 SR, пропуск 4 УД</td></tr></table></div></div>
    <div class="reveal"><h3>❌ Что носить ЗАПРЕЩЕНО</h3><div class="alert alert-danger"><ul><li>Одежда, не соответствующая роли (FailRP).</li><li>Оружие, не входящее в экипировку роли.</li><li>Маски, скрывающие лицо (кроме СБ и SCP-049).</li><li>Уникальные предметы SCP без допуска.</li><li>Чужие ключ-карты.</li><li>Аксессуары, нарушающие RP.</li></ul></div></div>
  </div>

  <hr class="divider">

  <h2 id="items" class="reveal">🎒 Раздел VIII. Предметы, арест и расстрел</h2>
  <p class="reveal">Правила о том, что можно носить, что нельзя, и какие меры применяются к нарушителям.</p>
  <h3 id="items-can" class="reveal">✅ Что можно носить персоналу</h3>
  <div class="two-col-grid">
    <div class="item-card item-yes reveal"><h4>🧪 Учёные (УД 2-3)</h4><ul><li>Аптечки (Medkit)</li><li>Обезболивающие (Painkillers)</li><li>Рация</li><li>Ключ-карта строго своего УД</li><li>Фонарь, планшет, очки</li></ul></div>
    <div class="item-card item-yes reveal"><h4>🛡️ Охрана и МОГ (УД 2-4)</h4><ul><li>Штатное оружие (MTF E-11 SR, CrossVec, FSP-9, FR-MG-0, AK, Logicer)</li><li>Дубинка/шокер</li><li>Бронежилет</li><li>Рация, наручники</li><li>Аптечки и гранаты (по ситуации)</li></ul></div>
    <div class="item-card item-yes reveal"><h4>⚙️ Инженеры (УД 2)</h4><ul><li>Инструменты (Toolkit)</li><li>Оборудование для генераторов</li><li>Ключ-карта 2 УД</li><li>Рация, фонарь</li></ul></div>
    <div class="item-card item-yes reveal"><h4>🧹 Класс D и уборщики (УД 1)</h4><ul><li>Метла и ведро (только уборщики)</li><li>Фонарь</li><li>Ключ-карта 1 УД (Janitor)</li><li><strong>Больше ничего!</strong></li></ul></div>
  </div>
  <h3 id="items-cant" class="reveal">❌ Что носить ЗАПРЕЩЕНО</h3>
  <div class="two-col-grid">
    <div class="item-card item-no reveal"><h4>🚫 Общие запреты</h4><ul><li><strong>Карта выше своего уровня допуска</strong></li><li>Чужие ключ-карты</li><li>Оружие не по экипировке роли</li><li>Компоненты боеголовки</li><li>SCP-предметы без допуска</li><li>SCP-018 (мяч)</li><li>Micro H.I.D. и 3-X Particle Disruptor</li><li>Маски, скрывающие лицо</li></ul></div>
    <div class="item-card item-no reveal"><h4>🚫 Для класса D и уборщиков</h4><ul><li>Любое огнестрельное оружие</li><li>Гранаты и взрывчатка</li><li>Карты выше 1 УД</li><li>Бронежилеты МОГ</li><li>SCP-предметы</li><li>Компоненты боеголовки</li><li>SCP-500 и SCP-268</li></ul></div>
    <div class="item-card item-no reveal"><h4>🚫 Для учёных</h4><ul><li>Тяжёлое оружие (MTF E-11 SR, Logicer, FR-MG-0, AK)</li><li>Гранаты (кроме успокоительных)</li><li>Карты 5 УД</li><li>Бронежилеты МОГ</li><li>Компоненты боеголовки</li><li><strong>SCP-500</strong></li><li>SCP-268</li></ul></div>
    <div class="item-card item-no reveal"><h4>🚫 Для охраны</h4><ul><li>SCP-предметы без допуска</li><li>Компоненты боеголовки</li><li>Карты 5 УД</li><li>Оружие не по экипировке СБ</li><li>Предметы, украденные у МОГ</li></ul></div>
  </div>

  <h3 id="items-arrest" class="reveal">🚨 Арест персонала</h3>
  <p class="reveal">Арест — временное помещение сотрудника под стражу с последующим <strong>выводом на эвакуацию</strong>.</p>
  <div class="two-col-grid">
    <div class="item-card item-arrest reveal"><h4>⚠️ Арест + вывод на эвакуацию</h4><p style="color:#ffaa00;font-size:.9em;">При обнаружении запрещённых предметов:</p><ul><li>Обнаружено <strong>запрещённое оружие</strong>.</li><li>Обнаружена <strong>карта выше уровня допуска</strong>.</li><li>Обнаружены <strong>компоненты боеголовки</strong>.</li><li>Обнаружены <strong>SCP-предметы</strong> без допуска.</li><li>Обнаружены <strong>чужие ключ-карты</strong>.</li><li>Обнаружены <strong>запрещённые маски</strong>.</li></ul><p style="margin-top:10px;color:#88ffbb;"><strong>Действия:</strong></p><ol><li>Задержать сотрудника.</li><li>Изъять запрещённые предметы.</li><li>Провести допрос с объяснением причин.</li><li><strong>Вывести на эвакуацию</strong>.</li></ol></div>
    <div class="item-card item-arrest reveal"><h4>🚨 Серьёзные нарушения</h4><ul><li>Проникновение в запрещённые зоны.</li><li>Нападение на сотрудника СБ.</li><li>Помощь Классу D в побеге.</li><li>Саботаж оборудования.</li><li>Попытка побега из Участка.</li><li>Сотрудничество с ПХ.</li></ul><p style="margin-top:10px;color:#88ffbb;"><strong>Действия:</strong></p><ol><li>Задержать сотрудника.</li><li>Провести допрос под стражей.</li><li>Вывести на эвакуацию.</li><li>При сопротивлении — разрешено применение силы.</li></ol></div>
  </div>

  <h3 id="items-execute" class="reveal">💀 Расстрел класса D</h3>
  <div class="two-col-grid">
    <div class="item-card item-execute reveal"><h4>🛑 Расстрел на месте</h4><p style="color:#ff6666;">Класс D подлежит немедленному расстрелу при:</p><ul><li>Нападении на охрану или персонал.</li><li>Завладении огнестрельным оружием.</li><li>Попытке побега за пределы Участка.</li><li>Попытке убийства учёного.</li><li>Организации бунта.</li><li>Умышленном саботаже оборудования.</li><li>Любой угрозе жизни персонала.</li></ul></div>
    <div class="item-card item-execute reveal"><h4>⚠️ Важно для СБ и МОГ</h4><ul><li>Расстрел разрешён <strong>при ЛЮБОМ коде</strong>.</li><li>Расстрел производится <strong>только при явной угрозе</strong>.</li><li>При отсутствии угрозы — сначала предупреждение.</li><li>Расстрел без причины = нарушение правил.</li><li>Расстрел мирного класса D запрещён.</li></ul></div>
  </div>

  <div class="alert alert-info reveal"><strong>💡 Права задержанного (персонал):</strong><ul><li>Узнать причину ареста.</li><li>Дать объяснение в своё оправдание.</li><li>Подать жалобу на действия СБ администрации.</li><li>Быть выведенным на эвакуацию (а не убитым).</li><li>На адвоката от учёных (для класса B и выше).</li></ul></div>

  <hr class="divider">

  <h2 id="general" class="reveal">📜 Раздел IX. Общие правила</h2>
  <div class="two-col-grid">
    <div class="section reveal" style="margin:0;"><h3>9.1. Принципы сервера</h3><p>Сервер <strong>MV.Project</strong> — <span class="highlight">Medium RP</span> проект.</p><ul><li>Уважение — основа сервера.</li><li>Запрещена дискриминация.</li><li>Запрещены угрозы в реальной жизни.</li><li>Запрещена пропаганда терроризма.</li><li>Запрещены атаки на сервер.</li></ul></div>
    <div class="section reveal" style="margin:0;"><h3>9.2. Возраст и аккаунты</h3><ul><li>Минимальный возраст — <span class="highlight">13 лет</span>.</li><li>Обман по возрасту = перманентный бан.</li><li>Запрещено несколько аккаунтов.</li><li>Запрещена передача аккаунта.</li><li>Обход бана = перманентный бан + IP-бан.</li></ul></div>
  </div>

  <hr class="divider">

  <h2 id="rp" class="reveal">🎭 Раздел X. RP-правила</h2>
  <div class="section reveal">
    <h3>10.1. Что такое RP?</h3>
    <p><strong>RP (Roleplay)</strong> — отыгрыш роли персонажа. Medium RP = играть роль без фанатизма.</p>
    <div class="two-col-grid">
      <div>
        <h4>❌ No RDM</h4><ul><li>Запрещено убивать без RP-причины.</li><li>Наказание: бан 1–30 дней.</li></ul>
        <h4>❌ No Teamkill</h4><ul><li>Запрещено убивать союзников.</li><li>Наказание: бан от 3 дней.</li></ul>
        <h4>❌ No Metagaming</h4><ul><li>Запрещено использовать внеигровую инфу.</li><li>Наказание: бан от 3 дней.</li></ul>
      </div>
      <div>
        <h4>❌ No Powergaming</h4><ul><li>Запрещены действия, невозможные в реальности.</li><li>Наказание: бан от 3 дней.</li></ul>
        <h4>❌ No Banhop</h4><ul><li>Запрещён баннихоп при побеге.</li><li>Наказание: бан от 1 дня.</li></ul>
        <h4>❌ No FailRP</h4><ul><li>Запрещено нарушать логику персонажа.</li><li>Наказание: предупреждение или бан.</li></ul>
      </div>
    </div>
  </div>

  <hr class="divider">

  <h2 id="classes" class="reveal">👥 Раздел XI. Правила игровых классов</h2>
  <div class="two-col-grid">
    <div class="acc reveal"><button class="acc-head" type="button"><span>🟠</span> Класс D <span class="acc-arrow">▶</span></button><div class="acc-body"><div class="acc-inner"><ul><li>Обязаны слушаться охрану.</li><li>Запрещено бунтовать без RP-причины.</li><li>Побег разрешён, но без Banhop.</li><li>Запрещено мешать тестам.</li><li>При КОДЕ КРАСНОМ+ разрешено всё для выживания.</li></ul></div></div></div>
    <div class="acc reveal"><button class="acc-head" type="button"><span>🔵</span> Учёные <span class="acc-arrow">▶</span></button><div class="acc-body"><div class="acc-inner"><ul><li>Обязаны проводить тесты SCP.</li><li>Запрещено покидать Участок.</li><li>Обязаны сотрудничать с МОГ.</li><li>Запрещено давать Класс D предметы.</li></ul></div></div></div>
    <div class="acc reveal"><button class="acc-head" type="button"><span>🟢</span> Охрана Фонда <span class="acc-arrow">▶</span></button><div class="acc-body"><div class="acc-inner"><ul><li>Обязаны следить за порядком.</li><li>Запрещено убивать Класс D без причины.</li><li>Обязаны сопровождать учёных.</li><li>При КОДЕ 3+ — защищать Участок.</li></ul></div></div></div>
    <div class="acc reveal"><button class="acc-head" type="button"><span>🔴</span> МОГ (NTF) <span class="acc-arrow">▶</span></button><div class="acc-body"><div class="acc-inner"><ul><li>Действуют по протоколу.</li><li>Запрещено убивать учёных и охрану.</li><li>Обязаны защищать Участок.</li><li>При КОДЕ 4 — вернуть SCP в камеры.</li></ul></div></div></div>
    <div class="acc reveal"><button class="acc-head" type="button"><span>⚫</span> ПХ (Chaos Insurgency) <span class="acc-arrow">▶</span></button><div class="acc-body"><div class="acc-inner"><ul><li>Цель — освобождение SCP.</li><li>Запрещён RDM.</li><li>Запрещено убивать своих.</li><li>Обязаны подчиняться командиру.</li></ul></div></div></div>
    <div class="acc reveal"><button class="acc-head" type="button"><span>🟣</span> SCP-объекты <span class="acc-arrow">▶</span></button><div class="acc-body"><div class="acc-inner"><ul><li>Обязаны отыгрывать свою роль.</li><li>Запрещено фармить убийства.</li><li>SCP-049 обязан лечить.</li><li>Запрещено кемперить.</li></ul></div></div></div>
  </div>

  <hr class="divider">

  <h2 id="scp" class="reveal">🧬 Раздел XII. Правила SCP-объектов</h2>
  <p class="reveal">Подробная информация о каждом SCP: здоровье, разумность, способности, что можно и что нельзя.</p>
  <div class="two-col-grid">
    <div class="scp-card reveal" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>🧱 SCP-173 — Статуя</h4><div class="hp-badge">❤️ 10 000 HP</div><p><strong>Разумность:</strong> ❌ Нет (автомат, не мыслит)</p><ul><li><strong>Скачок</strong> — телепорт до 8 м при зрительном контакте. Убивает ближайшего человека.</li><li><strong>Лужа грязи</strong> — замедляет людей (F).</li><li>Сопротивление пулям (кроме Micro H.I.D.).</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> двигаться при отсутствии зрительного контакта, оставлять лужи.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> телепортироваться при 3+ наблюдателях, убивать без RP-причины.</p><p><strong>Наказание:</strong> бан 7-30 дней.</p></div>
    <div class="scp-card reveal" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>🩺 SCP-049 — Чумной Доктор</h4><div class="hp-badge">❤️ 5 000 HP</div><p><strong>Разумность:</strong> ✅ Да (имеет интеллект, общается)</p><ul><li><strong>Сердечный приступ</strong> — атака наносит продолжительный урон.</li><li><strong>Воскрешение</strong> — поднимает мёртвых как SCP-049-2 (зомби).</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> лечить, воскрешать зомби по RP-причине.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> убивать всех подряд, воскрешать без RP-причины.</p><p><strong>Наказание:</strong> бан 3-7 дней.</p></div>
    <div class="scp-card reveal" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>👴 SCP-106 — Старик</h4><div class="hp-badge">❤️ 7 000 HP</div><p><strong>Разумность:</strong> ✅ Да (имеет интеллект)</p><ul><li><strong>Захват</strong> — отправляет человека в карманное измерение.</li><li><strong>Погружение</strong> — скрывается в полу (Shift).</li><li>Сопротивление пулям, слаб к другим источникам урона.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> захватывать людей по RP-причине, скрываться.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> отправлять в карманное измерение без RP-причины.</p><p><strong>Наказание:</strong> бан 3-7 дней.</p></div>
    <div class="scp-card reveal" style="border-color:rgba(255,170,0,.35);border-top:3px solid #ffaa00;"><h4>😢 SCP-096 — Застенчивый</h4><div class="evacuated-badge">🚨 ЭВАКУИРОВАН ИЗ УЧАСТКА 11</div><p style="color:#ffcc66;"><strong>Статус:</strong> SCP-096 был <strong>эвакуирован из Участка 11</strong> и переведён в другой объект Фонда. На данном Участке не содержится и не появляется.</p><p style="color:#ffcc66;"><strong>Причина:</strong> Угроза признана слишком высокой для содержания на Участке 11. Все правила и механики, связанные с SCP-096, <strong>временно отключены</strong>.</p><p style="color:#ff8888;"><strong>Внимание:</strong> Если вы заметили SCP-096 на территории Участка — немедленно сообщите администрации. Это может быть баг или ивент.</p></div>
    <div class="scp-card reveal" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>👄 SCP-939 — Многоголосый</h4><div class="hp-badge">❤️ 7 000 HP</div><p><strong>Разумность:</strong> ⚠️ Полуразумный (умеет охотиться, но не мыслит)</p><p><strong>Особенности:</strong></p><ul><li>Умеет <strong>охотиться</strong> на людей по звуку.</li><li><strong>Не умеет думать</strong> — действует на инстинктах.</li><li>Может <strong>только произносить звуки</strong> (имитирует голоса), но не понимает их смысла.</li><li>Не способен к RP-диалогу — издаёт звуки для приманки.</li></ul><p><strong>Способности:</strong></p><ul><li><strong>Мимикрия</strong> — имитирует голоса людей.</li><li><strong>Укус</strong> — 65 урона + амнезия (нельзя перезарядиться).</li><li>Чувствительность к звуку (видит сквозь стены).</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> использовать звук для охоты, имитировать голоса.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> игнорировать правила, кемперить.</p><p><strong>Наказание:</strong> предупреждение / бан 1 день.</p></div>
    <div class="scp-card reveal" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>💀 SCP-3114 — Скелет</h4><div class="hp-badge">❤️ 6 000 HP</div><p><strong>Разумность:</strong> ✅ Да (маскируется под человека)</p><ul><li><strong>Скелеты в шкафу</strong> — снимает кожу с трупов, маскируется.</li><li><strong>Удушение</strong> — захват человека.</li><li>Может использовать предметы в облике.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> маскироваться, общаться с людьми в облике.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> быстро раскрываться, убивать без RP-причины.</p><p><strong>Наказание:</strong> бан 1-3 дня.</p></div>
    <div class="scp-card reveal" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>💻 SCP-079 — Старый ИИ</h4><div class="hp-badge">❤️ 0 HP (уязвим к перегрузке)</div><p><strong>Разумность:</strong> ✅ Да (искусственный интеллект)</p><ul><li>Управление дверями, лифтами, тесла-воротами.</li><li>Громкоговоритель, блокировка дверей.</li><li>Видит людей с SCP-268.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> помогать другим SCP, управлять системами.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> игнорировать просьбы других SCP.</p><p><strong>Наказание:</strong> предупреждение / бан 1 день.</p></div>
    <div class="scp-card reveal" id="scp953" style="border-color:rgba(var(--accent-rgb),.35);border-top:3px solid var(--accent);"><h4>🦊 SCP-953 — Полиморфная рептилия</h4><div class="hp-badge">❤️ 1 600 HP</div><p><strong>Разумность:</strong> ✅ Да (лис-оборотень)</p><ul><li>Принимает облик человека.</li><li>Невидимость в облике.</li><li>Атаки в ближнем бою.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> использовать облик для RP.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> использовать облик для RDM, заманивать в ловушки.</p><p><strong>Наказание:</strong> бан 7-14 дней.</p></div>
  </div>

  <hr class="divider">

  <h2 id="scp914" class="reveal">⚙️ Раздел XIII. Правила SCP-914</h2>
  <div class="two-col-grid">
    <div class="section reveal" style="margin:0;"><h3>Правила использования</h3><ul><li>Запрещено использование 914 без RP-причины.</li><li>Запрещено превращение в SCP-049-2 без RP-причины.</li><li>Запрещено использование 914 для обхода правил.</li><li>Обязательно соблюдать очередь.</li><li>Запрещено закидывание людей на смертельные режимы.</li></ul></div>
    <div class="reveal"><h3>Режимы 914</h3><div class="table-wrap"><table class="data-table"><tr><th>Режим</th><th>Эффект</th><th>ОК?</th></tr><tr><td><strong>Rough</strong></td><td>Ломает предметы</td><td>Да</td></tr><tr><td><strong>Coarse</strong></td><td>Может ухудшить</td><td>Да</td></tr><tr><td><strong>1:1</strong></td><td>Обмен</td><td>Да</td></tr><tr><td><strong>Fine</strong></td><td>Улучшение</td><td>Да</td></tr><tr><td><strong>Very Fine</strong></td><td>SCP-049-2</td><td>Только по RP</td></tr></table></div></div>
  </div>

  <hr class="divider">

  <h2 id="intercom" class="reveal">📢 Раздел XIV. Правила интеркома и чата</h2>
  <div class="alert alert-info reveal"><strong>📢 Формат сообщения в интеркоме:</strong><p>«[Имя/Позывной], [Уровень допуска], [Класс персонала], [Что требуется]».</p><ul><li><strong>Пример 1:</strong> «Говорит СБ-Капрал Иванов, 2 УД, класс C. Требуется подкрепление в ЛЗС».</li><li><strong>Пример 2:</strong> «Говорит НС Петров, 3 УД, класс B. Побег SCP-173, КОД СИНИЙ».</li><li><strong>Пример 3:</strong> «Говорит Капитан МОГ, 4 УД, класс B. Объявляю КОД КРАСНЫЙ».</li></ul></div>
  <div class="two-col-grid">
    <div class="reveal"><h3>Запрещено в интеркоме</h3><div class="alert alert-danger"><ul><li>Спам и троллинг.</li><li>Музыка без RP-причины.</li><li>Крики, оскорбления.</li><li>Личные разговоры.</li><li>Перебивание говорящего.</li><li>Ложные коды.</li></ul></div></div>
    <div class="reveal"><h3>Наказания за интерком</h3><div class="table-wrap"><table class="data-table"><tr><th>Нарушение</th><th>1-е</th><th>2-е</th><th>3-е</th></tr><tr><td>Спам</td><td>Мут 1 ч</td><td>Мут 6 ч</td><td>Бан 1 день</td></tr><tr><td>Музыка</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr><tr><td>Ложный код</td><td colspan="3">Повод для РП (НЕ бан)</td></tr><tr><td>Оскорбления</td><td>Мут 6 ч</td><td>Бан 1 день</td><td>Бан 7 дней</td></tr></table></div></div>
  </div>
  <h3 id="chat" class="reveal">Правила чата</h3>
  <div class="two-col-grid">
    <div class="section reveal" style="margin:0;"><h4>Текстовый чат</h4><ul><li>Запрещён спам (более 3 сообщений).</li><li>Запрещён флуд.</li><li>Запрещены оскорбления.</li><li>Запрещён Caps Lock.</li><li>Запрещена реклама серверов.</li><li>Запрещена политика и религия.</li></ul></div>
    <div class="section reveal" style="margin:0;"><h4>Голосовой чат</h4><ul><li>Запрещены громкие звуки.</li><li>Запрещён Soundpad.</li><li>Запрещён спам.</li><li>Запрещено перебивать.</li><li>Рация — только для RP.</li></ul></div>
  </div>

  <hr class="divider">

  <h2 id="bans" class="reveal">⏱️ Раздел XV. Сроки наказаний</h2>
  <div class="table-wrap reveal"><table class="data-table">
    <tr><th>Нарушение</th><th>1-е</th><th>2-е</th><th>3-е</th></tr>
    <tr><td>Спам в чате</td><td>Мут 30 мин</td><td>Мут 2 ч</td><td>Мут 12 ч</td></tr>
    <tr><td>Оскорбления</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
    <tr><td>Громкий микрофон</td><td>Мут 1 ч</td><td>Мут 6 ч</td><td>Мут 24 ч</td></tr>
    <tr><td>Soundpad</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
    <tr><td>No RDM (1-2)</td><td>Бан 1 день</td><td>Бан 3 дня</td><td>Бан 7 дней</td></tr>
    <tr><td>No RDM (3+)</td><td>Бан 7 дней</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
    <tr><td>Teamkill (случайный)</td><td>Предупреждение</td><td>Бан 1 день</td><td>Бан 3 дня</td></tr>
    <tr><td>Teamkill (намеренный)</td><td>Бан 3 дня</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
    <tr><td>Meta / Powergaming</td><td>Бан 3 дня</td><td>Бан 7 дней</td><td>Бан 14 дней</td></tr>
    <tr><td>FailRP</td><td>Предупреждение</td><td>Бан 1 день</td><td>Бан 3 дня</td></tr>
    <tr><td>Banhop</td><td>Бан 1 день</td><td>Бан 3 дня</td><td>Бан 7 дней</td></tr>
    <tr><td>Телепорт к 173 (3+)</td><td>Бан 7 дней</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
    <tr><td>914 без RP</td><td>Бан 3 дня</td><td>Бан 7 дней</td><td>Бан 14 дней</td></tr>
    <tr><td>Использование багов</td><td>Бан 30 дней</td><td>Бан 90 дней</td><td>Перманентный бан</td></tr>
    <tr><td>Читы / софт</td><td colspan="3">Перманентный бан (без апелляции)</td></tr>
    <tr><td>Реклама серверов</td><td colspan="3">Перманентный бан</td></tr>
    <tr><td>Угрозы / травля</td><td colspan="3">Перманентный бан</td></tr>
    <tr><td>Обход бана</td><td colspan="3">Перманентный бан + IP-бан</td></tr>
    <tr><td>Подкуп администрации</td><td colspan="3">Перманентный бан</td></tr>
    <tr><td>Ложное объявление кода</td><td colspan="3">НЕ бан (повод для РП)</td></tr>
    <tr><td>Неуважение к админам</td><td>Мут 1 ч</td><td>Мут 12 ч</td><td>Бан 3 дня</td></tr>
  </table></div>
  <div class="alert alert-warning reveal"><strong>⚠️ Примечание:</strong> Рецидивы = удвоение срока.</div>

  <hr class="divider">

  <h2 id="appeal" class="reveal">📩 Раздел XVI. Процедура апелляции</h2>
  <div class="two-col-grid">
    <div class="section reveal" style="margin:0;"><h3>Как подать апелляцию</h3><ol><li>Зайди на Discord-сервер.</li><li>Перейди в канал <strong>#апелляции</strong>.</li><li>Создай тикет по шаблону.</li><li>Укажи SteamID, причину бана и объяснение.</li></ol><h3>Сроки рассмотрения</h3><ul><li>Обычная апелляция — до 24 часов.</li><li>Сложная — до 72 часов.</li><li>Перманентный бан — до 7 дней.</li></ul><h3>Связь с администрацией</h3><p>Вся связь с администрацией осуществляется <strong>только через Discord-сервер</strong> проекта.</p><p style="color:#ffcc66;">Не пишите в личные сообщения — там ваши обращения могут быть проигнорированы.</p></div>
    <div class="reveal"><h3>Правила апелляции</h3><div class="alert alert-danger"><ul><li>Запрещено оскорблять администрацию.</li><li>Запрещено дублировать апелляции.</li><li>Запрещено подавать с другого аккаунта.</li><li>Решение окончательное.</li><li>Без доказательств — последняя очередь.</li></ul></div><h3>Шаблон апелляции</h3><div class="section" style="margin:0;padding:18px;"><p><strong>SteamID:</strong> [ваш ID]</p><p><strong>Причина бана:</strong> [причина]</p><p><strong>Кто забанил:</strong> [ник]</p><p><strong>Объяснение:</strong> [почему несправедлив]</p><p><strong>Доказательства:</strong> [ссылка]</p></div></div>
  </div>

  <hr class="divider">

  <div class="alert alert-info reveal"><strong>💡 Помни:</strong> Соблюдение правил — залог комфортной игры для всех.</div>

  <div class="center reveal">
    <a href="https://discord.gg/ZCGAhTH6ep" class="discord">💬 ВСТУПИТЬ В DISCORD</a>
    <a href="https://t.me/mvprojectru" class="telegram">📢 TELEGRAM-КАНАЛ</a>
    <a href="https://www.youtube.com/@mebnes" class="youtube">▶ YOUTUBE-КАНАЛ</a>
  </div>

  <div class="footer">
    <p>© 2026 MV.PROJECT | SCP FOUNDATION | MEDIUM ROLEPLAY</p>
    <p>Документ №SCP-RP-01 «ЗАСЛОН» | Версия 3.3 | Обновлено: сентябрь 2026</p>
    <p style="margin-top:15px;color:var(--text-dim);opacity:.5;">CLASSIFIED — LEVEL 5 CLEARANCE REQUIRED</p>
  </div>

</main>

<button class="to-top" id="toTop" aria-label="Наверх">↑</button>

<script>
function toggleSection(el){
  el.classList.toggle('open');
  const sub=el.nextElementSibling;
  if(sub)sub.classList.toggle('open');
}
window.toggleSection=toggleSection;

const html=document.documentElement;
const state={accent:'green',theme:'dark'};
const STORAGE_KEY='mvp-settings';

const COLORS=[
  {id:'green',hex:'#00ff88'},{id:'cyan',hex:'#00ccff'},{id:'blue',hex:'#4a90d9'},
  {id:'purple',hex:'#b366ff'},{id:'magenta',hex:'#ff44dd'},{id:'pink',hex:'#ff69b4'},
  {id:'red',hex:'#ff4444'},{id:'orange',hex:'#ff8800'},{id:'amber',hex:'#ffaa00'},
  {id:'yellow',hex:'#ffdd00'},{id:'lime',hex:'#aaff00'},{id:'white',hex:'#ffffff'}
];

const colorGrid=document.getElementById('colorGrid');
COLORS.forEach(c=>{
  const b=document.createElement('button');
  b.className='color-swatch';
  b.type='button';
  b.dataset.accent=c.id;
  b.style.background=c.hex;
  b.title=c.id.toUpperCase();
  b.setAttribute('aria-label','Цвет: '+c.id);
  b.addEventListener('click',()=>setAccent(c.id));
  colorGrid.appendChild(b);
});

const themeBtns=document.querySelectorAll('.theme-btn');

function setAccent(id){
  state.accent=id;
  html.dataset.accent=id;
  document.querySelectorAll('.color-swatch').forEach(s=>s.classList.toggle('active',s.dataset.accent===id));
  saveLocal();
}
function setTheme(id){
  state.theme=id;
  html.dataset.theme=id;
  themeBtns.forEach(b=>b.classList.toggle('active',b.dataset.theme===id));
  saveLocal();
}
themeBtns.forEach(b=>b.addEventListener('click',()=>setTheme(b.dataset.theme)));

const settingsWrap = document.getElementById('settingsWrap');
const settingsToggle = document.getElementById('settingsToggle');
const settingsPanel = document.getElementById('settingsPanel');
const settingsReset = document.getElementById('settingsReset');

settingsToggle.addEventListener('click', (e) => {
  e.preventDefault();
  e.stopPropagation();
  const isOpen = settingsPanel.classList.contains('show');
  if (isOpen) {
    settingsPanel.classList.remove('show');
    settingsToggle.classList.remove('active');
  } else {
    settingsPanel.classList.add('show');
    settingsToggle.classList.add('active');
  }
});

settingsPanel.addEventListener('click', (e) => {
  e.stopPropagation();
});

document.addEventListener('click', (e) => {
  if (!settingsWrap.contains(e.target)) {
    settingsPanel.classList.remove('show');
    settingsToggle.classList.remove('active');
  }
});

settingsReset.addEventListener('click', () => {
  setAccent('green');
  setTheme('dark');
});

function saveLocal(){
  try{localStorage.setItem(STORAGE_KEY,JSON.stringify({accent:state.accent,theme:state.theme}));}catch(e){}
}
function loadLocal(){
  try{
    const raw=localStorage.getItem(STORAGE_KEY);
    if(!raw)return;
    const d=JSON.parse(raw);
    if(d.accent){state.accent=d.accent;html.dataset.accent=d.accent;}
    if(d.theme){state.theme=d.theme;html.dataset.theme=d.theme;}
  }catch(e){}
}
loadLocal();

document.querySelectorAll('.color-swatch').forEach(s=>s.classList.toggle('active',s.dataset.accent===state.accent));
themeBtns.forEach(b=>b.classList.toggle('active',b.dataset.theme===state.theme));

const navLinks=document.querySelectorAll('.nav-sub a');
const sections=document.querySelectorAll('h2[id], h3[id]');
function updateActiveLink(){
  let current='';
  sections.forEach(sec=>{if(window.scrollY>=sec.offsetTop-150)current=sec.getAttribute('id');});
  navLinks.forEach(l=>l.classList.toggle('active',l.getAttribute('href')==='#'+current));
}

const progressBar=document.getElementById('scrollProgress');
const toTop=document.getElementById('toTop');
function onScroll(){
  const doc=document.documentElement;
  const sc=doc.scrollTop;
  const max=doc.scrollHeight-doc.clientHeight;
  progressBar.style.width=(max>0?sc/max*100:0)+'%';
  toTop.classList.toggle('show',sc>400);
  updateActiveLink();
}
let ticking=false;
window.addEventListener('scroll',()=>{
  if(!ticking){requestAnimationFrame(()=>{onScroll();ticking=false;});ticking=true;}
},{passive:true});
toTop.addEventListener('click',()=>window.scrollTo({top:0,behavior:'smooth'}));

(function(){
  const items=document.querySelectorAll('.reveal');
  if(!('IntersectionObserver' in window)){items.forEach(i=>i.classList.add('in'));return;}
  const obs=new IntersectionObserver(entries=>{
    entries.forEach(en=>{
      if(!en.isIntersecting)return;
      en.target.classList.add('in');
      obs.unobserve(en.target);
    });
  },{threshold:0.1,rootMargin:'0px 0px -60px 0px'});
  items.forEach(i=>obs.observe(i));
})();

document.querySelectorAll('.acc-head').forEach(h=>h.addEventListener('click',()=>h.parentElement.classList.toggle('open')));

(function(){
  const ov=document.getElementById('watermark-overlay');
  const cols=5,rows=9,txt='MV.PROJECT';
  for(let i=0;i<rows;i++)for(let j=0;j<cols;j++){
    const d=document.createElement('div');
    d.className='wm';d.textContent=txt;
    const off=(i%2===0)?0:10;
    d.style.left=(5+j*20+off)+'%';
    d.style.top=(6+i*11)+'%';
    ov.appendChild(d);
  }
})();

(function(){
  const b=document.getElementById('layer-back'),m=document.getElementById('layer-middle');
  const bt='MV.PROJECT  '.repeat(4);
  const mt='SCP FOUNDATION  '.repeat(3);
  let bh='',mh='';
  for(let i=0;i<80;i++){bh+='<div class="parallax-line">'+bt+'</div>';mh+='<div class="parallax-line">'+mt+'</div>';}
  b.innerHTML=bh;m.innerHTML=mh;
  let cb=0,cm=0;
  (function loop(){
    const sc=window.scrollY;
    cb+=(sc*.12-cb)*.07;
    cm+=(sc*-.08-cm)*.07;
    b.style.transform='translateY('+(-cb)+'px)';
    m.style.transform='translateY('+(-cm)+'px)';
    requestAnimationFrame(loop);
  })();
})();

(function(){
  const box=document.getElementById('searchBox');
  const input=document.getElementById('searchInput');
  const res=document.getElementById('searchResults');
  const clr=document.getElementById('searchClear');
  const idx=[];
  document.querySelectorAll('h2[id], h3[id], h4').forEach(el=>{
    const raw=el.textContent.trim().replace(/\s+/g,' ');
    if(raw.length<2)return;
    idx.push({el,raw,low:raw.toLowerCase()});
  });
  const esc=s=>s.replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
  function render(q){
    q=q.toLowerCase().trim();
    res.innerHTML='';
    if(q.length<2){res.classList.remove('show');return;}
    const m=idx.filter(x=>x.low.includes(q)).slice(0,30);
    if(!m.length){
      res.innerHTML='<div style="padding:22px;text-align:center;color:var(--text-dim);font-size:.82em;">Ничего не найдено</div>';
      res.classList.add('show');return;
    }
    m.forEach(it=>{
      const d=document.createElement('div');
      d.className='search-item';
      const i=it.raw.toLowerCase().indexOf(q);
      const hi=esc(it.raw.slice(0,i))+'<mark>'+esc(it.raw.slice(i,i+q.length))+'</mark>'+esc(it.raw.slice(i+q.length));
      d.innerHTML='<span class="search-tag">'+(it.el.tagName==='H2'?'Раздел':'Подраздел')+'</span>'+hi;
      d.addEventListener('click',()=>{
        it.el.scrollIntoView({behavior:'smooth',block:'start'});
        res.classList.remove('show');input.blur();
      });
      res.appendChild(d);
    });
    res.classList.add('show');
  }
  input.addEventListener('input',()=>{
    box.classList.toggle('has-value',input.value.length>0);
    render(input.value);
  });
  clr.addEventListener('click',()=>{
    input.value='';box.classList.remove('has-value');
    res.classList.remove('show');input.focus();
  });
  document.addEventListener('click',e=>{if(!box.contains(e.target))res.classList.remove('show');});
})();

onScroll();
</script>

</body>
</html>
