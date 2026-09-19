<!DOCTYPE html>
<html lang="ru" data-theme="dark" data-accent="green" data-font="mono" data-bgfx="default">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MV.Project | Устав Фонда SCP</title>
<style>
:root{--accent:#00ff88;--accent-dim:#00cc66;--accent-deep:#009944;--accent-rgb:0,255,136;--green:var(--accent);--green-dim:var(--accent-dim);--green-deep:var(--accent-deep);--bg:#050505;--panel:#0d0d0d;--panel-2:#0f0f0f;--border:#1a1a1a;--text:#b8b8b8;--ease:cubic-bezier(.22,.68,.32,1);--grid-gap:14px;--font-stack:'Consolas','Courier New',monospace;}
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
html[data-theme="light"]{--bg:#f4f4f0;--panel:#fff;--panel-2:#fafafa;--border:#e0e0e0;--text:#333;}
html[data-font="sans"]{--font-stack:'Segoe UI',system-ui,sans-serif;}
html[data-font="serif"]{--font-stack:Georgia,'Times New Roman',serif;}
html[data-font="cyber"]{--font-stack:'Impact','Arial Black',sans-serif;}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
html,body{width:100%;min-height:100%;}
body{font-family:var(--font-stack);background:var(--bg);color:var(--text);line-height:1.9;overflow-x:hidden;transition:background-color .4s var(--ease),color .4s var(--ease);}
::selection{background:rgba(var(--accent-rgb),.3);color:#fff;}
::-webkit-scrollbar{width:10px;height:10px;}
::-webkit-scrollbar-track{background:var(--bg);}
::-webkit-scrollbar-thumb{background:linear-gradient(180deg,var(--accent),var(--accent-deep));border-radius:5px;border:2px solid var(--bg);}
body::before{content:'';position:fixed;inset:0;z-index:0;pointer-events:none;opacity:0;transition:opacity .6s;}
html[data-bgfx="grid"] body::before{opacity:.35;background-image:linear-gradient(rgba(var(--accent-rgb),.06) 1px,transparent 1px),linear-gradient(90deg,rgba(var(--accent-rgb),.06) 1px,transparent 1px);background-size:40px 40px;}
html[data-bgfx="noise"] body::before{opacity:.5;background-image:url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='120' height='120'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2'/></filter><rect width='100%25' height='100%25' filter='url(%23n)' opacity='0.35'/></svg>");}
html[data-bgfx="gradient"] body::before{opacity:.9;background:radial-gradient(circle at 20% 20%,rgba(var(--accent-rgb),.12),transparent 55%),radial-gradient(circle at 80% 70%,rgba(var(--accent-rgb),.09),transparent 55%);}
html[data-bgfx="space"] body::before{opacity:.7;background:radial-gradient(1px 1px at 20% 30%,#fff,transparent),radial-gradient(1px 1px at 70% 60%,#fff,transparent),radial-gradient(1.5px 1.5px at 40% 80%,var(--accent),transparent);}

/* ВИДИМАЯ КНОПКА АДМИНКИ */
.admin-open-btn{position:fixed;top:20px;right:380px;width:44px;height:44px;border-radius:50%;background:rgba(8,8,8,.92);border:2px solid var(--accent);color:var(--accent);font-size:1.2em;cursor:pointer;display:flex;align-items:center;justify-content:center;z-index:1350;backdrop-filter:blur(10px);box-shadow:0 0 20px rgba(var(--accent-rgb),.25);transition:transform .3s var(--ease),box-shadow .3s var(--ease),background .4s;padding:0;}
html[data-theme="light"] .admin-open-btn{background:rgba(255,255,255,.95);}
.admin-open-btn:hover{transform:rotate(15deg) scale(1.1);box-shadow:0 0 32px rgba(var(--accent-rgb),.6);}
.admin-open-btn.unlocked{background:var(--accent);color:#000;animation:pulseUnlock 2s infinite;}
@keyframes pulseUnlock{0%,100%{box-shadow:0 0 20px rgba(var(--accent-rgb),.5);}50%{box-shadow:0 0 40px rgba(var(--accent-rgb),1);}}
@media(max-width:900px){.admin-open-btn{top:15px;right:355px;width:40px;height:40px;}}
@media(max-width:640px){.admin-open-btn{right:auto;left:15px;top:65px;}}

.scroll-progress{position:fixed;top:0;left:0;height:3px;width:0%;background:linear-gradient(90deg,var(--accent),#00ccff,var(--accent));background-size:200% 100%;z-index:2000;pointer-events:none;box-shadow:0 0 14px rgba(var(--accent-rgb),.85);animation:gs 3s linear infinite;}
@keyframes gs{0%{background-position:0% 50%;}100%{background-position:200% 50%;}}
.parallax-bg{position:fixed;top:0;left:0;width:100%;height:100vh;pointer-events:none;z-index:0;overflow:hidden;}
.parallax-layer{position:absolute;top:0;left:0;width:100%;user-select:none;pointer-events:none;will-change:transform;}
.parallax-line{font-weight:bold;white-space:nowrap;letter-spacing:25px;padding:40px 0;text-align:center;}
.parallax-layer.back .parallax-line{font-size:5em;color:rgba(var(--accent-rgb),.028);}
.parallax-layer.middle .parallax-line{font-size:7em;color:rgba(255,0,0,.022);}
.watermark-overlay{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:1;overflow:hidden;}
.watermark-overlay .wm{position:absolute;color:rgba(var(--accent-rgb),.045);font-weight:bold;font-size:1.5em;letter-spacing:5px;white-space:nowrap;transform:rotate(-35deg);user-select:none;pointer-events:none;text-transform:uppercase;}

.sidebar{position:fixed;top:0;left:0;width:290px;height:100vh;background:linear-gradient(180deg,#080808,#060606);border-right:2px solid var(--accent);padding:25px 0;overflow-y:auto;z-index:1000;box-shadow:5px 0 40px rgba(0,0,0,.9);}
html[data-theme="light"] .sidebar{background:linear-gradient(180deg,#fff,#f0f0eb);}
.sidebar::-webkit-scrollbar{width:6px;}
.sidebar::-webkit-scrollbar-thumb{background:var(--accent);border-radius:3px;}
.sidebar-logo{padding:0 25px 25px;border-bottom:1px solid var(--border);margin-bottom:20px;}
.sidebar-logo .name{font-size:1.5em;font-weight:bold;letter-spacing:3px;background:linear-gradient(90deg,var(--accent),var(--accent-dim),var(--accent));background-size:200% auto;-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;display:block;margin-bottom:8px;animation:gs 4s linear infinite;}
.sidebar-logo .classif{display:inline-block;background:#ff2a2a;color:#fff;padding:3px 10px;font-size:.65em;letter-spacing:2px;font-weight:bold;border-radius:3px;animation:blink 2s infinite;}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:.45;}}
.sidebar-nav{padding:0 12px;}
.nav-section{margin-bottom:3px;}
.nav-section-header{display:flex;align-items:center;justify-content:space-between;color:var(--accent);text-decoration:none;padding:10px 14px;margin:2px 0;border-radius:6px;font-size:.88em;letter-spacing:1px;transition:.25s var(--ease);border-left:3px solid transparent;cursor:pointer;user-select:none;}
.nav-section-header:hover{background:rgba(var(--accent-rgb),.08);border-left-color:var(--accent);}
.nav-section-header .arrow{font-size:.7em;transition:transform .3s var(--ease);}
.nav-section-header.open .arrow{transform:rotate(90deg);}
.nav-section-header .label{flex:1;margin-left:8px;}
.nav-sub{max-height:0;overflow:hidden;transition:max-height .45s var(--ease);padding-left:10px;border-left:1px dashed #1f1f1f;margin-left:15px;}
html[data-theme="light"] .nav-sub{border-left-color:#ddd;}
.nav-sub.open{max-height:1200px;}
.nav-sub a{display:block;color:#88bbaa;text-decoration:none;padding:7px 14px;margin:2px 0;border-radius:5px;font-size:.78em;letter-spacing:.5px;transition:.25s var(--ease);border-left:2px solid transparent;}
html[data-theme="light"] .nav-sub a{color:#5a6a62;}
.nav-sub a:hover{background:rgba(var(--accent-rgb),.07);color:var(--accent);border-left-color:var(--accent-dim);padding-left:18px;}
.nav-sub a.active{background:rgba(var(--accent-rgb),.12);color:var(--accent);border-left-color:var(--accent);}

.main-content{margin-left:290px;padding:40px 20px;min-height:100vh;width:calc(100% - 290px);position:relative;z-index:10;background:rgba(5,5,5,.65);transition:background .4s var(--ease);}
html[data-theme="light"] .main-content{background:rgba(244,244,244,.82);}
body.admin-mode .main-content{overflow-x:auto;}
.main-inner{max-width:100%;margin:0 auto;}
.menu-toggle{display:none;position:fixed;top:15px;left:15px;z-index:1100;background:var(--accent);color:#000;border:none;padding:10px 15px;border-radius:8px;font-weight:bold;cursor:pointer;font-size:1.2em;}
@media(max-width:900px){.sidebar{transform:translateX(-100%);transition:transform .35s var(--ease);}.sidebar.open{transform:translateX(0);}.main-content{margin-left:0;padding:70px 12px 30px;width:100%;}.menu-toggle{display:block;}}

.search-box{position:fixed;top:20px;right:24px;width:340px;z-index:1300;}
.search-icon{position:absolute;left:14px;top:50%;transform:translateY(-50%);font-size:.95em;pointer-events:none;opacity:.55;}
.search-box input{width:100%;padding:12px 42px 12px 44px;background:rgba(8,8,8,.92);border:2px solid var(--border);border-radius:10px;color:var(--accent);font-family:inherit;font-size:.85em;letter-spacing:1px;outline:none;transition:.3s var(--ease);backdrop-filter:blur(10px);}
html[data-theme="light"] .search-box input{background:rgba(255,255,255,.95);border-color:#ddd;}
.search-box input::placeholder{color:#446;}
html[data-theme="light"] .search-box input::placeholder{color:#999;}
.search-box input:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(var(--accent-rgb),.12);}
.search-clear{position:absolute;right:10px;top:50%;transform:translateY(-50%);width:24px;height:24px;border-radius:50%;background:rgba(var(--accent-rgb),.15);color:var(--accent);border:none;cursor:pointer;font-size:.8em;display:none;align-items:center;justify-content:center;}
.search-box.has-value .search-clear{display:flex;}
.search-results{position:absolute;top:calc(100% + 10px);left:0;right:0;background:rgba(8,8,8,.98);border:1px solid var(--border);border-radius:10px;max-height:420px;overflow-y:auto;display:none;opacity:0;transform:translateY(-6px);transition:opacity .22s var(--ease),transform .22s var(--ease);backdrop-filter:blur(12px);box-shadow:0 24px 60px rgba(0,0,0,.85);}
html[data-theme="light"] .search-results{background:rgba(255,255,255,.99);}
.search-results.show{display:block;opacity:1;transform:none;}
.search-item{display:block;padding:11px 16px 11px 26px;color:#b0b0b0;text-decoration:none;border-bottom:1px solid #131313;font-size:.82em;cursor:pointer;position:relative;}
html[data-theme="light"] .search-item{color:#555;border-bottom-color:#ececec;}
.search-item::before{content:'▸';position:absolute;left:10px;top:50%;transform:translateY(-50%);color:var(--accent);opacity:0;transition:.2s;}
.search-item:hover,.search-item.active{background:rgba(var(--accent-rgb),.09);color:#e8e8e8;padding-left:32px;}
.search-item:hover::before,.search-item.active::before{opacity:1;}
.search-tag{display:inline-block;color:var(--accent-dim);font-size:.72em;letter-spacing:1.5px;text-transform:uppercase;margin-right:8px;padding:1px 6px;background:rgba(var(--accent-rgb),.08);border-radius:3px;font-weight:bold;}
.search-item mark{background:rgba(var(--accent-rgb),.28);color:var(--accent);padding:1px 3px;border-radius:3px;}
@media(max-width:900px){.search-box{top:15px;right:15px;width:calc(100% - 90px);max-width:340px;}}

.header{text-align:center;padding-bottom:40px;border-bottom:3px solid var(--accent);margin-bottom:50px;position:relative;overflow:hidden;}
.header::after{content:'';position:absolute;bottom:-3px;left:-100%;width:60%;height:3px;background:linear-gradient(90deg,transparent,#fff,transparent);animation:sh 4s ease-in-out infinite;}
@keyframes sh{0%{left:-60%;}60%,100%{left:120%;}}
.classification{display:inline-block;background:#ff2a2a;color:#fff;padding:8px 25px;font-weight:bold;letter-spacing:4px;font-size:.9em;margin-bottom:25px;border-radius:4px;box-shadow:0 0 30px rgba(255,0,0,.45);animation:blink 2s infinite;}
h1{font-size:clamp(2em,6vw,4em);background:linear-gradient(90deg,var(--accent),var(--accent-dim),var(--accent-deep),var(--accent));background-size:300% auto;-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;letter-spacing:5px;margin-bottom:15px;animation:gs 6s linear infinite;filter:drop-shadow(0 0 25px rgba(var(--accent-rgb),.25));}
.subtitle{color:var(--accent);font-size:clamp(.9em,2vw,1.2em);letter-spacing:3px;}
.codename{color:#666;font-size:.9em;margin-top:15px;letter-spacing:2px;}
html[data-theme="light"] .codename{color:#888;}
h2{color:var(--accent);font-size:clamp(1.3em,3vw,1.9em);margin:55px 0 25px;padding:18px 0 18px 25px;border-left:6px solid var(--accent);background:linear-gradient(90deg,rgba(var(--accent-rgb),.12),transparent);letter-spacing:2px;text-transform:uppercase;scroll-margin-top:20px;position:relative;}
h3{color:var(--accent-dim);font-size:clamp(1.05em,2.2vw,1.35em);margin:35px 0 18px;padding-left:18px;border-left:4px solid var(--accent-dim);letter-spacing:1px;scroll-margin-top:20px;}
h4{color:var(--accent);font-size:1.1em;margin:25px 0 12px;letter-spacing:1px;}
p{margin:12px 0;color:var(--text);}
strong{color:var(--accent);}
ul,ol{padding-left:30px;margin:18px 0;}
li{padding:8px 0 8px 10px;color:var(--text);border-bottom:1px dotted var(--border);}
.two-col-grid,.code-grid,.clearance-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:var(--grid-gap);margin:18px 0;width:100%;align-items:start;}
@media(max-width:1200px){.two-col-grid,.code-grid,.clearance-grid{grid-template-columns:1fr;}}
.data-table{width:100%;border-collapse:collapse;background:#0a0a0a;border:1px solid var(--border);font-size:.92em;}
html[data-theme="light"] .data-table{background:#fff;}
.data-table th{background:rgba(var(--accent-rgb),.08);color:var(--accent);padding:14px 16px;text-align:left;font-weight:bold;border-bottom:2px solid var(--accent);text-transform:uppercase;font-size:.85em;}
html[data-theme="light"] .data-table th{background:rgba(var(--accent-rgb),.12);color:#1a1a1a;}
.data-table td{padding:12px 16px;border-bottom:1px solid var(--border);color:var(--text);vertical-align:top;background:#0a0a0a;line-height:1.7;}
html[data-theme="light"] .data-table td{background:#fff;color:#333;border-color:#ececec;}
.data-table tr:hover td{background:#101010;color:#e8e8e8;}
.data-table strong{color:var(--accent);}
.table-wrap{background:#0a0a0a;border-radius:10px;overflow:hidden;margin:14px 0;width:100%;border:1px solid var(--border);}
html[data-theme="light"] .table-wrap{background:#fff;border-color:#e0e0e0;}
.code-card{padding:22px;border-radius:12px;background:var(--panel-2);border:2px solid;transition:.35s var(--ease);position:relative;overflow:hidden;}
html[data-theme="light"] .code-card{background:#fff;}
.code-card:hover{transform:translateY(-6px);box-shadow:0 18px 50px rgba(0,0,0,.7);}
.code-card::before{content:'';position:absolute;top:0;left:0;right:0;height:4px;}
.code-card h4{font-size:1.4em;margin-bottom:15px;letter-spacing:3px;}
.code-card p{font-size:.92em;color:#999;margin-bottom:12px;}
.code-red{border-color:#ff0000;background:linear-gradient(135deg,#0f0f0f,rgba(255,0,0,.08));}.code-red::before{background:#ff0000;}.code-red h4{color:#ff0000;}
.code-black{border-color:#444;background:linear-gradient(135deg,#0f0f0f,rgba(50,50,50,.15));}.code-black::before{background:#444;}.code-black h4{color:#999;}
.code-green{border-color:var(--accent);background:linear-gradient(135deg,#0f0f0f,rgba(var(--accent-rgb),.08));}.code-green::before{background:var(--accent);}.code-green h4{color:var(--accent);}
.code-blue{border-color:#4a90d9;background:linear-gradient(135deg,#0f0f0f,rgba(74,144,217,.08));}.code-blue::before{background:#4a90d9;}.code-blue h4{color:#4a90d9;}
.code-yellow{border-color:#ffcc00;background:linear-gradient(135deg,#0f0f0f,rgba(255,204,0,.08));}.code-yellow::before{background:#ffcc00;}.code-yellow h4{color:#ffcc00;}
.code-purple{border-color:#9013fe;background:linear-gradient(135deg,#0f0f0f,rgba(144,19,254,.08));}.code-purple::before{background:#9013fe;}.code-purple h4{color:#9013fe;}
.code-white{border-color:#ccc;background:linear-gradient(135deg,#0f0f0f,rgba(200,200,200,.08));}.code-white::before{background:#ccc;}.code-white h4{color:#ddd;}
.code-gray{border-color:#888;background:linear-gradient(135deg,#0f0f0f,rgba(136,136,136,.1));}.code-gray::before{background:#888;}.code-gray h4{color:#aaa;}
.code-silver{border-color:#c0c0c0;background:linear-gradient(135deg,#0f0f0f,rgba(192,192,192,.08));}.code-silver::before{background:#c0c0c0;}.code-silver h4{color:#c0c0c0;}
.code-superblue{border-color:#00ccff;background:linear-gradient(135deg,#0f0f0f,rgba(0,204,255,.08));}.code-superblue::before{background:#00ccff;}.code-superblue h4{color:#00ccff;}
.code-clean{border-color:#e0e0e0;background:linear-gradient(135deg,#0f0f0f,rgba(224,224,224,.06));}.code-clean::before{background:#e0e0e0;}.code-clean h4{color:#e0e0e0;}
.code-superclean{border-color:#ff69b4;background:linear-gradient(135deg,#0f0f0f,rgba(255,105,180,.08));}.code-superclean::before{background:#ff69b4;}.code-superclean h4{color:#ff69b4;}
.alert{padding:18px 24px;border-radius:10px;margin:18px 0;border-left:6px solid;font-size:.95em;}
.alert-danger{background:rgba(255,0,0,.08);border-color:#ff0000;color:#ff8888;}
.alert-info{background:rgba(var(--accent-rgb),.05);border-color:var(--accent);color:var(--accent-dim);}
.alert-warning{background:rgba(255,170,0,.08);border-color:#ffaa00;color:#ffcc66;}
.section{margin:24px 0;padding:24px;background:var(--panel);border-radius:12px;border:1px solid var(--border);}
html[data-theme="light"] .section{background:#fff;border-color:#e0e0e0;}
.footer{text-align:center;margin-top:70px;padding:40px 20px;border-top:2px solid var(--border);color:#555;font-size:.85em;letter-spacing:1px;background:#080808;border-radius:12px;}
html[data-theme="light"] .footer{background:#fff;color:#777;}
.discord,.telegram,.youtube{display:inline-block;color:#fff;padding:15px 40px;border-radius:12px;text-decoration:none;font-weight:bold;margin:10px;transition:.3s;letter-spacing:2px;}
.discord{background:#5865F2;}.discord:hover{background:#4752c4;transform:translateY(-3px) scale(1.04);}
.telegram{background:#0088cc;}.telegram:hover{background:#006699;transform:translateY(-3px) scale(1.04);}
.youtube{background:#ff0000;}.youtube:hover{background:#cc0000;transform:translateY(-3px) scale(1.04);}
.center{text-align:center;}
.acc{background:var(--panel);border:1px solid var(--border);border-radius:10px;overflow:hidden;align-self:start;}
html[data-theme="light"] .acc{background:#fff;border-color:#e0e0e0;}
.acc-head{width:100%;text-align:left;cursor:pointer;color:var(--accent);font-family:inherit;font-size:1em;font-weight:bold;letter-spacing:1px;background:var(--panel-2);border:none;border-left:5px solid var(--accent);padding:16px 20px;display:flex;align-items:center;gap:12px;}
html[data-theme="light"] .acc-head{background:#fafafa;}
.acc-head .acc-arrow{margin-left:auto;font-size:.7em;transition:transform .35s var(--ease);}
.acc.open .acc-head .acc-arrow{transform:rotate(90deg);}
.acc-body{display:grid;grid-template-rows:0fr;transition:grid-template-rows .45s var(--ease);}
.acc.open .acc-body{grid-template-rows:1fr;}
.acc-inner{overflow:hidden;}.acc-inner>*{padding:0 20px;}
.acc-inner>*:first-child{padding-top:16px;}.acc-inner>*:last-child{padding-bottom:16px;}
.highlight{background:rgba(var(--accent-rgb),.1);padding:2px 8px;border-radius:4px;color:var(--accent);}
.critical{background:rgba(255,0,0,.15);padding:2px 8px;border-radius:4px;color:#ff6666;font-weight:bold;}
.divider{height:2px;border:none;margin:40px 0;background:linear-gradient(90deg,transparent,var(--accent),transparent);opacity:.7;}
.clearance-card{padding:22px;border-radius:12px;border:2px solid;background:var(--panel-2);transition:.35s;}
html[data-theme="light"] .clearance-card{background:#fff;}
.clearance-card:hover{transform:translateY(-6px);box-shadow:0 18px 50px rgba(0,0,0,.7);}
.clearance-card h4{font-size:1.5em;margin-bottom:15px;letter-spacing:2px;}
.clearance-card p{font-size:.9em;color:#999;}
.level-1{border-color:#666;}.level-1 h4{color:#999;}
.level-2{border-color:#f5a623;}.level-2 h4{color:#f5a623;}
.level-3{border-color:#d0021b;}.level-3 h4{color:#d0021b;}
.level-4{border-color:#9013fe;}.level-4 h4{color:#9013fe;}
.level-5{border-color:var(--accent);}.level-5 h4{color:var(--accent);}
.level-a{border-color:#ff0000;}.level-a h4{color:#ff0000;}
.level-b{border-color:#ff8800;}.level-b h4{color:#ff8800;}
.level-c{border-color:#00ccff;}.level-c h4{color:#00ccff;}
.level-d{border-color:#666;}.level-d h4{color:#999;}
.level-e{border-color:#9013fe;}.level-e h4{color:#9013fe;}
.priv-card,.item-card,.scp-card{padding:22px;border-radius:12px;background:var(--panel-2);border:2px solid var(--accent);transition:.35s;}
html[data-theme="light"] .priv-card,html[data-theme="light"] .item-card,html[data-theme="light"] .scp-card{background:#fff;}
.priv-card:hover,.item-card:hover,.scp-card:hover{transform:translateY(-6px);box-shadow:0 18px 50px rgba(0,0,0,.7),0 0 35px rgba(var(--accent-rgb),.1);}
.priv-card h4,.scp-card h4{color:var(--accent);font-size:1.3em;margin-bottom:15px;letter-spacing:2px;}
.item-card h4{font-size:1.3em;margin-bottom:15px;letter-spacing:2px;}
.item-yes{border-color:var(--accent);}.item-yes h4{color:var(--accent);}
.item-no{border-color:#ff0000;}.item-no h4{color:#ff6666;}
.item-arrest{border-color:#ffaa00;}.item-arrest h4{color:#ffaa00;}
.item-execute{border-color:#d0021b;}.item-execute h4{color:#ff3333;}
.hp-badge{display:inline-block;background:rgba(255,0,0,.15);border:1px solid #ff4444;color:#ff8888;padding:4px 12px;border-radius:6px;font-size:.85em;font-weight:bold;margin-bottom:10px;}
.evacuated-badge{display:inline-block;background:rgba(255,170,0,.15);border:1px solid #ffaa00;color:#ffcc66;padding:4px 12px;border-radius:6px;font-size:.85em;font-weight:bold;margin-bottom:10px;}
.reveal{opacity:0;transform:translateY(34px);transition:opacity .8s var(--ease),transform .8s var(--ease);}
.reveal.in{opacity:1;transform:none;}
.to-top{position:fixed;right:24px;bottom:100px;width:52px;height:52px;border-radius:50%;background:linear-gradient(135deg,var(--accent),var(--accent-deep));color:#000;border:none;cursor:pointer;font-size:1.4em;font-weight:bold;display:flex;align-items:center;justify-content:center;z-index:1500;opacity:0;transform:translateY(20px) scale(.8);pointer-events:none;transition:.4s var(--ease);box-shadow:0 0 30px rgba(var(--accent-rgb),.5);}
.to-top.show{opacity:1;transform:none;pointer-events:auto;}
.to-top:hover{transform:translateY(-4px) scale(1.08);}

/* АДМИН-ПАНЕЛИ */
.admin-toolbar{position:fixed;top:0;left:0;right:0;background:linear-gradient(180deg,rgba(10,10,10,.99),rgba(15,15,15,.99));border-bottom:2px solid var(--accent);z-index:4500;display:none;flex-wrap:wrap;align-items:center;padding:6px 10px;gap:4px;box-shadow:0 6px 30px rgba(0,0,0,.85);backdrop-filter:blur(14px);}
html[data-theme="light"] .admin-toolbar{background:linear-gradient(180deg,rgba(255,255,255,.99),rgba(248,248,248,.99));}
.admin-toolbar.show{display:flex;}
.atb-logo{color:var(--accent);font-weight:bold;letter-spacing:2px;font-size:.78em;padding:6px 10px;border-right:1px solid var(--border);margin-right:4px;white-space:nowrap;}
.atb-btn{padding:6px 10px;background:rgba(255,255,255,.04);border:1px solid var(--border);border-radius:6px;color:#999;font-family:inherit;font-size:.72em;letter-spacing:.5px;cursor:pointer;transition:.2s;white-space:nowrap;display:flex;align-items:center;gap:5px;}
html[data-theme="light"] .atb-btn{background:#fafafa;color:#666;}
.atb-btn:hover{border-color:var(--accent);color:var(--accent);background:rgba(var(--accent-rgb),.08);}
.atb-btn.active{border-color:var(--accent);color:var(--accent);background:rgba(var(--accent-rgb),.15);}
.atb-btn.primary{background:var(--accent);color:#000;border-color:var(--accent);font-weight:bold;}
.atb-btn.primary:hover{box-shadow:0 0 20px rgba(var(--accent-rgb),.5);}
.atb-btn.danger:hover{border-color:#ff4444;color:#ff6666;background:rgba(255,0,0,.08);}
.atb-sep{width:1px;height:22px;background:var(--border);margin:0 2px;}
.atb-spacer{flex:1;min-width:10px;}
.atb-info{color:#666;font-size:.7em;letter-spacing:1px;padding:0 6px;white-space:nowrap;}
.atb-info b{color:var(--accent);}

.admin-blocks{position:fixed;top:48px;left:0;width:280px;height:calc(100vh - 48px - 56px);background:linear-gradient(180deg,rgba(10,10,10,.99),rgba(8,8,8,.99));border-right:2px solid var(--accent);z-index:4300;display:none;flex-direction:column;box-shadow:15px 0 40px rgba(0,0,0,.6);transform:translateX(-105%);transition:transform .35s var(--ease);}
html[data-theme="light"] .admin-blocks{background:linear-gradient(180deg,#fff,#f4f4f0);}
.admin-blocks.show{display:flex;transform:translateX(0);}
.abl-head{padding:12px 14px;border-bottom:2px solid var(--accent);display:flex;align-items:center;justify-content:space-between;background:rgba(var(--accent-rgb),.05);}
.abl-head h4{color:var(--accent);font-size:.78em;letter-spacing:2px;text-transform:uppercase;}
.abl-head .close{background:rgba(255,255,255,.05);border:1px solid var(--border);color:#888;border-radius:5px;padding:4px 8px;cursor:pointer;font-family:inherit;font-size:.7em;}
.abl-head .close:hover{color:#ff6666;border-color:#ff4444;}
.abl-search{padding:10px;}
.abl-search input{width:100%;padding:8px 12px;background:rgba(0,0,0,.4);border:1px solid var(--border);border-radius:6px;color:var(--accent);font-family:inherit;font-size:.78em;outline:none;}
html[data-theme="light"] .abl-search input{background:#fff;}
.abl-search input:focus{border-color:var(--accent);}
.abl-actions{padding:6px 10px;display:grid;grid-template-columns:1fr 1fr;gap:4px;border-top:1px solid var(--border);border-bottom:1px solid var(--border);}
.abl-action{padding:6px 8px;background:rgba(255,255,255,.03);border:1px solid var(--border);border-radius:5px;color:#999;font-family:inherit;font-size:.68em;cursor:pointer;transition:.2s;letter-spacing:.5px;}
html[data-theme="light"] .abl-action{background:#fafafa;color:#666;}
.abl-action:hover{border-color:var(--accent);color:var(--accent);}
.abl-action.full{grid-column:1 / -1;}
.abl-list{flex:1;overflow-y:auto;padding:6px;}
.abl-list::-webkit-scrollbar{width:5px;}
.abl-list::-webkit-scrollbar-thumb{background:var(--accent);border-radius:3px;}
.abl-item{padding:6px 8px;margin-bottom:2px;border-radius:5px;cursor:pointer;font-size:.72em;color:#999;display:flex;align-items:center;gap:6px;transition:.15s;border:1px solid transparent;overflow:hidden;}
html[data-theme="light"] .abl-item{color:#666;}
.abl-item:hover{background:rgba(var(--accent-rgb),.08);border-color:rgba(var(--accent-rgb),.3);color:var(--accent);}
.abl-item.selected{background:rgba(var(--accent-rgb),.18);border-color:var(--accent);color:var(--accent);font-weight:bold;}
.abl-item .abl-ico{width:16px;text-align:center;flex-shrink:0;}
.abl-item .abl-name{flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.abl-item .abl-type{color:#555;font-size:.9em;text-transform:uppercase;letter-spacing:.5px;flex-shrink:0;}
.abl-empty{padding:30px 12px;text-align:center;color:#555;font-size:.75em;letter-spacing:1px;}

.admin-props{position:fixed;top:48px;right:0;width:340px;height:calc(100vh - 48px - 56px);background:linear-gradient(180deg,rgba(10,10,10,.99),rgba(8,8,8,.99));border-left:2px solid var(--accent);z-index:4400;display:none;flex-direction:column;box-shadow:-15px 0 40px rgba(0,0,0,.7);transform:translateX(105%);transition:transform .35s var(--ease);}
html[data-theme="light"] .admin-props{background:linear-gradient(180deg,#fff,#f4f4f0);}
.admin-props.show{display:flex;transform:translateX(0);}
.ap-head{padding:12px 14px;border-bottom:2px solid var(--accent);display:flex;align-items:center;justify-content:space-between;background:rgba(var(--accent-rgb),.05);}
.ap-head h4{color:var(--accent);font-size:.78em;letter-spacing:2px;text-transform:uppercase;}
.ap-head .close{background:rgba(255,255,255,.05);border:1px solid var(--border);color:#888;border-radius:5px;padding:4px 8px;cursor:pointer;font-family:inherit;font-size:.7em;}
.ap-head .close:hover{color:#ff6666;border-color:#ff4444;}
.ap-tabs{display:flex;border-bottom:1px solid var(--border);background:rgba(0,0,0,.3);}
html[data-theme="light"] .ap-tabs{background:rgba(0,0,0,.02);}
.ap-tab{flex:1;padding:9px 4px;background:none;border:none;color:#666;font-family:inherit;font-size:.66em;letter-spacing:1px;text-transform:uppercase;cursor:pointer;transition:.2s;border-bottom:2px solid transparent;font-weight:bold;}
.ap-tab:hover{color:#aaa;}
.ap-tab.active{color:var(--accent);border-bottom-color:var(--accent);background:rgba(var(--accent-rgb),.05);}
.ap-body{flex:1;overflow-y:auto;padding:12px;}
.ap-body::-webkit-scrollbar{width:5px;}
.ap-body::-webkit-scrollbar-thumb{background:var(--accent);border-radius:3px;}
.ap-pane{display:none;}
.ap-pane.active{display:block;}
.ap-group{margin-bottom:14px;padding:10px;background:rgba(255,255,255,.02);border:1px solid var(--border);border-radius:8px;}
html[data-theme="light"] .ap-group{background:rgba(0,0,0,.02);}
.ap-group h5{color:var(--accent);font-size:.66em;letter-spacing:2px;text-transform:uppercase;margin-bottom:8px;padding-bottom:5px;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;}
.ap-group h5 .reset-prop{background:rgba(255,255,255,.05);border:1px solid var(--border);color:#666;border-radius:4px;padding:1px 6px;font-size:.75em;cursor:pointer;font-family:inherit;}
.ap-group h5 .reset-prop:hover{color:#ff6666;border-color:#ff4444;}
.ap-row{display:flex;align-items:center;gap:6px;margin-bottom:6px;}
.ap-row label{color:#888;font-size:.68em;letter-spacing:.5px;flex:0 0 80px;}
.ap-row input[type="text"],.ap-row input[type="number"],.ap-row select{flex:1;padding:5px 8px;background:rgba(0,0,0,.4);border:1px solid var(--border);border-radius:5px;color:var(--accent);font-family:inherit;font-size:.75em;outline:none;min-width:0;font-weight:bold;}
html[data-theme="light"] .ap-row input,html[data-theme="light"] .ap-row select{background:#fff;color:#333;}
.ap-row input:focus,.ap-row select:focus{border-color:var(--accent);}
.ap-row input::placeholder{color:#444;font-weight:normal;}
.ap-row input[type="color"]{width:30px;height:26px;padding:1px;border:1px solid var(--border);background:rgba(0,0,0,.4);border-radius:5px;cursor:pointer;flex:0 0 30px;}
.ap-row input[type="range"]{flex:1;accent-color:var(--accent);height:4px;}
.ap-row .range-val{color:var(--accent);font-size:.7em;font-weight:bold;min-width:44px;text-align:right;flex-shrink:0;}
.ap-grid3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:4px;}
.ap-mini{padding:5px 8px;background:rgba(255,255,255,.03);border:1px solid var(--border);border-radius:5px;color:#999;font-family:inherit;font-size:.68em;cursor:pointer;text-align:center;transition:.15s;}
html[data-theme="light"] .ap-mini{background:#fafafa;color:#666;}
.ap-mini:hover{border-color:var(--accent);color:var(--accent);}
.ap-mini.active{border-color:var(--accent);color:var(--accent);background:rgba(var(--accent-rgb),.12);}
.ap-actions{display:grid;grid-template-columns:repeat(2,1fr);gap:4px;margin-top:8px;}
.ap-action{padding:7px;background:rgba(255,255,255,.03);border:1px solid var(--border);border-radius:5px;color:#999;font-family:inherit;font-size:.68em;cursor:pointer;transition:.2s;text-align:center;letter-spacing:.5px;font-weight:bold;}
html[data-theme="light"] .ap-action{background:#fafafa;color:#666;}
.ap-action:hover{border-color:var(--accent);color:var(--accent);}
.ap-action.wide{grid-column:1 / -1;}
.ap-action.danger:hover{border-color:#ff4444;color:#ff6666;}
.ap-empty{padding:40px 14px;text-align:center;color:#555;font-size:.78em;letter-spacing:1px;}

.admin-bottom{position:fixed;bottom:0;left:0;right:0;height:56px;background:linear-gradient(0deg,rgba(10,10,10,.99),rgba(15,15,15,.99));border-top:2px solid var(--accent);z-index:4600;display:none;align-items:center;padding:0 10px;gap:5px;box-shadow:0 -6px 30px rgba(0,0,0,.7);backdrop-filter:blur(14px);overflow-x:auto;}
html[data-theme="light"] .admin-bottom{background:linear-gradient(0deg,rgba(255,255,255,.99),rgba(248,248,248,.99));}
.admin-bottom.show{display:flex;}
.admin-bottom::-webkit-scrollbar{height:4px;}
.admin-bottom::-webkit-scrollbar-thumb{background:var(--accent);border-radius:2px;}
.ab-label{color:#666;font-size:.7em;letter-spacing:1px;text-transform:uppercase;font-weight:bold;padding:0 6px;white-space:nowrap;}
.ab-preset{padding:6px 10px;background:rgba(255,255,255,.04);border:1px solid var(--border);border-radius:6px;color:var(--accent);font-family:inherit;font-size:.72em;font-weight:bold;cursor:pointer;transition:.15s;white-space:nowrap;letter-spacing:.5px;}
html[data-theme="light"] .ab-preset{background:#fafafa;}
.ab-preset:hover{background:rgba(var(--accent-rgb),.15);border-color:var(--accent);}
.ab-preset.active{background:var(--accent);color:#000;}
.ab-input{width:90px;padding:6px 8px;background:rgba(0,0,0,.4);border:1px solid var(--border);border-radius:6px;color:var(--accent);font-family:inherit;font-size:.75em;font-weight:bold;outline:none;text-align:center;}
html[data-theme="light"] .ab-input{background:#fff;color:#333;}
.ab-input:focus{border-color:var(--accent);}
.ab-input::placeholder{color:#555;font-weight:normal;}
.ab-unit{padding:6px 8px;background:rgba(255,255,255,.03);border:1px solid var(--border);border-radius:6px;color:#999;font-family:inherit;font-size:.72em;font-weight:bold;cursor:pointer;transition:.15s;}
.ab-unit.active{background:rgba(var(--accent-rgb),.15);color:var(--accent);border-color:var(--accent);}
.ab-sep{width:1px;height:28px;background:var(--border);margin:0 4px;flex-shrink:0;}

.block-toolbar{position:absolute;top:-30px;left:0;display:none;gap:2px;background:linear-gradient(135deg,rgba(10,10,10,.98),rgba(20,20,20,.98));border:1px solid var(--accent);border-radius:6px 6px 0 0;padding:2px 4px;z-index:3000;box-shadow:0 -4px 14px rgba(0,0,0,.6);pointer-events:auto;white-space:nowrap;}
html[data-theme="light"] .block-toolbar{background:linear-gradient(135deg,#fff,#f4f4f0);}
.block-toolbar .btb{width:22px;height:22px;border-radius:4px;background:rgba(255,255,255,.05);border:none;color:var(--accent);cursor:pointer;font-size:.72em;display:flex;align-items:center;justify-content:center;transition:.15s;padding:0;}
.block-toolbar .btb:hover{background:rgba(var(--accent-rgb),.2);transform:scale(1.12);}
.block-toolbar .btb.danger:hover{background:rgba(255,0,0,.2);color:#ff6666;}

.resize-handle{position:absolute;right:-7px;bottom:-7px;width:14px;height:14px;background:var(--accent);border:2px solid #000;border-radius:0 0 4px 0;cursor:nwse-resize;z-index:3100;display:none;box-shadow:0 0 10px rgba(var(--accent-rgb),.6);}
.resize-handle::after{content:'';position:absolute;right:2px;bottom:2px;width:5px;height:5px;border-right:2px solid #000;border-bottom:2px solid #000;}
.resize-handle.n{top:-5px;left:50%;right:auto;bottom:auto;transform:translateX(-50%);width:26px;height:8px;cursor:ns-resize;border-radius:4px;}
.resize-handle.s{bottom:-5px;left:50%;right:auto;transform:translateX(-50%);width:26px;height:8px;cursor:ns-resize;border-radius:4px;}
.resize-handle.w{left:-5px;top:50%;right:auto;bottom:auto;transform:translateY(-50%);width:8px;height:26px;cursor:ew-resize;border-radius:4px;}
.resize-handle.e{right:-5px;top:50%;left:auto;bottom:auto;transform:translateY(-50%);width:8px;height:26px;cursor:ew-resize;border-radius:4px;}
.resize-handle.ne{top:-7px;right:-7px;left:auto;bottom:auto;cursor:nesw-resize;}
.resize-handle.nw{top:-7px;left:-7px;right:auto;bottom:auto;cursor:nwse-resize;}
.resize-handle.sw{bottom:-7px;left:-7px;right:auto;top:auto;cursor:nesw-resize;}

body.admin-mode [data-editable-block]{position:relative;outline:1px dashed rgba(var(--accent-rgb),.3);outline-offset:2px;transition:outline .2s;}
body.admin-mode [data-editable-block]:hover{outline:1px dashed rgba(var(--accent-rgb),.6);}
body.admin-mode [data-editable-block].block-selected{outline:2px solid var(--accent);outline-offset:2px;box-shadow:0 0 0 4px rgba(var(--accent-rgb),.15),0 0 30px rgba(var(--accent-rgb),.3);z-index:1;}
body.admin-mode [data-editable-block].block-selected .block-toolbar{display:flex;}
body.admin-mode [data-editable-block].block-selected .resize-handle{display:block;}
body.admin-mode [data-editable-block].block-hidden{opacity:.35;outline-color:#ff4444 !important;}
body.admin-mode [data-editable-block].block-hidden::before{content:'СКРЫТ';position:absolute;top:4px;right:6px;background:#ff4444;color:#fff;font-size:.7em;padding:2px 8px;border-radius:4px;z-index:100;letter-spacing:1px;font-family:monospace;}
body.admin-mode [data-editable-block].block-locked{outline-color:#ffcc00 !important;}
body.admin-mode [data-editable-block].block-locked::after{content:'🔒';position:absolute;top:4px;left:6px;font-size:.9em;z-index:100;pointer-events:none;}
body.admin-mode [contenteditable="true"]:focus{outline:2px solid #ffcc00;outline-offset:2px;background:rgba(255,204,0,.06);}
.block-dragging{opacity:.5;}
.block-drop-target{outline:3px solid #ffcc00 !important;outline-offset:4px !important;}

.admin-ctx{position:fixed;z-index:4650;background:linear-gradient(180deg,#0d0d0d,#080808);border:1px solid var(--accent);border-radius:8px;padding:5px;display:none;min-width:220px;box-shadow:0 15px 50px rgba(0,0,0,.9);}
html[data-theme="light"] .admin-ctx{background:#fff;}
.admin-ctx.show{display:block;}
.admin-ctx .ctx-item{padding:7px 12px;color:#999;font-size:.76em;letter-spacing:.5px;cursor:pointer;border-radius:5px;display:flex;align-items:center;gap:10px;transition:.15s;font-family:inherit;white-space:nowrap;}
html[data-theme="light"] .admin-ctx .ctx-item{color:#555;}
.admin-ctx .ctx-item:hover{background:rgba(var(--accent-rgb),.15);color:var(--accent);}
.admin-ctx .ctx-item.danger:hover{background:rgba(255,0,0,.15);color:#ff6666;}
.admin-ctx .ctx-sep{height:1px;background:var(--border);margin:3px 0;}
.admin-ctx .ctx-hdr{color:#555;font-size:.68em;letter-spacing:2px;text-transform:uppercase;padding:6px 12px 3px;font-weight:bold;}

.sel-info{position:fixed;bottom:72px;left:50%;transform:translateX(-50%) translateY(80px);background:linear-gradient(135deg,#0d0d0d,#080808);border:2px solid var(--accent);border-radius:12px;padding:10px 20px;z-index:4700;display:flex;align-items:center;gap:14px;box-shadow:0 15px 50px rgba(0,0,0,.9),0 0 30px rgba(var(--accent-rgb),.3);transition:transform .35s var(--ease);pointer-events:none;white-space:nowrap;}
.sel-info.show{transform:translateX(-50%) translateY(0);pointer-events:auto;}
.sel-info b{color:var(--accent);font-size:1.1em;}
.sel-info span{color:#888;font-size:.8em;letter-spacing:1px;}
.sel-info button{background:var(--accent);color:#000;border:none;border-radius:6px;padding:6px 12px;cursor:pointer;font-family:inherit;font-weight:bold;font-size:.75em;letter-spacing:1px;}
.sel-info button.ghost{background:rgba(255,255,255,.05);color:#888;border:1px solid var(--border);}

.modal-backdrop{position:fixed;inset:0;z-index:5000;background:rgba(0,0,0,.8);display:none;align-items:center;justify-content:center;backdrop-filter:blur(8px);}
.modal-backdrop.show{display:flex;}
.modal{background:linear-gradient(180deg,#0d0d0d,#080808);border:2px solid var(--accent);border-radius:14px;padding:32px 28px;width:90%;max-width:380px;box-shadow:0 0 60px rgba(var(--accent-rgb),.35);text-align:center;}
html[data-theme="light"] .modal{background:#fff;}
.modal h3{color:var(--accent);margin-bottom:8px;letter-spacing:3px;text-transform:uppercase;font-size:1.15em;}
.modal .modal-sub{color:#666;font-size:.78em;margin-bottom:22px;letter-spacing:1px;}
.modal input{width:100%;padding:12px 16px;background:rgba(0,0,0,.5);border:2px solid var(--border);border-radius:8px;color:var(--text);font-family:inherit;font-size:1em;letter-spacing:3px;text-align:center;outline:none;transition:.25s;}
html[data-theme="light"] .modal input{background:#f8f8f5;color:#333;}
.modal input:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(var(--accent-rgb),.15);}
.modal-error{color:#ff6666;font-size:.82em;min-height:20px;margin-top:10px;letter-spacing:1px;}
.modal-actions{display:flex;gap:10px;margin-top:18px;}
.modal-btn{flex:1;padding:12px;border-radius:8px;border:none;cursor:pointer;font-family:inherit;font-weight:bold;letter-spacing:1.5px;font-size:.82em;transition:.25s;}
.modal-btn.primary{background:var(--accent);color:#000;}
.modal-btn.primary:hover{box-shadow:0 0 25px rgba(var(--accent-rgb),.6);}
.modal-btn.ghost{background:rgba(255,255,255,.05);color:#888;border:1px solid var(--border);}

body.admin-mode{padding-top:52px;padding-bottom:56px;}
body.admin-mode.blocks-open .main-content{margin-left:280px;}
body.admin-mode.props-open .main-content{margin-right:340px;}
body.admin-mode .to-top{bottom:120px;}
body.admin-mode.props-open .to-top{right:360px;}
</style>
</head>
<body>

<div class="scroll-progress" id="scrollProgress"></div>
<div class="parallax-bg">
  <div class="parallax-layer back" id="layer-back"></div>
  <div class="parallax-layer middle" id="layer-middle"></div>
</div>
<div class="watermark-overlay" id="watermark-overlay"></div>

<!-- ВИДИМАЯ КНОПКА АДМИНКИ -->
<button class="admin-open-btn" id="adminOpenBtn" title="Админ-панель" aria-label="Админ-панель">🔐</button>

<!-- МОДАЛКА ВХОДА -->
<div class="modal-backdrop" id="modalBackdrop">
  <div class="modal">
    <h3>🔐 Админ-панель</h3>
    <p class="modal-sub">Введите пароль</p>
    <input type="password" id="adminPasswordInput" placeholder="••••••••" autocomplete="off">
    <div class="modal-error" id="modalError"></div>
    <div class="modal-actions">
      <button class="modal-btn ghost" id="modalCancel" type="button">Отмена</button>
      <button class="modal-btn primary" id="modalSubmit" type="button">Войти</button>
    </div>
  </div>
</div>

<!-- ВЕРХНИЙ ТУЛБАР -->
<div class="admin-toolbar" id="adminToolbar">
  <span class="atb-logo">⚙ MV.ADMIN</span>
  <button class="atb-btn" id="tbBlocks" title="Менеджер блоков (Ctrl+B)">📋 Блоки</button>
  <button class="atb-btn" id="tbProps" title="Панель свойств (Ctrl+P)">🎛 Свойства</button>
  <span class="atb-sep"></span>
  <button class="atb-btn" id="tbTheme" title="Тема">🌙 Тема</button>
  <button class="atb-btn" id="tbColorPrev" title="Предыдущий цвет">◀</button>
  <button class="atb-btn" id="tbColorNext" title="Следующий цвет">▶</button>
  <button class="atb-btn" id="tbFont" title="Шрифт">🔤 <span id="tbFontLbl">Mono</span></button>
  <button class="atb-btn" id="tbBg" title="Фон">🌌 <span id="tbBgLbl">Пусто</span></button>
  <span class="atb-sep"></span>
  <button class="atb-btn" id="tbEditText" title="Правка текста (Ctrl+E)">✏ Текст</button>
  <button class="atb-btn" id="tbMoveMode" title="Перенос (Ctrl+M)">⠿ Перенос</button>
  <span class="atb-sep"></span>
  <button class="atb-btn" id="tbUndo" title="Отменить (Ctrl+Z)">↶</button>
  <button class="atb-btn" id="tbRedo" title="Вернуть (Ctrl+Y)">↷</button>
  <span class="atb-sep"></span>
  <button class="atb-btn" id="tbSelAll" title="Выделить всё (Ctrl+A)">⊞ Все</button>
  <button class="atb-btn" id="tbSelNone" title="Снять (Esc)">⊟ Нет</button>
  <button class="atb-btn" id="tbSelInv" title="Инвертировать (Ctrl+I)">⇄ Инв</button>
  <span class="atb-sep"></span>
  <button class="atb-btn" id="tbDup" title="Дублировать (Ctrl+D)">⧉</button>
  <button class="atb-btn danger" id="tbDelete" title="Удалить (Del)">🗑 Удалить</button>
  <button class="atb-btn" id="tbLock" title="Lock">🔒 Lock</button>
  <span class="atb-spacer"></span>
  <span class="atb-info" id="atbInfo">Выделено: <b>0</b></span>
  <button class="atb-btn primary" id="tbSave" title="Сохранить HTML (Ctrl+S)">💾 Сохранить</button>
  <button class="atb-btn danger" id="tbExit" title="Выйти">✕</button>
</div>

<!-- МЕНЕДЖЕР БЛОКОВ -->
<aside class="admin-blocks" id="adminBlocks">
  <div class="abl-head">
    <h4>📋 Блоки (<span id="ablCount">0</span>)</h4>
    <button class="close" id="ablClose">✕</button>
  </div>
  <div class="abl-search">
    <input type="text" id="ablSearch" placeholder="Фильтр по тексту или типу..." autocomplete="off">
  </div>
  <div class="abl-actions">
    <button class="abl-action" data-select="all">Выделить все</button>
    <button class="abl-action" data-select="none">Снять</button>
    <button class="abl-action" data-select="invert">Инвертировать</button>
    <button class="abl-action" data-select="visible">Видимые</button>
    <button class="abl-action full" data-select="sameType">Того же типа</button>
    <button class="abl-action" data-select="h2">H2</button>
    <button class="abl-action" data-select="h3">H3</button>
    <button class="abl-action" data-select="cards">Карточки</button>
    <button class="abl-action" data-select="tables">Таблицы</button>
    <button class="abl-action" data-select="alerts">Алерты</button>
    <button class="abl-action" data-select="grids">Сетки</button>
    <button class="abl-action" data-select="acc">Аккордеоны</button>
  </div>
  <div class="abl-list" id="ablList"></div>
</aside>

<!-- ПАНЕЛЬ СВОЙСТВ -->
<aside class="admin-props" id="adminProps">
  <div class="ap-head">
    <h4>🎛 Свойства</h4>
    <button class="close" id="apClose">✕</button>
  </div>
  <div class="ap-tabs">
    <button class="ap-tab active" data-tab="size">📐 Размер</button>
    <button class="ap-tab" data-tab="box">📦 Блок</button>
    <button class="ap-tab" data-tab="style">🎨 Стиль</button>
    <button class="ap-tab" data-tab="text">✍ Текст</button>
    <button class="ap-tab" data-tab="layout">⚙ Макет</button>
  </div>
  <div class="ap-body">
    <div id="apEmpty" class="ap-empty">Выдели блок на странице или в списке слева</div>
    <div id="apContent" style="display:none;">

      <div class="ap-pane active" data-pane="size">
        <div class="ap-group">
          <h5>Ширина и высота <button class="reset-prop" data-reset="width,height">сброс</button></h5>
          <div class="ap-row"><label>Ширина</label><input type="number" id="apW" step="10" placeholder="350"><select id="apWUnit" style="flex:0 0 60px;"><option value="%">%</option><option value="px">px</option><option value="vw">vw</option><option value="auto">auto</option></select></div>
          <div class="ap-row"><label>Высота</label><input type="number" id="apH" step="10" placeholder="200"><select id="apHUnit" style="flex:0 0 60px;"><option value="auto">auto</option><option value="px">px</option><option value="%">%</option><option value="vh">vh</option></select></div>
        </div>
        <div class="ap-group">
          <h5>Ограничения</h5>
          <div class="ap-row"><label>min-width</label><input type="text" id="apMinW" placeholder="auto"></div>
          <div class="ap-row"><label>max-width</label><input type="text" id="apMaxW" placeholder="none"></div>
          <div class="ap-row"><label>min-height</label><input type="text" id="apMinH" placeholder="auto"></div>
          <div class="ap-row"><label>max-height</label><input type="text" id="apMaxH" placeholder="none"></div>
        </div>
        <div class="ap-group">
          <h5>Быстрая ширина</h5>
          <div class="ap-grid3">
            <button class="ap-mini" data-preset="25%">25%</button><button class="ap-mini" data-preset="50%">50%</button><button class="ap-mini" data-preset="75%">75%</button>
            <button class="ap-mini" data-preset="100%">100%</button><button class="ap-mini" data-preset="125%">125%</button><button class="ap-mini" data-preset="150%">150%</button>
            <button class="ap-mini" data-preset="200%">200%</button><button class="ap-mini" data-preset="250%">250%</button><button class="ap-mini" data-preset="300%">300%</button>
            <button class="ap-mini" data-preset="350%">350%</button><button class="ap-mini" data-preset="500%">500%</button><button class="ap-mini" data-preset="auto">auto</button>
          </div>
        </div>
      </div>

      <div class="ap-pane" data-pane="box">
        <div class="ap-group">
          <h5>Padding <button class="reset-prop" data-reset="padding,padding-top,padding-right,padding-bottom,padding-left">сброс</button></h5>
          <div class="ap-row"><label>Все</label><input type="text" id="apPadAll" placeholder="10px / 10px 20px"></div>
          <div class="ap-row"><label>Верх</label><input type="text" id="apPadTop"></div>
          <div class="ap-row"><label>Право</label><input type="text" id="apPadRight"></div>
          <div class="ap-row"><label>Низ</label><input type="text" id="apPadBottom"></div>
          <div class="ap-row"><label>Лево</label><input type="text" id="apPadLeft"></div>
        </div>
        <div class="ap-group">
          <h5>Margin <button class="reset-prop" data-reset="margin,margin-top,margin-right,margin-bottom,margin-left">сброс</button></h5>
          <div class="ap-row"><label>Все</label><input type="text" id="apMarAll"></div>
          <div class="ap-row"><label>Верх</label><input type="text" id="apMarTop"></div>
          <div class="ap-row"><label>Право</label><input type="text" id="apMarRight"></div>
          <div class="ap-row"><label>Низ</label><input type="text" id="apMarBottom"></div>
          <div class="ap-row"><label>Лево</label><input type="text" id="apMarLeft"></div>
        </div>
        <div class="ap-group">
          <h5>Границы</h5>
          <div class="ap-row"><label>Ширина</label><input type="text" id="apBorW" placeholder="1px"></div>
          <div class="ap-row"><label>Стиль</label><select id="apBorS"><option value="">—</option><option value="solid">solid</option><option value="dashed">dashed</option><option value="dotted">dotted</option><option value="double">double</option><option value="none">none</option></select></div>
          <div class="ap-row"><label>Цвет</label><input type="color" id="apBorColor"><input type="text" id="apBorC"></div>
          <div class="ap-row"><label>Радиус</label><input type="text" id="apRadius" placeholder="12px"></div>
        </div>
      </div>

      <div class="ap-pane" data-pane="style">
        <div class="ap-group">
          <h5>Фон</h5>
          <div class="ap-row"><label>Цвет</label><input type="color" id="apBgColor"><input type="text" id="apBg"></div>
          <div class="ap-row"><label>Градиент</label><input type="text" id="apGrad" placeholder="linear-gradient(...)"></div>
          <div class="ap-row"><label>Картинка</label><input type="text" id="apBgImg" placeholder="url(...)"></div>
          <div class="ap-row"><label>Размер</label><select id="apBgSize"><option value="">—</option><option value="cover">cover</option><option value="contain">contain</option><option value="auto">auto</option><option value="100% 100%">100% 100%</option></select></div>
        </div>
        <div class="ap-group">
          <h5>Эффекты</h5>
          <div class="ap-row"><label>Цвет текста</label><input type="color" id="apTextColor"><input type="text" id="apTextC"></div>
          <div class="ap-row"><label>Тень</label><input type="text" id="apShadow" placeholder="0 8px 30px rgba(0,0,0,.5)"></div>
          <div class="ap-row"><label>Свечение</label><input type="text" id="apGlow" placeholder="0 0 20px #00ff88"></div>
          <div class="ap-row"><label>Прозрачность</label><input type="range" id="apOpacityR" min="0" max="100" value="100"><span class="range-val" id="apOpacityV">100%</span></div>
          <div class="ap-row"><label>Фильтр</label><input type="text" id="apFilter" placeholder="blur(2px)"></div>
          <div class="ap-row"><label>Трансформ</label><input type="text" id="apTransform" placeholder="rotate(0deg)"></div>
        </div>
      </div>

      <div class="ap-pane" data-pane="text">
        <div class="ap-group">
          <h5>Шрифт</h5>
          <div class="ap-row"><label>Семейство</label><select id="apFontFamily"><option value="">—</option><option value="'Consolas','Courier New',monospace">Mono</option><option value="'Segoe UI',system-ui,sans-serif">Sans</option><option value="Georgia,'Times New Roman',serif">Serif</option><option value="'Impact','Arial Black',sans-serif">Impact</option></select></div>
          <div class="ap-row"><label>Размер</label><input type="text" id="apFontSize" placeholder="16px"></div>
          <div class="ap-row"><label>Жирность</label><select id="apFontWeight"><option value="">—</option><option value="300">300</option><option value="400">400</option><option value="500">500</option><option value="600">600</option><option value="700">700</option><option value="800">800</option><option value="900">900</option></select></div>
          <div class="ap-row"><label>Курсив</label><select id="apFontStyle"><option value="">—</option><option value="normal">Normal</option><option value="italic">Italic</option></select></div>
        </div>
        <div class="ap-group">
          <h5>Форматирование</h5>
          <div class="ap-row"><label>Выравнивание</label><div class="ap-grid3" style="flex:1;"><button class="ap-mini" data-align="left">←</button><button class="ap-mini" data-align="center">↔</button><button class="ap-mini" data-align="right">→</button></div></div>
          <div class="ap-row"><label>Строки</label><input type="text" id="apLineHeight" placeholder="1.9"></div>
          <div class="ap-row"><label>Интервал букв</label><input type="text" id="apLetterSpacing" placeholder="1px"></div>
          <div class="ap-row"><label>Отступ строки</label><input type="text" id="apTextIndent"></div>
          <div class="ap-row"><label>Декорация</label><select id="apTextDecor"><option value="">—</option><option value="none">Нет</option><option value="underline">Подчёркнутый</option><option value="line-through">Зачёркнутый</option><option value="overline">Надчёркнутый</option></select></div>
          <div class="ap-row"><label>Трансформ</label><select id="apTextTransform"><option value="">—</option><option value="none">Нет</option><option value="uppercase">ВЕРХНИЙ</option><option value="lowercase">нижний</option><option value="capitalize">С Заглавной</option></select></div>
        </div>
      </div>

      <div class="ap-pane" data-pane="layout">
        <div class="ap-group">
          <h5>Display / Flex / Grid</h5>
          <div class="ap-row"><label>Display</label><select id="apDisplay"><option value="">—</option><option value="block">block</option><option value="inline-block">inline-block</option><option value="flex">flex</option><option value="inline-flex">inline-flex</option><option value="grid">grid</option><option value="none">none</option></select></div>
          <div class="ap-row"><label>Flex dir</label><select id="apFlexDir"><option value="">—</option><option value="row">row</option><option value="row-reverse">row-reverse</option><option value="column">column</option><option value="column-reverse">column-reverse</option></select></div>
          <div class="ap-row"><label>Justify</label><select id="apJustify"><option value="">—</option><option value="flex-start">flex-start</option><option value="center">center</option><option value="flex-end">flex-end</option><option value="space-between">space-between</option><option value="space-around">space-around</option><option value="space-evenly">space-evenly</option></select></div>
          <div class="ap-row"><label>Align items</label><select id="apAlignItems"><option value="">—</option><option value="flex-start">flex-start</option><option value="center">center</option><option value="flex-end">flex-end</option><option value="stretch">stretch</option></select></div>
          <div class="ap-row"><label>Gap</label><input type="text" id="apGap" placeholder="14px"></div>
          <div class="ap-row"><label>Grid cols</label><input type="text" id="apGridCols" placeholder="repeat(2, 1fr)"></div>
        </div>
        <div class="ap-group">
          <h5>Позиция</h5>
          <div class="ap-row"><label>Position</label><select id="apPosition"><option value="">—</option><option value="static">static</option><option value="relative">relative</option><option value="absolute">absolute</option><option value="fixed">fixed</option><option value="sticky">sticky</option></select></div>
          <div class="ap-row"><label>Top</label><input type="text" id="apTop"></div>
          <div class="ap-row"><label>Left</label><input type="text" id="apLeft"></div>
          <div class="ap-row"><label>Right</label><input type="text" id="apRight"></div>
          <div class="ap-row"><label>Bottom</label><input type="text" id="apBottom"></div>
          <div class="ap-row"><label>z-index</label><input type="text" id="apZindex"></div>
        </div>
        <div class="ap-group">
          <h5>Действия</h5>
          <div class="ap-actions">
            <button class="ap-action" data-act="up">↑ Вверх</button>
            <button class="ap-action" data-act="down">↓ Вниз</button>
            <button class="ap-action" data-act="dup">⧉ Дублировать</button>
            <button class="ap-action" data-act="hide">👁 Скрыть</button>
            <button class="ap-action" data-act="lock">🔒 Lock</button>
            <button class="ap-action" data-act="copyFull">📋 Копировать блок</button>
            <button class="ap-action wide" data-act="copySize">📋 Копировать размер</button>
            <button class="ap-action wide" data-act="pasteSize">📥 Вставить размер</button>
            <button class="ap-action wide" data-act="copyStyle">📋 Копировать все стили</button>
            <button class="ap-action wide" data-act="pasteStyle">📥 Вставить все стили</button>
            <button class="ap-action wide" data-act="applyAll">🌐 Применить ко всем</button>
            <button class="ap-action wide" data-act="reset">✕ Очистить стили</button>
            <button class="ap-action wide danger" data-act="delete">🗑 Удалить блок</button>
          </div>
        </div>
      </div>

    </div>
  </div>
</aside>

<!-- НИЖНЯЯ ПАНЕЛЬ -->
<div class="admin-bottom" id="adminBottom">
  <span class="ab-label">Ширина:</span>
  <button class="ab-preset" data-w="25%">25%</button><button class="ab-preset" data-w="50%">50%</button><button class="ab-preset" data-w="75%">75%</button><button class="ab-preset" data-w="100%">100%</button><button class="ab-preset" data-w="125%">125%</button><button class="ab-preset" data-w="150%">150%</button><button class="ab-preset" data-w="200%">200%</button><button class="ab-preset" data-w="250%">250%</button><button class="ab-preset" data-w="300%">300%</button><button class="ab-preset" data-w="350%">350%</button><button class="ab-preset" data-w="500%">500%</button>
  <span class="ab-sep"></span>
  <input type="number" class="ab-input" id="abWidthCustom" placeholder="Своё" step="5">
  <button class="ab-unit active" data-unit="%">%</button><button class="ab-unit" data-unit="px">px</button><button class="ab-unit" data-unit="vw">vw</button>
  <button class="ab-preset" id="abApplyW">→</button>
  <span class="ab-sep"></span>
  <span class="ab-label">Высота:</span>
  <input type="number" class="ab-input" id="abHeightCustom" placeholder="Своё" step="10">
  <button class="ab-unit active" data-hunit="px">px</button><button class="ab-unit" data-hunit="%">%</button><button class="ab-unit" data-hunit="vh">vh</button>
  <button class="ab-preset" id="abApplyH">→</button>
  <span class="ab-sep"></span>
  <span class="ab-label">Выравнивание:</span>
  <button class="ab-preset" id="abAlignLeft">← Растянуть</button><button class="ab-preset" id="abAlignCenter">↔ Центр</button><button class="ab-preset" id="abAlignRight">→ Растянуть</button>
  <span class="ab-sep"></span>
  <span class="ab-label">Уравнять:</span>
  <button class="ab-preset" id="abEqualW">= Ширина</button><button class="ab-preset" id="abEqualH">= Высота</button><button class="ab-preset" id="abMatchFirst">Скопировать</button>
  <span class="ab-sep"></span>
  <button class="ab-preset" id="abResetSize">↺ Размер</button>
</div>

<!-- КОНТЕКСТНОЕ МЕНЮ -->
<div class="admin-ctx" id="adminCtx">
  <div class="ctx-hdr">Блок</div>
  <div class="ctx-item" data-action="edit">✏ Редактировать текст</div>
  <div class="ctx-item" data-action="rename">🏷 Переименовать</div>
  <div class="ctx-sep"></div>
  <div class="ctx-item" data-action="dup">⧉ Дублировать</div>
  <div class="ctx-item" data-action="up">↑ Вверх</div>
  <div class="ctx-item" data-action="down">↓ Вниз</div>
  <div class="ctx-sep"></div>
  <div class="ctx-item" data-action="copySize">📋 Копировать размер</div>
  <div class="ctx-item" data-action="pasteSize">📥 Вставить размер</div>
  <div class="ctx-item" data-action="copyStyle">📋 Копировать стили</div>
  <div class="ctx-item" data-action="pasteStyle">📥 Вставить стили</div>
  <div class="ctx-item" data-action="applyAll">🌐 Применить ко всем</div>
  <div class="ctx-sep"></div>
  <div class="ctx-item" data-action="hide">👁 Скрыть / Показать</div>
  <div class="ctx-item" data-action="lock">🔒 Lock / Unlock</div>
  <div class="ctx-item" data-action="reset">✕ Очистить стили</div>
  <div class="ctx-sep"></div>
  <div class="ctx-item danger" data-action="delete">🗑 Удалить</div>
</div>

<!-- ПЛАШКА ВЫДЕЛЕНИЯ -->
<div class="sel-info" id="selInfo">
  <span>Выделено: <b id="selCount">0</b></span>
  <button id="selProps">Свойства</button>
  <button id="selApplyFirst">Размер 1-го → всем</button>
  <button class="ghost" id="selClear">Снять</button>
</div>

<button class="menu-toggle" onclick="document.querySelector('.sidebar').classList.toggle('open')">☰</button>

<div class="search-box" id="searchBox">
  <span class="search-icon">🔍</span>
  <input type="text" id="searchInput" placeholder="Поиск по уставу..." autocomplete="off" spellcheck="false">
  <button class="search-clear" id="searchClear" type="button">✕</button>
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
  <div class="main-inner">

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
        <tr><td><strong>Альфа-40</strong></td><td>«Мятежники»</td><td>Ликвидация неавторизованных.</td></tr>
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
      <div class="priv-card reveal" id="priv-forbidden" style="border-color:#ff0000;"><h4 style="color:#ff6666;">❌ Что ЗАПРЕЩЕНО админу</h4><ul><li>Оскорблять игроков или коллег.</li><li>Злоупотреблять полномочиями.</li><li>Игнорировать игроков.</li><li>Читерить или использовать софт.</li><li>Использовать команды в личных целях.</li><li>Сливать информацию из админ-чата.</li><li>Кормить читеров.</li><li>Создавать конфликты на публике.</li><li>Отсутствовать 7+ дней.</li></ul></div>
      <div class="priv-card reveal" id="priv-lies" style="border-color:#ffaa00;"><h4 style="color:#ffaa00;">⚠️ Наказания за враньё</h4><ul><li><strong>1-е:</strong> строгий выговор.</li><li><strong>2-е:</strong> временный ЧСА (3–7 дней).</li><li><strong>3-е:</strong> понижение или пожизненный ЧСА.</li></ul></div>
      <div class="priv-card reveal" id="priv-confidential" style="border-color:#ff0000;"><h4 style="color:#ff6666;">🚫 Конфиденциальность переписок</h4><ul><li>Запрещено публиковать скриншоты админ-чата.</li><li>Запрещено пересылать личные сообщения.</li><li>Запрещено рассказывать игрокам об обсуждениях.</li><li><strong>Даже для обжалования</strong> нельзя показывать переписки.</li><li><strong>Наказание:</strong> ПОЖИЗНЕННЫЙ ЧСА.</li></ul></div>
      <div class="priv-card reveal" id="priv-others" style="border-color:#9013fe;"><h4 style="color:#c07aff;">🛡️ Админство на других серверах</h4><ul><li>Запрещено быть админом на других серверах.</li><li>Конфликт интересов.</li><li><strong>Наказание:</strong> пожизненный ЧСА.</li></ul></div>
      <div class="priv-card reveal" id="priv-hierarchy" style="border-color:#00ff88;"><h4>👑 Иерархия должностей</h4><ul><li><strong>Высший состав:</strong> Владелец, Со-владелец, Гл. Админ, Зам., HR, Dev.</li><li><strong>Кураторы:</strong> Ст. куратор и кураторы отделов.</li><li><strong>Ивент-отдел:</strong> Гл. ивентолог, ивентолог.</li><li><strong>Администраторы:</strong> Ст. админ, админ, мл. админ.</li><li><strong>Модераторы:</strong> Ст. модер, модер, мл. модер.</li><li><strong>Помощники:</strong> Ст. помощник, помощник, мл. помощник.</li><li><strong>Стажёры:</strong> Ст. стажёр, стажёр, кандидат, испытательный.</li><li><strong>Контент-мейкеры:</strong> Гл. КМ, ст. КМ, КМ, видео-оператор, стример, летсплейщик.</li></ul></div>
      <div class="priv-card reveal" id="priv-punish" style="border-color:#f5a623;"><h4 style="color:#f5a623;">⚖️ Виды взысканий</h4><ul><li><strong>Выговор устный</strong> — мелкие нарушения.</li><li><strong>Выговор письменный</strong> — грубые или повторные.</li><li><strong>Временный ЧСА</strong> — систематические (3–30 дней).</li><li><strong>Понижение</strong> — неисполнение обязанностей.</li><li><strong>Пожизненный ЧСА</strong> — за читерство, слив, оскорбления, враньё (3+), админство на других.</li></ul></div>
      <div class="priv-card reveal" id="priv-rights" style="border-color:#00ccff;"><h4 style="color:#00ccff;">📋 Права администрации</h4><ul><li>Право на ошибку, если готов её признать.</li><li>Право на защиту своей позиции.</li><li>Право обратиться к старшему или владельцу.</li><li>Право на апелляцию наказания.</li></ul></div>
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
      <div class="scp-card reveal"><h4>🧱 SCP-173 — Статуя</h4><div class="hp-badge">❤️ 10 000 HP</div><p><strong>Разумность:</strong> ❌ Нет (автомат, не мыслит)</p><ul><li><strong>Скачок</strong> — телепорт до 8 м при зрительном контакте. Убивает ближайшего человека.</li><li><strong>Лужа грязи</strong> — замедляет людей (F).</li><li>Сопротивление пулям (кроме Micro H.I.D.).</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> двигаться при отсутствии зрительного контакта, оставлять лужи.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> телепортироваться при 3+ наблюдателях, убивать без RP-причины.</p><p><strong>Наказание:</strong> бан 7-30 дней.</p></div>
      <div class="scp-card reveal"><h4>🩺 SCP-049 — Чумной Доктор</h4><div class="hp-badge">❤️ 5 000 HP</div><p><strong>Разумность:</strong> ✅ Да (имеет интеллект, общается)</p><ul><li><strong>Сердечный приступ</strong> — атака наносит продолжительный урон.</li><li><strong>Воскрешение</strong> — поднимает мёртвых как SCP-049-2 (зомби).</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> лечить, воскрешать зомби по RP-причине.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> убивать всех подряд, воскрешать без RP-причины.</p><p><strong>Наказание:</strong> бан 3-7 дней.</p></div>
      <div class="scp-card reveal"><h4>👴 SCP-106 — Старик</h4><div class="hp-badge">❤️ 7 000 HP</div><p><strong>Разумность:</strong> ✅ Да (имеет интеллект)</p><ul><li><strong>Захват</strong> — отправляет человека в карманное измерение.</li><li><strong>Погружение</strong> — скрывается в полу (Shift).</li><li>Сопротивление пулям, слаб к другим источникам урона.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> захватывать людей по RP-причине, скрываться.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> отправлять в карманное измерение без RP-причины.</p><p><strong>Наказание:</strong> бан 3-7 дней.</p></div>
      <div class="scp-card reveal" style="border-color:#ffaa00;"><h4>😢 SCP-096 — Застенчивый</h4><div class="evacuated-badge">🚨 ЭВАКУИРОВАН ИЗ УЧАСТКА 11</div><p style="color:#ffcc66;"><strong>Статус:</strong> SCP-096 был <strong>эвакуирован из Участка 11</strong> и переведён в другой объект Фонда. На данном Участке не содержится и не появляется.</p><p style="color:#ffcc66;"><strong>Причина:</strong> Угроза признана слишком высокой для содержания на Участке 11. Все правила и механики, связанные с SCP-096, <strong>временно отключены</strong>.</p><p style="color:#ff8888;"><strong>Внимание:</strong> Если вы заметили SCP-096 на территории Участка — немедленно сообщите администрации. Это может быть баг или ивент.</p></div>
      <div class="scp-card reveal"><h4>👄 SCP-939 — Многоголосый</h4><div class="hp-badge">❤️ 7 000 HP</div><p><strong>Разумность:</strong> ⚠️ Полуразумный (умеет охотиться, но не мыслит)</p><p><strong>Особенности:</strong></p><ul><li>Умеет <strong>охотиться</strong> на людей по звуку.</li><li><strong>Не умеет думать</strong> — действует на инстинктах.</li><li>Может <strong>только произносить звуки</strong> (имитирует голоса), но не понимает их смысла.</li><li>Не способен к RP-диалогу — издаёт звуки для приманки.</li></ul><p><strong>Способности:</strong></p><ul><li><strong>Мимикрия</strong> — имитирует голоса людей.</li><li><strong>Укус</strong> — 65 урона + амнезия (нельзя перезарядиться).</li><li>Чувствительность к звуку (видит сквозь стены).</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> использовать звук для охоты, имитировать голоса.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> игнорировать правила, кемперить.</p><p><strong>Наказание:</strong> предупреждение / бан 1 день.</p></div>
      <div class="scp-card reveal"><h4>💀 SCP-3114 — Скелет</h4><div class="hp-badge">❤️ 6 000 HP</div><p><strong>Разумность:</strong> ✅ Да (маскируется под человека)</p><ul><li><strong>Скелеты в шкафу</strong> — снимает кожу с трупов, маскируется.</li><li><strong>Удушение</strong> — захват человека.</li><li>Может использовать предметы в облике.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> маскироваться, общаться с людьми в облике.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> быстро раскрываться, убивать без RP-причины.</p><p><strong>Наказание:</strong> бан 1-3 дня.</p></div>
      <div class="scp-card reveal"><h4>💻 SCP-079 — Старый ИИ</h4><div class="hp-badge">❤️ 0 HP (уязвим к перегрузке)</div><p><strong>Разумность:</strong> ✅ Да (искусственный интеллект)</p><ul><li>Управление дверями, лифтами, тесла-воротами.</li><li>Громкоговоритель, блокировка дверей.</li><li>Видит людей с SCP-268.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> помогать другим SCP, управлять системами.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> игнорировать просьбы других SCP.</p><p><strong>Наказание:</strong> предупреждение / бан 1 день.</p></div>
      <div class="scp-card reveal" id="scp953"><h4>🦊 SCP-953 — Полиморфная рептилия</h4><div class="hp-badge">❤️ 1 600 HP</div><p><strong>Разумность:</strong> ✅ Да (лис-оборотень)</p><ul><li>Принимает облик человека.</li><li>Невидимость в облике.</li><li>Атаки в ближнем бою.</li></ul><p style="color:#88ffbb;"><strong>Можно:</strong> использовать облик для RP.</p><p style="color:#ff6666;"><strong>Нельзя:</strong> использовать облик для RDM, заманивать в ловушки.</p><p><strong>Наказание:</strong> бан 7-14 дней.</p></div>
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
      <div class="reveal"><h3>Правила апелляции</h3><div class="alert alert-danger"><ul><li>Запрещено оскорблять администрацию.</li><li>Запрещено дублировать апелляции.</li><li>Запрещено подавать с другого аккаунта.</li><li>Решение окончательное.</li><li>Без доказательств — последняя очередь.</li></ul></div><h3>Шаблон апелляции</h3><div class="section" style="margin:0;padding:15px;"><p><strong>SteamID:</strong> [ваш ID]</p><p><strong>Причина бана:</strong> [причина]</p><p><strong>Кто забанил:</strong> [ник]</p><p><strong>Объяснение:</strong> [почему несправедлив]</p><p><strong>Доказательства:</strong> [ссылка]</p></div></div>
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
      <p style="margin-top:15px;color:#333;">CLASSIFIED — LEVEL 5 CLEARANCE REQUIRED</p>
    </div>

  </div>
</main>

<button class="to-top" id="toTop">↑</button>

<script>
const ADMIN_PASSWORD = 'MV-Admin-2026';
const STORAGE_KEY = 'mvp-admin-v4';
const html = document.documentElement;
const state = {
  accent:'green', theme:'dark', font:'mono', bgfx:'default',
  editMode:false, moveMode:false, blocksPanel:false, propsPanel:false,
  selected:[], clipboardSize:null, clipboardStyle:null, clipboardFull:null,
  dragSrc:null, history:{stack:[],idx:-1,max:60}, unitW:'%', unitH:'px', blockNames:{}
};
const ALL_COLORS = ['green','cyan','blue','purple','magenta','pink','red','orange','amber','yellow','lime','white'];
const ALL_FONTS = [{id:'mono',lbl:'Mono'},{id:'sans',lbl:'Sans'},{id:'serif',lbl:'Serif'},{id:'cyber',lbl:'Cyber'}];
const ALL_BGS = ['default','grid','noise','gradient','space'];
const EDITABLE_SELECTOR = '.code-card, .clearance-card, .priv-card, .item-card, .scp-card, .alert, .section, .table-wrap, .acc, .footer, .header, h2, h3, h4, p, ul, ol, .center, .divider, .subtitle, .codename, .classification';
const TEXT_SELECTOR = 'h1, h2, h3, h4, p, li, td, th, strong, .subtitle, .codename, .classification, .highlight, .hp-badge, .evacuated-badge';

function qs(s,r){return (r||document).querySelector(s);}
function qsa(s,r){return Array.from((r||document).querySelectorAll(s));}
function toggleSection(el){el.classList.toggle('open');const s=el.nextElementSibling;if(s)s.classList.toggle('open');}
window.toggleSection = toggleSection;
function toast(msg,type){
  const t=document.createElement('div');
  t.textContent=msg;
  t.style.cssText=`position:fixed;top:70px;left:50%;transform:translateX(-50%);background:${type==='error'?'#ff4444':'var(--accent)'};color:${type==='error'?'#fff':'#000'};padding:10px 22px;border-radius:8px;font-weight:bold;z-index:9999;box-shadow:0 8px 30px rgba(0,0,0,.5);font-family:monospace;letter-spacing:1px;pointer-events:none;opacity:0;transition:opacity .3s;font-size:.85em;`;
  document.body.appendChild(t);
  requestAnimationFrame(()=>t.style.opacity='1');
  setTimeout(()=>{t.style.opacity='0';setTimeout(()=>t.remove(),300);},2000);
}

/* ВИДИМАЯ КНОПКА */
const adminOpenBtn = qs('#adminOpenBtn');
adminOpenBtn.addEventListener('click',()=>{
  if(document.body.classList.contains('admin-mode')){
    qs('#adminToolbar').classList.add('show');
    qs('#adminBottom').classList.add('show');
    return;
  }
  openLoginModal();
});

/* МОДАЛКА */
const modalBackdrop=qs('#modalBackdrop');
const adminPasswordInput=qs('#adminPasswordInput');
const modalError=qs('#modalError');
function openLoginModal(){modalBackdrop.classList.add('show');modalError.textContent='';adminPasswordInput.value='';setTimeout(()=>adminPasswordInput.focus(),80);}
function closeLoginModal(){modalBackdrop.classList.remove('show');}
qs('#modalCancel').addEventListener('click',closeLoginModal);
qs('#modalSubmit').addEventListener('click',tryLogin);
adminPasswordInput.addEventListener('keydown',e=>{if(e.key==='Enter')tryLogin();if(e.key==='Escape')closeLoginModal();});
modalBackdrop.addEventListener('click',e=>{if(e.target===modalBackdrop)closeLoginModal();});
function tryLogin(){
  if(adminPasswordInput.value===ADMIN_PASSWORD){closeLoginModal();activateAdmin();}
  else{modalError.textContent='Неверный пароль';adminPasswordInput.value='';adminPasswordInput.focus();}
}

/* АКТИВАЦИЯ */
function activateAdmin(){
  document.body.classList.add('admin-mode');
  qs('#adminToolbar').classList.add('show');
  qs('#adminBottom').classList.add('show');
  adminOpenBtn.classList.add('unlocked');
  adminOpenBtn.textContent='⚙';
  markEditable();
  applyStateToUI();
  bindBlockEvents();
  bindGlobalEvents();
  buildBlockList();
  pushHistory();
  toast('✅ Админ-режим активен');
  localStorage.setItem(STORAGE_KEY+'-unlocked','1');
}
function deactivateAdmin(){
  document.body.classList.remove('admin-mode','blocks-open','props-open');
  qs('#adminToolbar').classList.remove('show');
  qs('#adminBlocks').classList.remove('show');
  qs('#adminProps').classList.remove('show');
  qs('#adminBottom').classList.remove('show');
  adminOpenBtn.classList.remove('unlocked');
  adminOpenBtn.textContent='🔐';
  clearSelection();
  unmarkEditable();
  localStorage.removeItem(STORAGE_KEY+'-unlocked');
  toast('Админ-режим выключен');
}
function markEditable(){qsa(EDITABLE_SELECTOR,qs('.main-inner')).forEach(el=>{if(!el.hasAttribute('data-editable-block')){el.setAttribute('data-editable-block','1');el.style.position=el.style.position||'relative';}});}
function unmarkEditable(){qsa('[data-editable-block]').forEach(el=>el.removeAttribute('data-editable-block'));qsa('.block-toolbar, .resize-handle').forEach(el=>el.remove());}

/* UI БЛОКОВ */
function bindBlockEvents(){qsa('[data-editable-block]').forEach(el=>{if(el.querySelector(':scope > .block-toolbar'))return;attachBlockUI(el);});}
function attachBlockUI(el){
  const tb=document.createElement('div');
  tb.className='block-toolbar';
  tb.innerHTML=`<button class="btb" data-act="drag" title="Перетащить">⠿</button>
    <button class="btb" data-act="edit" title="Правка">✏</button>
    <button class="btb" data-act="w100" title="100%">100</button>
    <button class="btb" data-act="w150" title="150%">150</button>
    <button class="btb" data-act="w200" title="200%">200</button>
    <button class="btb" data-act="w350" title="350%">350</button>
    <button class="btb" data-act="copySize" title="Копировать размер">📋</button>
    <button class="btb" data-act="pasteSize" title="Вставить размер">📥</button>
    <button class="btb" data-act="dup" title="Дублировать">⧉</button>
    <button class="btb danger" data-act="delete" title="Удалить">🗑</button>`;
  el.appendChild(tb);
  ['nw','n','ne','w','e','sw','s','se'].forEach(pos=>{
    const h=document.createElement('div');
    h.className='resize-handle '+pos;
    h.dataset.dir=pos;
    el.appendChild(h);
  });
  el.addEventListener('click',e=>{
    if(e.target.closest('.block-toolbar, .resize-handle, [contenteditable="true"], a, button, input, select'))return;
    if(state.moveMode)return;
    e.stopPropagation();
    handleBlockClick(el,e);
  });
  el.addEventListener('contextmenu',e=>{
    if(e.target.closest('.block-toolbar, .resize-handle'))return;
    e.preventDefault();
    if(!state.selected.includes(el)){if(!e.shiftKey&&!e.ctrlKey&&!e.metaKey)clearSelection();addSelection(el);}
    openContextMenu(e.clientX,e.clientY);
  });
  el.addEventListener('dblclick',e=>{
    if(e.target.closest('.block-toolbar, .resize-handle'))return;
    if(!state.editMode)return;
    const t=e.target.closest(TEXT_SELECTOR);
    if(t){t.setAttribute('contenteditable','true');t.focus();}
  });
  tb.addEventListener('click',e=>{
    const btn=e.target.closest('.btb');
    if(!btn)return;
    e.stopPropagation();
    const act=btn.dataset.act;
    if(!state.selected.includes(el))selectSingle(el);
    if(act==='drag')startDrag(el);
    else if(act==='edit')toggleBlockEditMode(el);
    else if(act==='dup')duplicateBlock(el);
    else if(act==='copySize')copySize();
    else if(act==='pasteSize')pasteSize();
    else if(act==='delete')deleteBlock(el);
    else if(act.startsWith('w')){const w=act.slice(1)+'%';state.selected.forEach(x=>{x.style.width=w;});pushHistory();}
  });
  qsa('.resize-handle',el).forEach(h=>{h.addEventListener('mousedown',e=>startResize(e,el,h.dataset.dir));});
  if(state.moveMode)el.setAttribute('draggable','true');
}

/* ВЫДЕЛЕНИЕ */
function handleBlockClick(el,e){
  if(e.shiftKey||e.ctrlKey||e.metaKey){
    if(state.selected.includes(el))removeSelection(el);else addSelection(el);
  }else{clearSelection();addSelection(el);}
}
function addSelection(el){if(!state.selected.includes(el)){state.selected.push(el);el.classList.add('block-selected');updateSelectionUI();}}
function removeSelection(el){const i=state.selected.indexOf(el);if(i>-1){state.selected.splice(i,1);el.classList.remove('block-selected');updateSelectionUI();}}
function clearSelection(){state.selected.forEach(el=>el.classList.remove('block-selected'));state.selected=[];updateSelectionUI();}
function selectSingle(el){clearSelection();addSelection(el);}
function updateSelectionUI(){
  const n=state.selected.length;
  qs('#selCount').textContent=n;
  qs('#atbInfo').innerHTML=`Выделено: <b>${n}</b>`;
  qs('#selInfo').classList.toggle('show',n>0);
  if(n===1){qs('#apEmpty').style.display='none';qs('#apContent').style.display='block';fillPropsPanel(state.selected[0]);}
  else if(n>1){qs('#apEmpty').style.display='none';qs('#apContent').style.display='block';clearPropsPanel();}
  else{qs('#apEmpty').style.display='block';qs('#apContent').style.display='none';}
  qsa('.abl-item').forEach(item=>{const id=item.dataset.blockId;const el=findBlockById(id);item.classList.toggle('selected',el&&state.selected.includes(el));});
}

/* ID СИСТЕМА */
function findBlockById(id){return qsa('[data-editable-block]').find(el=>el.dataset.blockId===id);}
function ensureBlockId(el){if(!el.dataset.blockId){el.dataset.blockId='b_'+Math.random().toString(36).slice(2,9);}return el.dataset.blockId;}

/* СПИСОК БЛОКОВ */
function buildBlockList(){
  const list=qs('#ablList');
  list.innerHTML='';
  const blocks=qsa('[data-editable-block]',qs('.main-inner'));
  qs('#ablCount').textContent=blocks.length;
  if(!blocks.length){list.innerHTML='<div class="abl-empty">Нет блоков</div>';return;}
  blocks.forEach(el=>{
    const id=ensureBlockId(el);
    const item=document.createElement('div');
    item.className='abl-item';
    item.dataset.blockId=id;
    const text=(el.textContent||'').trim().replace(/\s+/g,' ').slice(0,45);
    const tag=el.tagName.toLowerCase();
    const cls=Array.from(el.classList).find(c=>['code-card','clearance-card','scp-card','item-card','priv-card','alert','section','table-wrap','acc','header','footer'].includes(c))||'';
    const icon=getBlockIcon(el);
    item.innerHTML=`<span class="abl-ico">${icon}</span><span class="abl-name">${text||tag}</span><span class="abl-type">${cls||tag}</span>`;
    if(state.selected.includes(el))item.classList.add('selected');
    item.addEventListener('click',e=>{
      if(e.shiftKey||e.ctrlKey||e.metaKey){if(state.selected.includes(el))removeSelection(el);else addSelection(el);}
      else{selectSingle(el);el.scrollIntoView({behavior:'smooth',block:'center'});}
    });
    list.appendChild(item);
  });
}
function getBlockIcon(el){
  if(el.matches('h2'))return'📌';if(el.matches('h3'))return'📎';if(el.matches('h4'))return'🔖';
  if(el.matches('p'))return'¶';if(el.matches('ul, ol'))return'☰';
  if(el.matches('.code-card'))return'🎴';if(el.matches('.clearance-card'))return'🎫';
  if(el.matches('.scp-card'))return'🧬';if(el.matches('.item-card'))return'📦';
  if(el.matches('.priv-card'))return'⭐';if(el.matches('.alert'))return'⚠';
  if(el.matches('.table-wrap'))return'📊';if(el.matches('.acc'))return'📂';
  if(el.matches('.header'))return'🎯';if(el.matches('.footer'))return'🏁';
  if(el.matches('.section'))return'📄';return'▪';
}

/* RESIZE */
function startResize(e,el,dir){
  e.preventDefault();e.stopPropagation();
  if(el.classList.contains('block-locked')){toast('Заблокировано','error');return;}
  const sx=e.clientX,sy=e.clientY;
  const r=el.getBoundingClientRect();
  const sw=r.width,sh=r.height;
  el.style.boxSizing='border-box';
  el.style.width=sw+'px';
  el.style.height=sh+'px';
  function onMove(ev){
    let dx=ev.clientX-sx,dy=ev.clientY-sy;
    let w=sw,h=sh;
    if(dir.includes('e'))w=Math.max(30,sw+dx);
    if(dir.includes('w'))w=Math.max(30,sw-dx);
    if(dir.includes('s'))h=Math.max(20,sh+dy);
    if(dir.includes('n'))h=Math.max(20,sh-dy);
    el.style.width=Math.round(w)+'px';
    el.style.height=Math.round(h)+'px';
  }
  function onUp(){document.removeEventListener('mousemove',onMove);document.removeEventListener('mouseup',onUp);pushHistory();updateSelectionUI();}
  document.addEventListener('mousemove',onMove);
  document.addEventListener('mouseup',onUp);
}

/* DRAG & DROP */
function startDrag(el){
  state.dragSrc=el;el.classList.add('block-dragging');
  function onMove(e){
    const t=document.elementFromPoint(e.clientX,e.clientY);
    const target=t&&t.closest('[data-editable-block]');
    qsa('.block-drop-target').forEach(x=>x.classList.remove('block-drop-target'));
    if(target&&target!==el)target.classList.add('block-drop-target');
  }
  function onUp(e){
    document.removeEventListener('mousemove',onMove);
    document.removeEventListener('mouseup',onUp);
    el.classList.remove('block-dragging');
    qsa('.block-drop-target').forEach(x=>x.classList.remove('block-drop-target'));
    const t=document.elementFromPoint(e.clientX,e.clientY);
    const target=t&&t.closest('[data-editable-block]');
    if(target&&target!==el&&!target.contains(el)){
      const r=target.getBoundingClientRect();
      const after=e.clientY>r.top+r.height/2;
      target.parentNode.insertBefore(el,after?target.nextSibling:target);
      pushHistory();buildBlockList();
    }
    state.dragSrc=null;
  }
  document.addEventListener('mousemove',onMove);
  document.addEventListener('mouseup',onUp);
}

/* ДЕЙСТВИЯ */
function deleteBlock(el){if(!el||el.classList.contains('block-locked')){toast('Заблокировано','error');return;}el.remove();removeSelection(el);pushHistory();buildBlockList();toast('Удалено');}
function duplicateBlock(el){
  if(!el)return;
  const clone=el.cloneNode(true);
  clone.querySelectorAll('.block-toolbar, .resize-handle').forEach(x=>x.remove());
  clone.classList.remove('block-selected','block-locked','block-hidden');
  clone.removeAttribute('data-editable-block');
  clone.removeAttribute('data-block-id');
  el.parentNode.insertBefore(clone,el.nextSibling);
  setTimeout(()=>{clone.setAttribute('data-editable-block','1');attachBlockUI(clone);buildBlockList();},20);
  pushHistory();toast('Продублировано');
}
function moveBlock(el,dir){
  if(dir==='up'&&el.previousElementSibling)el.parentNode.insertBefore(el,el.previousElementSibling);
  else if(dir==='down'&&el.nextElementSibling)el.parentNode.insertBefore(el.nextElementSibling,el);
  pushHistory();buildBlockList();
}
function toggleLock(el){el.classList.toggle('block-locked');pushHistory();}
function toggleHide(el){el.classList.toggle('block-hidden');pushHistory();}

/* КОПИРОВАНИЕ */
function copySize(){
  if(state.selected.length!==1){toast('Нужен 1 блок','error');return;}
  const el=state.selected[0];
  state.clipboardSize={width:el.style.width||'',height:el.style.height||'',minWidth:el.style.minWidth||'',maxWidth:el.style.maxWidth||'',minHeight:el.style.minHeight||'',maxHeight:el.style.maxHeight||''};
  toast('📋 Размер скопирован');
}
function pasteSize(){
  if(!state.clipboardSize){toast('Буфер пуст','error');return;}
  if(!state.selected.length){toast('Ничего не выделено','error');return;}
  state.selected.forEach(el=>{Object.entries(state.clipboardSize).forEach(([k,v])=>{if(v)el.style[k]=v;});});
  pushHistory();toast(`📥 Размер применён к ${state.selected.length}`);
}
function copyStyle(){if(state.selected.length!==1){toast('Нужен 1 блок','error');return;}state.clipboardStyle=state.selected[0].style.cssText;toast('📋 Стили скопированы');}
function pasteStyle(){if(!state.clipboardStyle){toast('Буфер пуст','error');return;}state.selected.forEach(el=>el.style.cssText+=';'+state.clipboardStyle);pushHistory();toast(`📥 Стили применены к ${state.selected.length}`);}
function copyFull(){if(state.selected.length!==1){toast('Нужен 1 блок','error');return;}state.clipboardFull=state.selected[0].cloneNode(true);toast('📋 Блок скопирован');}
function applyToAll(){if(state.selected.length<2){toast('Нужно 2+ блока','error');return;}const cssText=state.selected[0].style.cssText;state.selected.slice(1).forEach(el=>{el.style.cssText+=';'+cssText;});pushHistory();toast(`🌐 Применено к ${state.selected.length} блокам`);}

/* ПАНЕЛЬ СВОЙСТВ */
function fillPropsPanel(el){
  const cs=el.style;
  const wM=(cs.width||'').match(/^([\d.]+)(%|px|vw|vh|em|rem)?$/);
  if(wM){qs('#apW').value=wM[1];qs('#apWUnit').value=wM[2]||'%';}else{qs('#apW').value='';qs('#apWUnit').value='%';}
  const hM=(cs.height||'').match(/^([\d.]+)(%|px|vw|vh|em|rem)?$/);
  if(hM){qs('#apH').value=hM[1];qs('#apHUnit').value=hM[2]||'px';}else{qs('#apH').value='';qs('#apHUnit').value='auto';}
  qs('#apMinW').value=cs.minWidth||'';qs('#apMaxW').value=cs.maxWidth||'';
  qs('#apMinH').value=cs.minHeight||'';qs('#apMaxH').value=cs.maxHeight||'';
  qs('#apPadAll').value=cs.padding||'';qs('#apPadTop').value=cs.paddingTop||'';
  qs('#apPadRight').value=cs.paddingRight||'';qs('#apPadBottom').value=cs.paddingBottom||'';qs('#apPadLeft').value=cs.paddingLeft||'';
  qs('#apMarAll').value=cs.margin||'';qs('#apMarTop').value=cs.marginTop||'';
  qs('#apMarRight').value=cs.marginRight||'';qs('#apMarBottom').value=cs.marginBottom||'';qs('#apMarLeft').value=cs.marginLeft||'';
  qs('#apBorW').value=cs.borderWidth||'';qs('#apBorS').value=cs.borderStyle||'';qs('#apBorC').value=cs.borderColor||'';
  qs('#apRadius').value=cs.borderRadius||'';
  qs('#apBg').value=cs.background||cs.backgroundColor||'';
  qs('#apGrad').value=(cs.backgroundImage||'').includes('gradient')?cs.backgroundImage:'';
  qs('#apBgImg').value=(cs.backgroundImage||'').includes('url')?cs.backgroundImage:'';
  qs('#apBgSize').value=cs.backgroundSize||'';
  qs('#apTextC').value=cs.color||'';qs('#apShadow').value=cs.boxShadow||'';
  qs('#apFilter').value=cs.filter||'';qs('#apTransform').value=cs.transform||'';
  qs('#apFontFamily').value=cs.fontFamily||'';qs('#apFontSize').value=cs.fontSize||'';
  qs('#apFontWeight').value=cs.fontWeight||'';qs('#apFontStyle').value=cs.fontStyle||'';
  qs('#apLineHeight').value=cs.lineHeight||'';qs('#apLetterSpacing').value=cs.letterSpacing||'';
  qs('#apTextIndent').value=cs.textIndent||'';qs('#apTextDecor').value=cs.textDecoration||'';
  qs('#apTextTransform').value=cs.textTransform||'';
  qs('#apDisplay').value=cs.display||'';qs('#apFlexDir').value=cs.flexDirection||'';
  qs('#apJustify').value=cs.justifyContent||'';qs('#apAlignItems').value=cs.alignItems||'';
  qs('#apGap').value=cs.gap||'';qs('#apGridCols').value=cs.gridTemplateColumns||'';
  qs('#apPosition').value=cs.position||'';qs('#apTop').value=cs.top||'';
  qs('#apLeft').value=cs.left||'';qs('#apRight').value=cs.right||'';qs('#apBottom').value=cs.bottom||'';
  qs('#apZindex').value=cs.zIndex||'';
  const op=cs.opacity?Math.round(parseFloat(cs.opacity)*100):100;
  qs('#apOpacityR').value=op;qs('#apOpacityV').textContent=op+'%';
  const bgHex=rgbToHex(cs.backgroundColor);if(bgHex)qs('#apBgColor').value=bgHex;
  const colHex=rgbToHex(cs.color);if(colHex)qs('#apTextColor').value=colHex;
  const borHex=rgbToHex(cs.borderColor);if(borHex)qs('#apBorColor').value=borHex;
}
function clearPropsPanel(){
  ['apW','apH','apMinW','apMaxW','apMinH','apMaxH','apPadAll','apPadTop','apPadRight','apPadBottom','apPadLeft','apMarAll','apMarTop','apMarRight','apMarBottom','apMarLeft','apBorW','apBorC','apRadius','apBg','apGrad','apBgImg','apTextC','apShadow','apFilter','apTransform','apFontSize','apLineHeight','apLetterSpacing','apTextIndent','apGap','apGridCols','apTop','apLeft','apRight','apBottom','apZindex'].forEach(id=>{const e=qs('#'+id);if(e)e.value='';});
  ['apWUnit','apHUnit','apBorS','apBgSize','apFontFamily','apFontWeight','apFontStyle','apTextDecor','apTextTransform','apDisplay','apFlexDir','apJustify','apAlignItems','apPosition'].forEach(id=>{const e=qs('#'+id);if(e)e.value='';});
  qs('#apOpacityR').value=100;qs('#apOpacityV').textContent='100%';
}
function rgbToHex(c){if(!c||c==='transparent')return'';if(c.startsWith('#'))return c;const m=c.match(/\d+/g);if(!m||m.length<3)return'';return'#'+m.slice(0,3).map(x=>(+x).toString(16).padStart(2,'0')).join('');}

function bindProp(id,cssProp){
  const el=qs('#'+id);
  if(!el)return;
  const evt=el.type==='color'||el.tagName==='SELECT'?'change':'input';
  el.addEventListener(evt,()=>{
    let v=el.value;
    state.selected.forEach(block=>{if(v==='')block.style.removeProperty(cssProp);else block.style.setProperty(cssProp,v);});
  });
  el.addEventListener('change',()=>pushHistory());
}
function applySize(){
  const w=qs('#apW').value,wu=qs('#apWUnit').value;
  const h=qs('#apH').value,hu=qs('#apHUnit').value;
  state.selected.forEach(el=>{
    if(w)el.style.width=w+wu;else if(wu==='auto')el.style.width='auto';
    if(h)el.style.height=h+hu;else if(hu==='auto')el.style.height='auto';
  });
  pushHistory();
}
qs('#apW').addEventListener('input',applySize);qs('#apH').addEventListener('input',applySize);
qs('#apWUnit').addEventListener('change',applySize);qs('#apHUnit').addEventListener('change',applySize);
bindProp('apMinW','min-width');bindProp('apMaxW','max-width');
bindProp('apMinH','min-height');bindProp('apMaxH','max-height');
bindProp('apPadAll','padding');bindProp('apPadTop','padding-top');
bindProp('apPadRight','padding-right');bindProp('apPadBottom','padding-bottom');bindProp('apPadLeft','padding-left');
bindProp('apMarAll','margin');bindProp('apMarTop','margin-top');
bindProp('apMarRight','margin-right');bindProp('apMarBottom','margin-bottom');bindProp('apMarLeft','margin-left');
bindProp('apBorW','border-width');bindProp('apBorS','border-style');bindProp('apBorC','border-color');bindProp('apBorColor','border-color');
bindProp('apRadius','border-radius');bindProp('apBg','background');bindProp('apBgColor','background-color');
bindProp('apGrad','background-image');bindProp('apBgImg','background-image');bindProp('apBgSize','background-size');
bindProp('apTextC','color');bindProp('apTextColor','color');bindProp('apShadow','box-shadow');
bindProp('apFilter','filter');bindProp('apTransform','transform');
bindProp('apFontFamily','font-family');bindProp('apFontSize','font-size');
bindProp('apFontWeight','font-weight');bindProp('apFontStyle','font-style');
bindProp('apLineHeight','line-height');bindProp('apLetterSpacing','letter-spacing');
bindProp('apTextIndent','text-indent');bindProp('apTextDecor','text-decoration');bindProp('apTextTransform','text-transform');
bindProp('apDisplay','display');bindProp('apFlexDir','flex-direction');
bindProp('apJustify','justify-content');bindProp('apAlignItems','align-items');
bindProp('apGap','gap');bindProp('apGridCols','grid-template-columns');
bindProp('apPosition','position');bindProp('apTop','top');bindProp('apLeft','left');
bindProp('apRight','right');bindProp('apBottom','bottom');bindProp('apZindex','z-index');

qs('#apOpacityR').addEventListener('input',e=>{const v=e.target.value/100;qs('#apOpacityV').textContent=e.target.value+'%';state.selected.forEach(el=>el.style.opacity=v);});
qs('#apOpacityR').addEventListener('change',pushHistory);
qs('#apGlow').addEventListener('input',e=>{const v=e.target.value;state.selected.forEach(el=>{if(v)el.style.boxShadow=(el.style.boxShadow||'')+', '+v;});});

qsa('[data-preset]').forEach(btn=>{
  btn.addEventListener('click',()=>{
    const w=btn.dataset.preset;
    if(!state.selected.length){toast('Ничего не выделено','error');return;}
    state.selected.forEach(el=>el.style.width=w);
    qs('#apW').value=parseFloat(w)||'';
    qs('#apWUnit').value=w.includes('%')?'%':w.includes('px')?'px':'auto';
    pushHistory();toast('Ширина '+w);
  });
});
qsa('[data-align]').forEach(btn=>{
  btn.addEventListener('click',()=>{state.selected.forEach(el=>el.style.textAlign=btn.dataset.align);pushHistory();});
});
qsa('.ap-action[data-act]').forEach(btn=>{
  btn.addEventListener('click',()=>{
    const act=btn.dataset.act;
    const sel=state.selected;
    if(act==='up')sel.forEach(el=>moveBlock(el,'up'));
    else if(act==='down')sel.forEach(el=>moveBlock(el,'down'));
    else if(act==='dup')sel.slice().forEach(el=>duplicateBlock(el));
    else if(act==='hide')sel.forEach(el=>toggleHide(el));
    else if(act==='lock')sel.forEach(el=>toggleLock(el));
    else if(act==='copyFull')copyFull();
    else if(act==='copySize')copySize();
    else if(act==='pasteSize')pasteSize();
    else if(act==='copyStyle')copyStyle();
    else if(act==='pasteStyle')pasteStyle();
    else if(act==='applyAll')applyToAll();
    else if(act==='reset'){sel.forEach(el=>el.removeAttribute('style'));pushHistory();updateSelectionUI();}
    else if(act==='delete')sel.slice().forEach(el=>deleteBlock(el));
  });
});
qsa('.ap-tab').forEach(tab=>{
  tab.addEventListener('click',()=>{
    qsa('.ap-tab').forEach(t=>t.classList.toggle('active',t===tab));
    qsa('.ap-pane').forEach(p=>p.classList.toggle('active',p.dataset.pane===tab.dataset.tab));
  });
});
qsa('.reset-prop[data-reset]').forEach(btn=>{
  btn.addEventListener('click',()=>{
    const props=btn.dataset.reset.split(',');
    state.selected.forEach(el=>props.forEach(p=>el.style.removeProperty(p.trim())));
    pushHistory();updateSelectionUI();
  });
});

/* РЕЖИМ ТЕКСТА */
function setEditMode(on){
  state.editMode=on;
  document.body.classList.toggle('edit-mode',on);
  qsa(TEXT_SELECTOR,qs('.main-inner')).forEach(el=>{
    if(on){el.setAttribute('contenteditable','true');el.setAttribute('spellcheck','false');}
    else el.removeAttribute('contenteditable');
  });
  qs('#tbEditText').classList.toggle('active',on);
}
function toggleBlockEditMode(el){
  qsa(TEXT_SELECTOR,el).forEach(t=>{t.setAttribute('contenteditable','true');t.focus();});
  toast('Правка текста включена');
}

/* КОНТЕКСТНОЕ МЕНЮ */
const adminCtx=qs('#adminCtx');
function openContextMenu(x,y){
  adminCtx.style.left=Math.min(x,window.innerWidth-240)+'px';
  adminCtx.style.top=Math.min(y,window.innerHeight-340)+'px';
  adminCtx.classList.add('show');
}
function closeContextMenu(){adminCtx.classList.remove('show');}
adminCtx.addEventListener('click',e=>{
  const item=e.target.closest('.ctx-item');
  if(!item)return;
  const a=item.dataset.action;
  const sel=state.selected;
  closeContextMenu();
  if(a==='edit'&&sel[0])toggleBlockEditMode(sel[0]);
  else if(a==='rename'&&sel[0]){const n=prompt('Имя блока:',state.blockNames[sel[0].dataset.blockId]||'');if(n!==null){state.blockNames[sel[0].dataset.blockId]=n;buildBlockList();}}
  else if(a==='dup')sel.slice().forEach(el=>duplicateBlock(el));
  else if(a==='up')sel.forEach(el=>moveBlock(el,'up'));
  else if(a==='down')sel.forEach(el=>moveBlock(el,'down'));
  else if(a==='copySize')copySize();
  else if(a==='pasteSize')pasteSize();
  else if(a==='copyStyle')copyStyle();
  else if(a==='pasteStyle')pasteStyle();
  else if(a==='applyAll')applyToAll();
  else if(a==='hide')sel.forEach(el=>toggleHide(el));
  else if(a==='lock')sel.forEach(el=>toggleLock(el));
  else if(a==='reset'){sel.forEach(el=>el.removeAttribute('style'));pushHistory();}
  else if(a==='delete')sel.slice().forEach(el=>deleteBlock(el));
});
document.addEventListener('click',e=>{if(!e.target.closest('#adminCtx'))closeContextMenu();});

/* ВЫБОР */
function selectAllBlocks(){clearSelection();qsa('[data-editable-block]',qs('.main-inner')).forEach(el=>addSelection(el));toast('Выделено всё');}
function selectNone(){clearSelection();toast('Снято');}
function invertSelection(){qsa('[data-editable-block]',qs('.main-inner')).forEach(el=>{if(state.selected.includes(el))removeSelection(el);else addSelection(el);});toast('Инвертировано');}

/* НИЖНЯЯ ПАНЕЛЬ */
qsa('.ab-preset[data-w]').forEach(btn=>{
  btn.addEventListener('click',()=>{
    if(!state.selected.length){toast('Ничего не выделено','error');return;}
    const w=btn.dataset.w;
    state.selected.forEach(el=>el.style.width=w);
    qsa('.ab-preset[data-w]').forEach(b=>b.classList.toggle('active',b===btn));
    pushHistory();toast('Ширина: '+w);
  });
});
qsa('.ab-unit[data-unit]').forEach(btn=>{btn.addEventListener('click',()=>{state.unitW=btn.dataset.unit;qsa('.ab-unit[data-unit]').forEach(b=>b.classList.toggle('active',b===btn));});});
qsa('.ab-unit[data-hunit]').forEach(btn=>{btn.addEventListener('click',()=>{state.unitH=btn.dataset.hunit;qsa('.ab-unit[data-hunit]').forEach(b=>b.classList.toggle('active',b===btn));});});
qs('#abApplyW').addEventListener('click',()=>{
  const v=qs('#abWidthCustom').value;
  if(!v)return;
  if(!state.selected.length){toast('Ничего не выделено','error');return;}
  const w=v+state.unitW;
  state.selected.forEach(el=>el.style.width=w);
  pushHistory();toast('Ширина: '+w);
});
qs('#abApplyH').addEventListener('click',()=>{
  const v=qs('#abHeightCustom').value;
  if(!v)return;
  if(!state.selected.length){toast('Ничего не выделено','error');return;}
  const h=v+state.unitH;
  state.selected.forEach(el=>el.style.height=h);
  pushHistory();toast('Высота: '+h);
});
qs('#abAlignLeft').addEventListener('click',()=>{state.selected.forEach(el=>{el.style.marginLeft='0';el.style.marginRight='auto';});pushHistory();});
qs('#abAlignCenter').addEventListener('click',()=>{state.selected.forEach(el=>{el.style.marginLeft='auto';el.style.marginRight='auto';});pushHistory();});
qs('#abAlignRight').addEventListener('click',()=>{state.selected.forEach(el=>{el.style.marginLeft='auto';el.style.marginRight='0';});pushHistory();});
qs('#abEqualW').addEventListener('click',()=>{
  if(state.selected.length<2){toast('Нужно 2+','error');return;}
  let max=0,maxVal='';
  state.selected.forEach(el=>{const w=el.getBoundingClientRect().width;if(w>max){max=w;maxVal=w+'px';}});
  state.selected.forEach(el=>el.style.width=maxVal);
  pushHistory();toast('Уравнено: '+maxVal);
});
qs('#abEqualH').addEventListener('click',()=>{
  if(state.selected.length<2){toast('Нужно 2+','error');return;}
  let max=0,maxVal='';
  state.selected.forEach(el=>{const h=el.getBoundingClientRect().height;if(h>max){max=h;maxVal=h+'px';}});
  state.selected.forEach(el=>el.style.height=maxVal);
  pushHistory();toast('Уравнено: '+maxVal);
});
qs('#abMatchFirst').addEventListener('click',()=>{
  if(state.selected.length<2){toast('Нужно 2+','error');return;}
  const src=state.selected[0];
  const w=src.style.width,h=src.style.height;
  state.selected.slice(1).forEach(el=>{if(w)el.style.width=w;if(h)el.style.height=h;});
  pushHistory();toast('Размер первого применён');
});
qs('#abResetSize').addEventListener('click',()=>{
  state.selected.forEach(el=>{
    ['width','height','min-width','max-width','min-height','max-height'].forEach(p=>el.style.removeProperty(p));
  });
  pushHistory();toast('Размер сброшен');
});

/* ВЕРХНИЙ ТУЛБАР */
qs('#tbBlocks').addEventListener('click',()=>{
  state.blocksPanel=!state.blocksPanel;
  qs('#adminBlocks').classList.toggle('show',state.blocksPanel);
  document.body.classList.toggle('blocks-open',state.blocksPanel);
  qs('#tbBlocks').classList.toggle('active',state.blocksPanel);
  if(state.blocksPanel)buildBlockList();
});
qs('#tbProps').addEventListener('click',()=>{
  state.propsPanel=!state.propsPanel;
  qs('#adminProps').classList.toggle('show',state.propsPanel);
  document.body.classList.toggle('props-open',state.propsPanel);
  qs('#tbProps').classList.toggle('active',state.propsPanel);
});
qs('#tbTheme').addEventListener('click',()=>{
  state.theme=state.theme==='dark'?'light':'dark';
  html.dataset.theme=state.theme;
  qs('#tbTheme').innerHTML=(state.theme==='dark'?'🌙':'☀')+' Тема';
  pushHistory();
});
qs('#tbColorPrev').addEventListener('click',()=>{
  const i=ALL_COLORS.indexOf(state.accent);
  state.accent=ALL_COLORS[(i-1+ALL_COLORS.length)%ALL_COLORS.length];
  html.dataset.accent=state.accent;
  toast('Цвет: '+state.accent.toUpperCase());pushHistory();
});
qs('#tbColorNext').addEventListener('click',()=>{
  const i=ALL_COLORS.indexOf(state.accent);
  state.accent=ALL_COLORS[(i+1)%ALL_COLORS.length];
  html.dataset.accent=state.accent;
  toast('Цвет: '+state.accent.toUpperCase());pushHistory();
});
qs('#tbFont').addEventListener('click',()=>{
  const i=ALL_FONTS.findIndex(f=>f.id===state.font);
  const next=ALL_FONTS[(i+1)%ALL_FONTS.length];
  state.font=next.id;html.dataset.font=next.id;
  qs('#tbFontLbl').textContent=next.lbl;
  pushHistory();
});
qs('#tbBg').addEventListener('click',()=>{
  const i=ALL_BGS.indexOf(state.bgfx);
  const next=ALL_BGS[(i+1)%ALL_BGS.length];
  state.bgfx=next;html.dataset.bgfx=next;
  qs('#tbBgLbl').textContent=next==='default'?'Пусто':next;
  pushHistory();
});
qs('#tbEditText').addEventListener('click',()=>setEditMode(!state.editMode));
qs('#tbMoveMode').addEventListener('click',()=>{
  state.moveMode=!state.moveMode;
  qs('#tbMoveMode').classList.toggle('active',state.moveMode);
  qsa('[data-editable-block]').forEach(el=>{
    if(state.moveMode)el.setAttribute('draggable','true');else el.removeAttribute('draggable');
  });
  toast(state.moveMode?'Режим переноса ВКЛ':'Режим переноса ВЫКЛ');
});
qs('#tbUndo').addEventListener('click',undo);
qs('#tbRedo').addEventListener('click',redo);
qs('#tbSelAll').addEventListener('click',selectAllBlocks);
qs('#tbSelNone').addEventListener('click',selectNone);
qs('#tbSelInv').addEventListener('click',invertSelection);
qs('#tbDup').addEventListener('click',()=>state.selected.slice().forEach(el=>duplicateBlock(el)));
qs('#tbDelete').addEventListener('click',()=>state.selected.slice().forEach(el=>deleteBlock(el)));
qs('#tbLock').addEventListener('click',()=>state.selected.forEach(el=>toggleLock(el)));
qs('#tbSave').addEventListener('click',saveHTML);
qs('#tbExit').addEventListener('click',deactivateAdmin);
qs('#ablClose').addEventListener('click',()=>{state.blocksPanel=false;qs('#adminBlocks').classList.remove('show');document.body.classList.remove('blocks-open');qs('#tbBlocks').classList.remove('active');});
qs('#apClose').addEventListener('click',()=>{state.propsPanel=false;qs('#adminProps').classList.remove('show');document.body.classList.remove('props-open');qs('#tbProps').classList.remove('active');});
qs('#ablSearch').addEventListener('input',e=>{
  const q=e.target.value.toLowerCase();
  qsa('.abl-item').forEach(item=>{item.style.display=item.textContent.toLowerCase().includes(q)?'':'none';});
});
qsa('.abl-action[data-select]').forEach(btn=>{
  btn.addEventListener('click',()=>{
    const mode=btn.dataset.select;
    if(mode==='all')selectAllBlocks();
    else if(mode==='none')selectNone();
    else if(mode==='invert')invertSelection();
    else if(mode==='visible'){clearSelection();qsa('[data-editable-block]:not(.block-hidden)',qs('.main-inner')).forEach(el=>addSelection(el));}
    else if(mode==='sameType'){
      if(!state.selected.length){toast('Выдели блок сначала','error');return;}
      const first=state.selected[0];
      const cls=Array.from(first.classList).find(c=>c.includes('card')||c.includes('alert')||c.includes('section'));
      const tag=first.tagName;
      qsa('[data-editable-block]',qs('.main-inner')).forEach(el=>{
        if(cls&&el.classList.contains(cls))addSelection(el);
        else if(!cls&&el.tagName===tag)addSelection(el);
      });
    }
    else if(mode==='h2')qsa('h2[data-editable-block]').forEach(el=>addSelection(el));
    else if(mode==='h3')qsa('h3[data-editable-block]').forEach(el=>addSelection(el));
    else if(mode==='cards')qsa('.code-card[data-editable-block], .clearance-card[data-editable-block], .scp-card[data-editable-block], .item-card[data-editable-block], .priv-card[data-editable-block]').forEach(el=>addSelection(el));
    else if(mode==='tables')qsa('.table-wrap[data-editable-block]').forEach(el=>addSelection(el));
    else if(mode==='alerts')qsa('.alert[data-editable-block]').forEach(el=>addSelection(el));
    else if(mode==='grids')qsa('.code-grid[data-editable-block], .clearance-grid[data-editable-block], .two-col-grid[data-editable-block]').forEach(el=>addSelection(el));
    else if(mode==='acc')qsa('.acc[data-editable-block]').forEach(el=>addSelection(el));
  });
});

/* ПЛАШКА */
qs('#selClear').addEventListener('click',clearSelection);
qs('#selProps').addEventListener('click',()=>{if(!state.propsPanel)qs('#tbProps').click();});
qs('#selApplyFirst').addEventListener('click',()=>qs('#abMatchFirst').click());

/* UNDO / REDO */
function pushHistory(){
  const clone=qs('.main-inner').cloneNode(true);
  clone.querySelectorAll('.block-toolbar, .resize-handle').forEach(el=>el.remove());
  clone.querySelectorAll('[data-editable-block]').forEach(el=>el.removeAttribute('data-editable-block'));
  clone.querySelectorAll('.block-selected, .block-hidden, .block-locked, .block-dragging, .block-drop-target').forEach(el=>{el.classList.remove('block-selected','block-hidden','block-locked','block-dragging','block-drop-target');});
  clone.querySelectorAll('[contenteditable]').forEach(el=>el.removeAttribute('contenteditable'));
  state.history.stack=state.history.stack.slice(0,state.history.idx+1);
  state.history.stack.push(clone.innerHTML);
  if(state.history.stack.length>state.history.max)state.history.stack.shift();
  state.history.idx=state.history.stack.length-1;
  saveLocal();
}
function undo(){if(state.history.idx<=0){toast('Нечего отменять');return;}state.history.idx--;applyHistory();}
function redo(){if(state.history.idx>=state.history.stack.length-1){toast('Нечего возвращать');return;}state.history.idx++;applyHistory();}
function applyHistory(){
  qs('.main-inner').innerHTML=state.history.stack[state.history.idx];
  clearSelection();
  setTimeout(()=>{
    markEditable();bindBlockEvents();buildBlockList();
    qsa('.acc-head').forEach(h=>h.onclick=()=>h.parentElement.classList.toggle('open'));
    if(state.editMode)setEditMode(true);
  },20);
}

/* СОХРАНЕНИЕ HTML */
function saveHTML(){
  const clone=document.documentElement.cloneNode(true);
  clone.querySelectorAll('#adminToolbar, #adminBlocks, #adminProps, #adminCtx, #selInfo, #modalBackdrop, #adminOpenBtn, #searchResults, #adminBottom').forEach(el=>el.remove());
  clone.querySelectorAll('.block-toolbar, .resize-handle').forEach(el=>el.remove());
  clone.querySelectorAll('[data-editable-block]').forEach(el=>el.removeAttribute('data-editable-block'));
  clone.querySelectorAll('[data-block-id]').forEach(el=>el.removeAttribute('data-block-id'));
  clone.querySelectorAll('.block-selected, .block-hidden, .block-locked, .block-dragging, .block-drop-target').forEach(el=>{el.classList.remove('block-selected','block-hidden','block-locked','block-dragging','block-drop-target');});
  clone.querySelectorAll('[contenteditable]').forEach(el=>el.removeAttribute('contenteditable'));
  clone.querySelectorAll('[draggable]').forEach(el=>el.removeAttribute('draggable'));
  clone.querySelectorAll('#watermark-overlay, #layer-back, #layer-middle').forEach(el=>el.innerHTML='');
  Array.from(clone.attributes).forEach(a=>{if(!['lang','data-theme','data-accent','data-font','data-bgfx'].includes(a.name))clone.removeAttribute(a.name);});
  const bodyEl=clone.querySelector('body');
  bodyEl.classList.remove('admin-mode','props-open','blocks-open','edit-mode','move-mode');
  const doc='<!DOCTYPE html>\n'+clone.outerHTML;
  const blob=new Blob([doc],{type:'text/html;charset=utf-8'});
  const url=URL.createObjectURL(blob);
  const a=document.createElement('a');
  a.href=url;a.download='index.html';
  document.body.appendChild(a);a.click();document.body.removeChild(a);
  URL.revokeObjectURL(url);
  toast('✅ index.html скачан — залей в репозиторий');
}

/* LOCALSTORAGE */
function saveLocal(){
  try{localStorage.setItem(STORAGE_KEY,JSON.stringify({accent:state.accent,theme:state.theme,font:state.font,bgfx:state.bgfx}));}catch(e){}
}
function loadLocal(){
  try{
    const raw=localStorage.getItem(STORAGE_KEY);
    if(!raw)return;
    const d=JSON.parse(raw);
    if(d.accent){state.accent=d.accent;html.dataset.accent=d.accent;}
    if(d.theme){state.theme=d.theme;html.dataset.theme=d.theme;}
    if(d.font){state.font=d.font;html.dataset.font=d.font;}
    if(d.bgfx){state.bgfx=d.bgfx;html.dataset.bgfx=d.bgfx;}
  }catch(e){}
}
function applyStateToUI(){
  qs('#tbTheme').innerHTML=(state.theme==='dark'?'🌙':'☀')+' Тема';
  qs('#tbFontLbl').textContent=(ALL_FONTS.find(f=>f.id===state.font)||{}).lbl||'Mono';
  qs('#tbBgLbl').textContent=state.bgfx==='default'?'Пусто':state.bgfx;
}

/* ГЛОБАЛЬНЫЕ СОБЫТИЯ */
let globalBound=false;
function bindGlobalEvents(){
  if(globalBound)return;
  globalBound=true;
  document.addEventListener('mousedown',e=>{
    if(e.target.closest('[data-editable-block], .admin-toolbar, .admin-blocks, .admin-props, .admin-ctx, .sel-info, .modal-backdrop, .admin-bottom'))return;
    if(e.target.closest('a, button, input, select, textarea'))return;
    if(state.editMode&&e.target.isContentEditable)return;
    clearSelection();
  });
  document.addEventListener('keydown',e=>{
    if(!document.body.classList.contains('admin-mode'))return;
    const inField=e.target.isContentEditable||['INPUT','TEXTAREA','SELECT'].includes(e.target.tagName);
    if(e.ctrlKey&&!e.shiftKey&&e.key.toLowerCase()==='z'&&!inField){e.preventDefault();undo();return;}
    if((e.ctrlKey&&e.key.toLowerCase()==='y'&&!inField)||(e.ctrlKey&&e.shiftKey&&e.key.toLowerCase()==='z'&&!inField)){e.preventDefault();redo();return;}
    if(inField){if(e.key==='Escape')e.target.blur();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='a'){e.preventDefault();selectAllBlocks();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='i'){e.preventDefault();invertSelection();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='d'){e.preventDefault();state.selected.slice().forEach(el=>duplicateBlock(el));return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='c'){e.preventDefault();copySize();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='v'){e.preventDefault();pasteSize();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='e'){e.preventDefault();setEditMode(!state.editMode);return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='m'){e.preventDefault();qs('#tbMoveMode').click();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='b'){e.preventDefault();qs('#tbBlocks').click();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='p'){e.preventDefault();qs('#tbProps').click();return;}
    if(e.ctrlKey&&e.key.toLowerCase()==='s'){e.preventDefault();saveHTML();return;}
    if(e.key==='Delete'&&state.selected.length){e.preventDefault();state.selected.slice().forEach(el=>deleteBlock(el));return;}
    if(e.key==='Escape'){if(document.activeElement.isContentEditable)document.activeElement.blur();else clearSelection();return;}
    if(['ArrowUp','ArrowDown','ArrowLeft','ArrowRight'].includes(e.key)&&state.selected.length){
      e.preventDefault();
      const step=e.shiftKey?20:5;
      state.selected.forEach(el=>{
        const r=el.getBoundingClientRect();
        const cw=r.width,ch=r.height;
        if(e.key==='ArrowRight')el.style.width=(cw+step)+'px';
        if(e.key==='ArrowLeft')el.style.width=Math.max(30,cw-step)+'px';
        if(e.key==='ArrowDown')el.style.height=(ch+step)+'px';
        if(e.key==='ArrowUp')el.style.height=Math.max(20,ch-step)+'px';
      });
      pushHistory();
    }
  });
}

/* БАЗОВЫЙ САЙТ */
const navLinks=qsa('.nav-sub a');
const sections=qsa('h2[id], h3[id]');
function updateActiveLink(){
  let cur='';
  sections.forEach(s=>{if(window.scrollY>=s.offsetTop-150)cur=s.getAttribute('id');});
  navLinks.forEach(l=>l.classList.toggle('active',l.getAttribute('href')==='#'+cur));
}
const progressBar=qs('#scrollProgress');
const toTop=qs('#toTop');
function onScroll(){
  const doc=document.documentElement;
  const sc=doc.scrollTop;
  const max=doc.scrollHeight-doc.clientHeight;
  progressBar.style.width=(max>0?sc/max*100:0)+'%';
  toTop.classList.toggle('show',sc>400);
  updateActiveLink();
}
let ticking=false;
window.addEventListener('scroll',()=>{if(!ticking){requestAnimationFrame(()=>{onScroll();ticking=false;});ticking=true;}},{passive:true});
toTop.addEventListener('click',()=>window.scrollTo({top:0,behavior:'smooth'}));
(function(){
  const items=qsa('.reveal');
  if(!('IntersectionObserver' in window)){items.forEach(i=>i.classList.add('in'));return;}
  const obs=new IntersectionObserver(entries=>{
    entries.forEach(en=>{if(!en.isIntersecting)return;en.target.classList.add('in');obs.unobserve(en.target);});
  },{threshold:0.1,rootMargin:'0px 0px -60px 0px'});
  items.forEach(i=>obs.observe(i));
})();
qsa('.acc-head').forEach(h=>h.addEventListener('click',()=>h.parentElement.classList.toggle('open')));
(function(){
  const ov=qs('#watermark-overlay');
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
  const b=qs('#layer-back'),m=qs('#layer-middle');
  const bt='MV.PROJECT  '.repeat(4);
  const mt='SCP FOUNDATION  '.repeat(3);
  let bh='',mh='';
  for(let i=0;i<80;i++){bh+='<div class="parallax-line">'+bt+'</div>';mh+='<div class="parallax-line">'+mt+'</div>';}
  b.innerHTML=bh;m.innerHTML=mh;
  let cb=0,cm=0;
  (function loop(){
    const sc=window.scrollY;
    cb+=(sc*.15-cb)*.08;
    cm+=(sc*-.10-cm)*.08;
    b.style.transform='translateY('+(-cb)+'px)';
    m.style.transform='translateY('+(-cm)+'px)';
    requestAnimationFrame(loop);
  })();
})();
(function(){
  const box=qs('#searchBox'),input=qs('#searchInput'),res=qs('#searchResults'),clr=qs('#searchClear');
  const idx=[];
  qsa('h2[id], h3[id], h4').forEach(el=>{
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
    if(!m.length){res.innerHTML='<div style="padding:20px;text-align:center;color:#666;font-size:.82em;">Ничего не найдено</div>';res.classList.add('show');return;}
    m.forEach(it=>{
      const d=document.createElement('div');
      d.className='search-item';
      const i=it.raw.toLowerCase().indexOf(q);
      const hi=esc(it.raw.slice(0,i))+'<mark>'+esc(it.raw.slice(i,i+q.length))+'</mark>'+esc(it.raw.slice(i+q.length));
      d.innerHTML='<span class="search-tag">'+(it.el.tagName==='H2'?'Раздел':'Подраздел')+'</span>'+hi;
      d.addEventListener('click',()=>{it.el.scrollIntoView({behavior:'smooth',block:'start'});res.classList.remove('show');input.blur();});
      res.appendChild(d);
    });
    res.classList.add('show');
  }
  input.addEventListener('input',()=>{box.classList.toggle('has-value',input.value.length>0);render(input.value);});
  clr.addEventListener('click',()=>{input.value='';box.classList.remove('has-value');res.classList.remove('show');input.focus();});
  document.addEventListener('click',e=>{if(!box.contains(e.target))res.classList.remove('show');});
})();

/* ИНИЦИАЛИЗАЦИЯ */
loadLocal();
applyStateToUI();
if(localStorage.getItem(STORAGE_KEY+'-unlocked')==='1'){
  setTimeout(activateAdmin,150);
}
setTimeout(()=>{pushHistory();onScroll();},300);
</script>
</body>
</html>
