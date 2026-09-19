<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MV.Project | Устав Фонда SCP</title>
<style>
  /* ============ БАЗА ============ */
  :root {
    --green: #00ff88;
    --green-dim: #00cc66;
    --green-deep: #009944;
    --red: #ff2a2a;
    --amber: #ffaa00;
    --bg: #050505;
    --panel: #0d0d0d;
    --panel-2: #0f0f0f;
    --border: #1a1a1a;
    --text: #b8b8b8;
    --ease: cubic-bezier(.22,.68,.32,1);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  html, body { width: 100%; min-height: 100%; }
  body {
    font-family: 'Consolas', 'Courier New', monospace;
    background: var(--bg); color: var(--text); line-height: 1.9;
    overflow-x: hidden;
  }

  ::selection { background: rgba(0,255,136,.3); color: #fff; }

  ::-webkit-scrollbar { width: 10px; }
  ::-webkit-scrollbar-track { background: #060606; }
  ::-webkit-scrollbar-thumb {
    background: linear-gradient(180deg, var(--green), var(--green-deep));
    border-radius: 5px; border: 2px solid #060606;
  }
  ::-webkit-scrollbar-thumb:hover { background: var(--green); }

  /* ============ ПРОГРЕСС ПРОКРУТКИ ============ */
  .scroll-progress {
    position: fixed; top: 0; left: 0; height: 3px; width: 0%;
    background: linear-gradient(90deg, var(--green), #00ccff, var(--green));
    background-size: 200% 100%;
    z-index: 2000; pointer-events: none;
    box-shadow: 0 0 14px rgba(0,255,136,.85);
    animation: gradientShift 3s linear infinite;
  }
  @keyframes gradientShift {
    0% { background-position: 0% 50%; }
    100% { background-position: 200% 50%; }
  }

  /* ============ ФОН ============ */
  .parallax-bg {
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100vh;
    pointer-events: none; z-index: 0; overflow: hidden;
  }
  .parallax-layer {
    position: absolute; top: 0; left: 0;
    width: 100%; user-select: none;
    pointer-events: none; will-change: transform;
  }
  .parallax-line {
    font-family: 'Consolas', 'Courier New', monospace;
    font-weight: bold; white-space: nowrap;
    letter-spacing: 25px; padding: 40px 0;
    text-align: center; user-select: none;
  }
  .parallax-layer.back .parallax-line { font-size: 5em; color: rgba(0, 255, 136, 0.028); }
  .parallax-layer.middle .parallax-line { font-size: 7em; color: rgba(255, 0, 0, 0.022); }
  .parallax-layer.front .parallax-line { font-size: 4em; color: rgba(255, 255, 255, 0.018); }

  /* ============ ВОДЯНЫЕ ЗНАКИ (отдельные MV.PROJECT, сетка с отступами) ============ */
  .watermark-overlay {
    position: fixed; top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none; z-index: 1; overflow: hidden;
  }
  .watermark-overlay .wm {
    position: absolute; color: rgba(0, 255, 136, 0.045);
    font-family: 'Consolas', monospace;
    font-weight: bold; font-size: 1.5em;
    letter-spacing: 5px; white-space: nowrap;
    transform: rotate(-35deg);
    user-select: none; pointer-events: none;
    text-transform: uppercase;
  }

  /* ============ SIDEBAR ============ */
  .sidebar {
    position: fixed; top: 0; left: 0;
    width: 290px; height: 100vh;
    background: linear-gradient(180deg, #080808, #060606);
    border-right: 2px solid var(--green);
    padding: 25px 0; overflow-y: auto; z-index: 1000;
    box-shadow: 5px 0 40px rgba(0,0,0,.9), 0 0 60px rgba(0,255,136,.04);
  }
  .sidebar::-webkit-scrollbar { width: 6px; }
  .sidebar::-webkit-scrollbar-track { background: #0a0a0a; }
  .sidebar::-webkit-scrollbar-thumb { background: var(--green); border-radius: 3px; }

  .sidebar-logo { padding: 0 25px 25px; border-bottom: 1px solid var(--border); margin-bottom: 20px; }
  .sidebar-logo .name {
    font-size: 1.5em; font-weight: bold; letter-spacing: 3px;
    background: linear-gradient(90deg, #00ff88, #00cc66, #00ff88);
    background-size: 200% auto;
    -webkit-background-clip: text; background-clip: text;
    -webkit-text-fill-color: transparent;
    display: block; margin-bottom: 8px;
    animation: gradientShift 4s linear infinite;
  }
  .sidebar-logo .classif {
    display: inline-block; background: var(--red); color: #fff;
    padding: 3px 10px; font-size: 0.65em; letter-spacing: 2px;
    font-weight: bold;
    border-radius: 3px;
    animation: blink 2s infinite, levelGlitch 5s infinite;
  }
  @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0.45; } }

  /* ============ ГЛИТЧ LEVEL 5 ============ */
  @keyframes levelGlitch {
    0%, 86%, 100% {
      text-shadow: 0 0 30px rgba(255,0,0,.45);
      transform: translate(0, 0);
    }
    87% {
      text-shadow: -2px 0 #00ff88, 2px 0 #00ccff, 0 0 30px rgba(255,0,0,.9);
      transform: translate(-1px, 0);
    }
    89% {
      text-shadow: 2px 0 #ff0000, -2px 0 #00ff88, 0 0 30px rgba(255,0,0,.9);
      transform: translate(1px, 1px);
    }
    91% {
      text-shadow: -2px 0 #00ccff, 2px 0 #ff0000, 0 0 30px rgba(255,0,0,.9);
      transform: translate(-1px, -1px);
    }
    93% {
      text-shadow: 2px 0 #00ff88, -2px 0 #00ccff, 0 0 30px rgba(255,0,0,.9);
      transform: translate(1px, 0);
    }
    95%, 97% {
      text-shadow: 0 0 30px rgba(255,0,0,.45);
      transform: translate(0, 0);
    }
  }

  .sidebar-nav { padding: 0 12px; }
  .nav-section { margin-bottom: 3px; }
  .nav-section-header {
    display: flex; align-items: center; justify-content: space-between;
    color: var(--green); text-decoration: none;
    padding: 10px 14px; margin: 2px 0; border-radius: 6px;
    font-size: 0.88em; letter-spacing: 1px; transition: .25s var(--ease);
    border-left: 3px solid transparent;
    cursor: pointer; user-select: none;
    position: relative; overflow: hidden;
  }
  .nav-section-header::after {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(90deg, rgba(0,255,136,.12), transparent);
    opacity: 0; transition: opacity .25s; pointer-events: none;
  }
  .nav-section-header:hover { background: rgba(0,255,136,.08); border-left-color: var(--green); }
  .nav-section-header:hover::after { opacity: 1; }
  .nav-section-header .arrow { font-size: .7em; transition: transform .3s var(--ease); color: var(--green); }
  .nav-section-header.open .arrow { transform: rotate(90deg); }
  .nav-section-header .label { flex: 1; margin-left: 8px; }

  .nav-sub {
    max-height: 0; overflow: hidden;
    transition: max-height .45s var(--ease);
    padding-left: 10px; border-left: 1px dashed #1f1f1f; margin-left: 15px;
  }
  .nav-sub.open { max-height: 1200px; }
  .nav-sub a {
    display: block; color: #88bbaa; text-decoration: none;
    padding: 7px 14px; margin: 2px 0; border-radius: 5px;
    font-size: .78em; letter-spacing: .5px;
    transition: .25s var(--ease); border-left: 2px solid transparent;
  }
  .nav-sub a:hover { background: rgba(0,255,136,.07); color: var(--green); border-left-color: var(--green-dim); padding-left: 18px; }
  .nav-sub a.active {
    background: rgba(0,255,136,.12); color: var(--green);
    border-left-color: var(--green);
    box-shadow: inset 0 0 12px rgba(0,255,136,.08);
  }

  /* ============ ОСНОВНОЙ КОНТЕНТ ============ */
  .main-content {
    margin-left: 290px; padding: 45px 40px;
    min-height: 100vh; width: calc(100% - 290px);
    position: relative; z-index: 10;
    background: rgba(5, 5, 5, 0.65);
  }

  .menu-toggle {
    display: none; position: fixed;
    top: 15px; left: 15px; z-index: 1100;
    background: var(--green); color: #000;
    border: none; padding: 10px 15px;
    border-radius: 8px; font-weight: bold;
    cursor: pointer; font-size: 1.2em;
    box-shadow: 0 0 20px rgba(0,255,136,.5);
    transition: .25s var(--ease);
  }
  .menu-toggle:hover { transform: scale(1.06); }

  @media (max-width: 900px) {
    .sidebar { transform: translateX(-100%); transition: transform .35s var(--ease); }
    .sidebar.open { transform: translateX(0); }
    .main-content { margin-left: 0; padding: 70px 15px 30px; width: 100%; }
    .menu-toggle { display: block; }
  }

  /* ============ ПОИСК ============ */
  .search-box {
    position: fixed; top: 20px; right: 24px;
    width: 340px; z-index: 1300;
  }
  .search-icon {
    position: absolute; left: 14px; top: 50%;
    transform: translateY(-50%);
    font-size: .95em; pointer-events: none;
    opacity: .55; z-index: 2; transition: .3s var(--ease);
  }
  .search-box:focus-within .search-icon { opacity: 1; transform: translateY(-50%) scale(1.1); }

  .search-box input {
    width: 100%; padding: 12px 42px 12px 44px;
    background: rgba(8,8,8,.92);
    border: 2px solid #1a1a1a;
    border-radius: 10px;
    color: var(--green);
    font-family: inherit; font-size: .85em;
    letter-spacing: 1px; outline: none;
    transition: .3s var(--ease);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
  }
  .search-box input::placeholder { color: #446; letter-spacing: 1px; }
  .search-box input:focus {
    border-color: var(--green);
    background: rgba(10,15,12,.95);
    box-shadow: 0 0 0 3px rgba(0,255,136,.12), 0 10px 30px rgba(0,0,0,.6);
    transform: translateY(-1px);
  }

  .search-clear {
    position: absolute; right: 10px; top: 50%;
    transform: translateY(-50%);
    width: 24px; height: 24px; border-radius: 50%;
    background: rgba(0,255,136,.15); color: var(--green);
    border: none; cursor: pointer;
    font-size: .8em; line-height: 1;
    display: none; align-items: center; justify-content: center;
    transition: .2s;
  }
  .search-clear:hover { background: rgba(0,255,136,.3); transform: translateY(-50%) scale(1.1); }
  .search-box.has-value .search-clear { display: flex; }

  .search-results {
    position: absolute; top: calc(100% + 10px); left: 0; right: 0;
    background: rgba(8,8,8,.98);
    border: 1px solid #1f1f1f;
    border-radius: 10px;
    max-height: 420px; overflow-y: auto;
    display: none; opacity: 0;
    transform: translateY(-6px);
    transition: opacity .22s var(--ease), transform .22s var(--ease);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    box-shadow: 0 24px 60px rgba(0,0,0,.85), 0 0 40px rgba(0,255,136,.05);
    overflow-x: hidden;
  }
  .search-results.show { display: block; opacity: 1; transform: none; }
  .search-results::-webkit-scrollbar { width: 5px; }
  .search-results::-webkit-scrollbar-thumb { background: var(--green); border-radius: 3px; }
  .search-results::-webkit-scrollbar-track { background: #0a0a0a; }

  .search-item {
    display: block; padding: 11px 16px 11px 26px;
    color: #b0b0b0; text-decoration: none;
    border-bottom: 1px solid #131313;
    font-size: .82em; line-height: 1.5;
    transition: .2s var(--ease);
    cursor: pointer; position: relative;
  }
  .search-item:last-child { border-bottom: none; }
  .search-item::before {
    content: '▸'; position: absolute;
    left: 10px; top: 50%; transform: translateY(-50%);
    color: var(--green); font-size: .9em;
    opacity: 0; transition: .2s;
  }
  .search-item:hover, .search-item.active {
    background: rgba(0,255,136,.09);
    color: #e8e8e8; padding-left: 32px;
  }
  .search-item:hover::before, .search-item.active::before { opacity: 1; }

  .search-tag {
    display: inline-block;
    color: var(--green-dim); font-size: .72em;
    letter-spacing: 1.5px; text-transform: uppercase;
    margin-right: 8px; padding: 1px 6px;
    background: rgba(0,255,136,.08);
    border-radius: 3px; font-weight: bold;
  }
  .search-item mark {
    background: rgba(0,255,136,.28);
    color: var(--green); padding: 1px 3px;
    border-radius: 3px; font-weight: bold;
  }
  .search-empty {
    padding: 22px 16px; text-align: center;
    color: #555; font-size: .82em; letter-spacing: 1px;
  }
  .search-empty strong { color: var(--green); }

  @media (max-width: 900px) {
    .search-box {
      top: 15px; right: 15px;
      width: calc(100% - 90px);
      max-width: 340px;
    }
    .search-box input { padding: 10px 38px 10px 38px; font-size: .78em; }
  }

  /* ============ ЗАГОЛОВОК ============ */
  .header {
    text-align: center; padding-bottom: 40px;
    border-bottom: 3px solid var(--green); margin-bottom: 50px;
    position: relative; overflow: hidden;
  }
  .header::after {
    content: ''; position: absolute; bottom: -3px; left: -100%;
    width: 60%; height: 3px;
    background: linear-gradient(90deg, transparent, #fff, transparent);
    animation: scanHeader 4s ease-in-out infinite;
  }
  @keyframes scanHeader {
    0% { left: -60%; }
    60%, 100% { left: 120%; }
  }

  .classification {
    display: inline-block; background: var(--red); color: #fff;
    padding: 8px 25px; font-weight: bold; letter-spacing: 4px;
    font-size: .9em; margin-bottom: 25px;
    border-radius: 4px;
    box-shadow: 0 0 30px rgba(255,0,0,.45);
    animation: blink 2s infinite, levelGlitch 5s infinite;
  }
  h1 {
    font-size: clamp(2em, 6vw, 4em);
    background: linear-gradient(90deg, #00ff88, #00cc66, #009944, #00ff88);
    background-size: 300% auto;
    -webkit-background-clip: text; background-clip: text;
    -webkit-text-fill-color: transparent;
    letter-spacing: 5px; margin-bottom: 15px;
    animation: gradientShift 6s linear infinite;
    filter: drop-shadow(0 0 25px rgba(0,255,136,.25));
  }
  .subtitle { color: var(--green); font-size: clamp(.9em, 2vw, 1.2em); letter-spacing: 3px; }
  .codename { color: #666; font-size: .9em; margin-top: 15px; letter-spacing: 2px; }

  /* ============ ЗАГОЛОВКИ ============ */
  h2 {
    color: var(--green); font-size: clamp(1.3em, 3vw, 1.9em);
    margin: 55px 0 25px; padding: 18px 0 18px 25px;
    border-left: 6px solid var(--green);
    background: linear-gradient(90deg, rgba(0,255,136,.12), transparent);
    letter-spacing: 2px; text-transform: uppercase;
    scroll-margin-top: 20px;
    position: relative;
    transition: .3s var(--ease);
  }
  h2::before {
    content: ''; position: absolute; left: -6px; top: 0; bottom: 0;
    width: 6px; background: var(--green);
    box-shadow: 0 0 20px var(--green);
  }
  h2:hover { padding-left: 35px; background: linear-gradient(90deg, rgba(0,255,136,.2), transparent); }

  h3 {
    color: #66ffaa; font-size: clamp(1.05em, 2.2vw, 1.35em);
    margin: 35px 0 18px; padding-left: 18px;
    border-left: 4px solid var(--green-dim); letter-spacing: 1px;
    scroll-margin-top: 20px;
    transition: .3s var(--ease);
  }
  h3:hover { border-left-color: var(--green); padding-left: 24px; }

  h4 { color: #88ffbb; font-size: 1.1em; margin: 25px 0 12px; letter-spacing: 1px; }

  p { margin: 12px 0; color: var(--text); }
  strong { color: var(--green); }

  ul, ol { padding-left: 30px; margin: 18px 0; }
  li { padding: 8px 0 8px 10px; color: var(--text); border-bottom: 1px dotted var(--border); transition: .2s; }
  li:hover { color: #e8e8e8; border-bottom-color: rgba(0,255,136,.25); }

  /* ============ СЕТКИ ============ */
  .two-col-grid,
  .code-grid,
  .clearance-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 30px; margin: 25px 0; width: 100%;
    align-items: start;
  }
  @media (max-width: 1200px) {
    .two-col-grid, .code-grid, .clearance-grid { grid-template-columns: 1fr; }
  }

  /* ============ ТАБЛИЦЫ ============ */
  .data-table {
    width: 100%; border-collapse: collapse;
    background: #0a0a0a; border: 1px solid var(--border);
    font-size: .92em; table-layout: auto;
  }
  .data-table th {
    background: #0f1a12; color: var(--green); padding: 16px 18px;
    text-align: left; font-weight: bold; letter-spacing: 1px;
    border-bottom: 2px solid var(--green);
    text-transform: uppercase; font-size: .85em;
  }
  .data-table td {
    padding: 14px 18px; border-bottom: 1px solid var(--border);
    color: var(--text); vertical-align: top;
    background: #0a0a0a; line-height: 1.7;
    transition: .2s;
  }
  .data-table tr { background: #0a0a0a; transition: .2s; }
  .data-table tbody tr:hover, .data-table tr:hover td {
    background: #101010; color: #e8e8e8;
  }
  .data-table tr:hover td:first-child { box-shadow: inset 3px 0 0 var(--green); }
  .data-table strong { color: var(--green); }
  .table-wrap {
    background: #0a0a0a; border-radius: 10px; overflow: hidden;
    margin: 20px 0; width: 100%;
    border: 1px solid var(--border);
    transition: .3s var(--ease);
  }
  .table-wrap:hover { border-color: rgba(0,255,136,.35); box-shadow: 0 12px 40px rgba(0,0,0,.6); }

  /* ============ КАРТОЧКИ КОДОВ ============ */
  .code-card {
    padding: 28px; border-radius: 12px; background: var(--panel-2);
    border: 2px solid; transition: .35s var(--ease);
    position: relative; overflow: hidden;
    isolation: isolate;
  }
  .code-card::after {
    content: ''; position: absolute; top: 0; left: -120%;
    width: 60%; height: 100%;
    background: linear-gradient(100deg, transparent, rgba(255,255,255,.06), transparent);
    transform: skewX(-18deg);
    transition: left .7s var(--ease);
    pointer-events: none;
  }
  .code-card:hover::after { left: 140%; }
  .code-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 18px 50px rgba(0,0,0,.7);
  }
  .code-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px; }
  .code-card h4 { font-size: 1.4em; margin-bottom: 15px; letter-spacing: 3px; }
  .code-card p { font-size: .92em; color: #999; margin-bottom: 12px; }
  .code-card ul { margin-top: 10px; font-size: .88em; }
  .code-card li { border-bottom: 1px dotted rgba(255,255,255,.05); }

  .code-red { border-color: #ff0000; background: linear-gradient(135deg, #0f0f0f, rgba(255,0,0,.08)); }
  .code-red::before { background: #ff0000; box-shadow: 0 0 18px #ff0000; }
  .code-red h4 { color: #ff0000; text-shadow: 0 0 15px rgba(255,0,0,.5); }
  .code-black { border-color: #444; background: linear-gradient(135deg, #0f0f0f, rgba(50,50,50,.15)); }
  .code-black::before { background: #444; }
  .code-black h4 { color: #999; text-shadow: 0 0 15px rgba(150,150,150,.5); }
  .code-green { border-color: var(--green); background: linear-gradient(135deg, #0f0f0f, rgba(0,255,136,.08)); }
  .code-green::before { background: var(--green); box-shadow: 0 0 18px var(--green); }
  .code-green h4 { color: var(--green); text-shadow: 0 0 15px rgba(0,255,136,.5); }
  .code-blue { border-color: #4a90d9; background: linear-gradient(135deg, #0f0f0f, rgba(74,144,217,.08)); }
  .code-blue::before { background: #4a90d9; }
  .code-blue h4 { color: #4a90d9; text-shadow: 0 0 15px rgba(74,144,217,.5); }
  .code-superblue { border-color: #00ccff; background: linear-gradient(135deg, #0f0f0f, rgba(0,204,255,.08)); }
  .code-superblue::before { background: #00ccff; box-shadow: 0 0 18px #00ccff; }
  .code-superblue h4 { color: #00ccff; text-shadow: 0 0 15px rgba(0,204,255,.5); }
  .code-yellow { border-color: #ffcc00; background: linear-gradient(135deg, #0f0f0f, rgba(255,204,0,.08)); }
  .code-yellow::before { background: #ffcc00; }
  .code-yellow h4 { color: #ffcc00; text-shadow: 0 0 15px rgba(255,204,0,.5); }
  .code-orange { border-color: #ff8800; background: linear-gradient(135deg, #0f0f0f, rgba(255,136,0,.08)); }
  .code-orange::before { background: #ff8800; }
  .code-orange h4 { color: #ff8800; text-shadow: 0 0 15px rgba(255,136,0,.5); }
  .code-purple { border-color: #9013fe; background: linear-gradient(135deg, #0f0f0f, rgba(144,19,254,.08)); }
  .code-purple::before { background: #9013fe; box-shadow: 0 0 18px #9013fe; }
  .code-purple h4 { color: #9013fe; text-shadow: 0 0 15px rgba(144,19,254,.5); }
  .code-white { border-color: #cccccc; background: linear-gradient(135deg, #0f0f0f, rgba(200,200,200,.08)); }
  .code-white::before { background: #cccccc; }
  .code-white h4 { color: #ddd; text-shadow: 0 0 15px rgba(200,200,200,.4); }
  .code-gray { border-color: #888; background: linear-gradient(135deg, #0f0f0f, rgba(136,136,136,.1)); }
  .code-gray::before { background: #888; }
  .code-gray h4 { color: #aaa; text-shadow: 0 0 15px rgba(150,150,150,.5); }
  .code-clean { border-color: #e0e0e0; background: linear-gradient(135deg, #0f0f0f, rgba(224,224,224,.06)); }
  .code-clean::before { background: #e0e0e0; }
  .code-clean h4 { color: #e0e0e0; text-shadow: 0 0 15px rgba(224,224,224,.5); }
  .code-superclean { border-color: #ff69b4; background: linear-gradient(135deg, #0f0f0f, rgba(255,105,180,.08)); }
  .code-superclean::before { background: #ff69b4; box-shadow: 0 0 18px #ff69b4; }
  .code-superclean h4 { color: #ff69b4; text-shadow: 0 0 15px rgba(255,105,180,.5); }
  .code-silver { border-color: #c0c0c0; background: linear-gradient(135deg, #0f0f0f, rgba(192,192,192,.08)); }
  .code-silver::before { background: #c0c0c0; }
  .code-silver h4 { color: #c0c0c0; text-shadow: 0 0 15px rgba(192,192,192,.5); }

  /* ============ АЛЕРТЫ ============ */
  .alert {
    padding: 22px 28px; border-radius: 10px; margin: 25px 0;
    border-left: 6px solid; font-size: .95em;
    transition: .3s var(--ease);
    backdrop-filter: blur(4px);
  }
  .alert:hover { transform: translateX(6px); }
  .alert-danger { background: rgba(255, 0, 0, .08); border-color: #ff0000; color: #ff8888; }
  .alert-warning { background: rgba(255, 170, 0, .08); border-color: #ffaa00; color: #ffcc66; }
  .alert-info { background: rgba(0, 255, 136, .05); border-color: var(--green); color: #88ffbb; }

  .section {
    margin: 40px 0; padding: 32px;
    background: var(--panel); border-radius: 12px;
    border: 1px solid var(--border);
    transition: .3s var(--ease);
  }
  .section:hover { border-color: rgba(0,255,136,.25); }

  /* ============ ФУТЕР ============ */
  .footer {
    text-align: center; margin-top: 70px; padding: 40px 20px;
    border-top: 2px solid var(--border); color: #555;
    font-size: .85em; letter-spacing: 1px; background: #080808;
    border-radius: 12px;
  }
  .discord, .telegram, .youtube {
    display: inline-block; color: #fff;
    padding: 15px 40px; border-radius: 12px; text-decoration: none;
    font-weight: bold; margin: 10px; transition: .3s var(--ease);
    letter-spacing: 2px; font-size: 1em;
    position: relative; overflow: hidden;
  }
  .discord::after, .telegram::after, .youtube::after {
    content: ''; position: absolute; top: 0; left: -120%;
    width: 60%; height: 100%;
    background: linear-gradient(100deg, transparent, rgba(255,255,255,.35), transparent);
    transform: skewX(-18deg);
  }
  .discord:hover::after, .telegram:hover::after, .youtube:hover::after {
    animation: btnShine .8s var(--ease);
  }
  @keyframes btnShine { to { left: 150%; } }

  .discord { background: #5865F2; }
  .discord:hover { background: #4752c4; transform: translateY(-3px) scale(1.04); box-shadow: 0 12px 40px rgba(88,101,242,.55); }
  .telegram { background: #0088cc; }
  .telegram:hover { background: #006699; transform: translateY(-3px) scale(1.04); box-shadow: 0 12px 40px rgba(0,136,204,.55); }
  .youtube { background: #ff0000; }
  .youtube:hover { background: #cc0000; transform: translateY(-3px) scale(1.04); box-shadow: 0 12px 40px rgba(255,0,0,.55); }
  .center { text-align: center; }

  /* ============ АККОРДЕОН ============ */
  .acc {
    background: var(--panel);
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
    align-self: start;
    height: fit-content;
    transition: .35s var(--ease);
  }
  .acc:hover { border-color: rgba(0,255,136,.35); }
  .acc.open { border-color: rgba(0,255,136,.5); box-shadow: 0 12px 40px rgba(0,0,0,.6), 0 0 30px rgba(0,255,136,.06); }

  .acc-head {
    width: 100%; text-align: left; cursor: pointer;
    color: var(--green); font-family: inherit; font-size: 1em;
    font-weight: bold; letter-spacing: 1px;
    background: var(--panel-2);
    border: none; border-left: 5px solid var(--green);
    padding: 18px 22px;
    display: flex; align-items: center; gap: 12px;
    transition: .3s var(--ease);
  }
  .acc-head:hover { background: #141414; padding-left: 28px; }
  .acc.open .acc-head { border-left-color: var(--amber); color: var(--amber); background: #141414; }
  .acc-head .acc-arrow {
    margin-left: auto; font-size: .7em;
    transition: transform .35s var(--ease);
  }
  .acc.open .acc-head .acc-arrow { transform: rotate(90deg); }

  .acc-body {
    display: grid; grid-template-rows: 0fr;
    transition: grid-template-rows .45s var(--ease);
  }
  .acc.open .acc-body { grid-template-rows: 1fr; }
  .acc-inner { overflow: hidden; }
  .acc-inner > * { padding: 0 22px; }
  .acc-inner > *:first-child { padding-top: 18px; }
  .acc-inner > *:last-child { padding-bottom: 18px; }
  .acc-inner ul { padding-left: 46px; }

  /* ============ УТИЛИТЫ ============ */
  .highlight { background: rgba(0,255,136,.1); padding: 2px 8px; border-radius: 4px; color: var(--green); }
  .critical { background: rgba(255,0,0,.15); padding: 2px 8px; border-radius: 4px; color: #ff6666; font-weight: bold; }
  .evacuated { background: rgba(255,170,0,.15); padding: 2px 8px; border-radius: 4px; color: #ffcc66; font-weight: bold; }
  .divider {
    height: 2px; border: none; margin: 50px 0;
    background: linear-gradient(90deg, transparent, var(--green), transparent);
    opacity: .7;
  }

  /* ============ ДОПУСК / КЛАССЫ ============ */
  .clearance-card {
    padding: 28px; border-radius: 12px; border: 2px solid;
    background: var(--panel-2); transition: .35s var(--ease);
    position: relative; overflow: hidden;
  }
  .clearance-card::after {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 100%;
    background: radial-gradient(circle at top right, rgba(255,255,255,.05), transparent 60%);
    opacity: 0; transition: opacity .35s;
    pointer-events: none;
  }
  .clearance-card:hover::after { opacity: 1; }
  .clearance-card:hover { transform: translateY(-6px); box-shadow: 0 18px 50px rgba(0,0,0,.7); }
  .clearance-card h4 { font-size: 1.5em; margin-bottom: 15px; letter-spacing: 2px; }
  .clearance-card p { font-size: .9em; color: #999; }
  .clearance-card ul { margin-top: 10px; font-size: .9em; }

  .level-1 { border-color: #666; } .level-1 h4 { color: #999; }
  .level-2 { border-color: #f5a623; } .level-2 h4 { color: #f5a623; }
  .level-3 { border-color: #d0021b; } .level-3 h4 { color: #d0021b; }
  .level-4 { border-color: #9013fe; } .level-4 h4 { color: #9013fe; }
  .level-5 { border-color: var(--green); } .level-5 h4 { color: var(--green); }
  .level-a { border-color: #ff0000; } .level-a h4 { color: #ff0000; }
  .level-b { border-color: #ff8800; } .level-b h4 { color: #ff8800; }
  .level-c { border-color: #00ccff; } .level-c h4 { color: #00ccff; }
  .level-d { border-color: #666; } .level-d h4 { color: #999; }
  .level-e { border-color: #9013fe; } .level-e h4 { color: #9013fe; }

  /* ============ КАРТОЧКИ ============ */
  .priv-card, .item-card, .scp-card {
    padding: 28px; border-radius: 12px;
    background: var(--panel-2); border: 2px solid var(--green);
    transition: .35s var(--ease);
    position: relative; overflow: hidden;
  }
  .priv-card::after, .item-card::after, .scp-card::after {
    content: ''; position: absolute; top: 0; left: -120%;
    width: 60%; height: 100%;
    background: linear-gradient(100deg, transparent, rgba(255,255,255,.06), transparent);
    transform: skewX(-18deg);
    transition: left .8s var(--ease);
    pointer-events: none;
  }
  .priv-card:hover::after, .item-card:hover::after, .scp-card:hover::after { left: 140%; }
  .priv-card:hover, .item-card:hover, .scp-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 18px 50px rgba(0,0,0,.7), 0 0 35px rgba(0,255,136,.1);
  }
  .priv-card h4, .scp-card h4 { color: var(--green); font-size: 1.3em; margin-bottom: 15px; letter-spacing: 2px; }
  .priv-card p, .scp-card p { font-size: .9em; color: #999; }
  .priv-card ul, .item-card ul, .scp-card ul { margin-top: 10px; font-size: .9em; }

  .item-card h4 { font-size: 1.3em; margin-bottom: 15px; letter-spacing: 2px; }
  .item-yes { border-color: var(--green); } .item-yes h4 { color: var(--green); }
  .item-no { border-color: #ff0000; } .item-no h4 { color: #ff6666; }
  .item-arrest { border-color: #ffaa00; } .item-arrest h4 { color: #ffaa00; }
  .item-execute { border-color: #d0021b; } .item-execute h4 { color: #ff3333; }

  .hp-badge {
    display: inline-block; background: rgba(255,0,0,.15);
    border: 1px solid #ff4444; color: #ff8888;
    padding: 4px 12px; border-radius: 6px;
    font-size: .85em; font-weight: bold;
    margin-bottom: 10px; letter-spacing: 1px;
  }
  .evacuated-badge {
    display: inline-block; background: rgba(255,170,0,.15);
    border: 1px solid #ffaa00; color: #ffcc66;
    padding: 4px 12px; border-radius: 6px;
    font-size: .85em; font-weight: bold;
    margin-bottom: 10px; letter-spacing: 1px;
    animation: blink 2.4s infinite;
  }

  /* ============ REVEAL ============ */
  .reveal {
    opacity: 0; transform: translateY(34px);
    transition: opacity .8s var(--ease), transform .8s var(--ease);
    will-change: opacity, transform;
  }
  .reveal.in { opacity: 1; transform: none; }

  .reveal-left { opacity: 0; transform: translateX(-34px);
    transition: opacity .8s var(--ease), transform .8s var(--ease); }
  .reveal-left.in { opacity: 1; transform: none; }

  .reveal-right { opacity: 0; transform: translateX(34px);
    transition: opacity .8s var(--ease), transform .8s var(--ease); }
  .reveal-right.in { opacity: 1; transform: none; }

  .reveal-scale { opacity: 0; transform: scale(.94);
    transition: opacity .7s var(--ease), transform .7s var(--ease); }
  .reveal-scale.in { opacity: 1; transform: none; }

  /* ============ КНОПКА НАВЕРХ ============ */
  .to-top {
    position: fixed; right: 24px; bottom: 24px;
    width: 52px; height: 52px; border-radius: 50%;
    background: linear-gradient(135deg, var(--green), var(--green-deep));
    color: #000; border: none; cursor: pointer;
    font-size: 1.4em; font-weight: bold;
    display: flex; align-items: center; justify-content: center;
    z-index: 1500;
    opacity: 0; transform: translateY(20px) scale(.8); pointer-events: none;
    transition: .4s var(--ease);
    box-shadow: 0 0 30px rgba(0,255,136,.5);
  }
  .to-top.show { opacity: 1; transform: none; pointer-events: auto; }
  .to-top:hover { transform: translateY(-4px) scale(1.08); box-shadow: 0 0 45px rgba(0,255,136,.8); }

  @media (max-width: 900px) {
    .to-top { right: 14px; bottom: 14px; width: 46px; height: 46px; }
  }

  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; transition: none !important; }
    .reveal, .reveal-left, .reveal-right, .reveal-scale { opacity: 1; transform: none; }
  }
</style>
</head>
<body>

  <div class="scroll-progress" id="scrollProgress"></div>

  <div class="parallax-bg">
    <div class="parallax-layer back" id="layer-back"></div>
    <div class="parallax-layer middle" id="layer-middle"></div>
    <div class="parallax-layer front" id="layer-front"></div>
  </div>

  <div class="watermark-overlay" id="watermark-overlay"></div>

  <!-- ПОИСК -->
  <div class="search-box" id="searchBox">
    <span class="search-icon">🔍</span>
    <input type="text" id="searchInput" placeholder="Поиск по уставу..." autocomplete="off" spellcheck="false">
    <button class="search-clear" id="searchClear" type="button" aria-label="Очистить">✕</button>
    <div class="search-results" id="searchResults"></div>
  </div>

  <button class="menu-toggle" onclick="document.querySelector('.sidebar').classList.toggle('open')">☰</button>

  <aside class="sidebar">
    <div class="sidebar-logo">
      <span class="name">MV.PROJECT</span>
      <span class="classif">⚠ LEVEL 5 ⚠</span>
    </div>
    <nav class="sidebar-nav">

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🚨</span><span class="label">КОДЫ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#codes">Все коды угроз</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🔐</span><span class="label">ДОПУСК</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#clearance">Уровни 1-5</a>
          <a href="#classes-personnel">Классы A-E</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🛡️</span><span class="label">МОГ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#mtf">Основные МОГ</a>
          <a href="#mtf-dop">Дополнительные МОГ</a>
          <a href="#mtf-tg">Тактические группы</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>📋</span><span class="label">ПРОТОКОЛЫ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#prot-p-l">Протоколы P-L</a>
          <a href="#prot-p-s">Протоколы P-S</a>
          <a href="#prot-p-b">Протоколы P-B</a>
          <a href="#prot-p-i">Протоколы P-I</a>
          <a href="#prot-p-e">Протоколы P-E</a>
          <a href="#prot-kir">Изоляционные коды</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>⭐</span><span class="label">ПРИВИЛЕГИИ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#priv-obligations">Обязанности админа</a>
          <a href="#priv-forbidden">Запреты</a>
          <a href="#priv-lies">Наказания за враньё</a>
          <a href="#priv-confidential">Конфиденциальность</a>
          <a href="#priv-others">Админство на других</a>
          <a href="#priv-hierarchy">Иерархия</a>
          <a href="#priv-punish">Виды взысканий</a>
          <a href="#priv-rights">Права админов</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>👔</span><span class="label">ФОРМА</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#uniform">Что можно носить</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🎒</span><span class="label">ПРЕДМЕТЫ И АРЕСТ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#items-can">Что можно носить</a>
          <a href="#items-cant">Что нельзя носить</a>
          <a href="#items-arrest">Арест персонала</a>
          <a href="#items-execute">Расстрел класса D</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>📜</span><span class="label">ОБЩИЕ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#general">Принципы и возраст</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🎭</span><span class="label">RP</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#rp">Все RP-правила</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>👥</span><span class="label">КЛАССЫ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#classes">Игровые классы</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🧬</span><span class="label">SCP</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#scp">Основные SCP</a>
          <a href="#scp953">SCP-953</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>⚙️</span><span class="label">SCP-914</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#scp914">Правила 914</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>📢</span><span class="label">ИНТЕРКОМ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#intercom">Правила интеркома</a>
          <a href="#chat">Правила чата</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>⏱️</span><span class="label">БАНЫ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub"><a href="#bans">Сроки наказаний</a></div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>📩</span><span class="label">АПЕЛЛЯЦИЯ</span><span class="arrow">▶</span>
        </div>
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
      <strong>⛔ ВНИМАНИЕ:</strong> Данный устав обязателен к прочтению каждому сотруднику Участка. 
      Заходя на сервер <strong>MV.Project</strong>, вы автоматически соглашаетесь с правилами. 
      <span class="critical">Незнание правил не освобождает от ответственности.</span>
    </div>

    <!-- КОДЫ -->
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
      <div class="code-card code-green reveal-scale">
        <h4>🟢 КОД ЗЕЛЁНЫЙ</h4>
        <p><strong>Био-угроза / Заражение</strong></p>
        <p>Опасность, связанная с био-угрозой, инфекцией или источником заражения.</p>
        <p><strong>Указания:</strong> Избегайте контакта с источниками. Не покидайте Участок.</p>
        <p><strong>МОГ:</strong> Бета-7 «Шляпные болванчики»</p>
      </div>
      <div class="code-card code-blue reveal-scale">
        <h4>🔵 КОД СИНИЙ</h4>
        <p><strong>Побег разумного объекта</strong></p>
        <p>Побег объекта с интеллектом ниже человеческого.</p>
        <p><strong>Указания:</strong> Следуйте указаниям охраны.</p>
        <p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p>
      </div>
      <div class="code-card code-superblue reveal-scale">
        <h4>🔷 КОД СУПЕРСИНИЙ</h4>
        <p><strong>Побег разумного объекта (высокий интеллект)</strong></p>
        <p>Побег объекта с интеллектом, равным или превышающим человеческий.</p>
        <p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p>
      </div>
      <div class="code-card code-yellow reveal-scale">
        <h4>🟡 КОД ЖЁЛТЫЙ</h4>
        <p><strong>Меметическая / когнитивная угроза</strong></p>
        <p>Присутствие меметической или информационной угрозы.</p>
        <p><strong>МОГ:</strong> Эта-10, Эта-11</p>
      </div>
      <div class="code-card code-red reveal-scale">
        <h4>🔴 КОД КРАСНЫЙ</h4>
        <p><strong>Агрессивная сущность (АНС)</strong></p>
        <p>Побег опасной агрессивной сущности.</p>
        <p><strong>МОГ:</strong> Ню-7, Эта-5, Гамма-5</p>
      </div>
      <div class="code-card code-black reveal-scale">
        <h4>⚫ КОД ЧЁРНЫЙ</h4>
        <p><strong>Нарушение содержания НЛУ</strong></p>
        <p>Нарушение содержания Неликвидируемой Угрозы.</p>
        <p><strong>⚠️ ВАЖНО:</strong> <span class="critical">Эвакуация ЗАПРЕЩЕНА!</span> Код чёрный может быть и на SCP-106 — покидание комплекса смертельно опасно.</p>
        <p><strong>МОГ:</strong> Эпсилон-11, Сигма-23</p>
      </div>
      <div class="code-card code-white reveal-scale">
        <h4>⚪ КОД БЕЛЫЙ</h4>
        <p><strong>Вторжение сил захвата</strong></p>
        <p>Вторжение высокоорганизованных сил захвата.</p>
        <p><strong>МОГ:</strong> Все ММОГ уровня батальона</p>
      </div>
      <div class="code-card code-gray reveal-scale">
        <h4>🌫️ КОД СЕРЫЙ</h4>
        <p><strong>Внутренняя угроза</strong></p>
        <p>Аналог БЕЛОГО, но угроза изнутри Участка.</p>
        <p><strong>МОГ:</strong> Все ММОГ уровня батальона</p>
      </div>
      <div class="code-card code-purple reveal-scale">
        <h4>🟣 КОД ПУРПУРНЫЙ</h4>
        <p><strong>Экстрамерная угроза</strong></p>
        <p>Нарушения пространства, времени, причинности.</p>
        <p><strong>МОГ:</strong> Дзета-9, Лямбда-5, Мю-13</p>
      </div>
      <div class="code-card code-clean reveal-scale">
        <h4>⬜ КОД ЧИСТЫЙ</h4>
        <p><strong>НОУС</strong></p>
        <p>Нарушение Удержания Объекта Содержания — <strong>известная сущность, но неизвестно какая именно</strong>.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
      <div class="code-card code-superclean reveal-scale">
        <h4>💗 КОД СУПЕРЧИСТЫЙ</h4>
        <p><strong>Неизвестная аномальная угроза</strong></p>
        <p>Обозначает <strong>неизвестную аномальную угрозу</strong> (сама угроза не идентифицирована).</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
      <div class="code-card code-silver reveal-scale">
        <h4>🥈 КОД ХЛАДНОЕ СЕРЕБРО</h4>
        <p><strong>Фатальный сбой Фонда</strong></p>
        <p>Событие, ведущее к краху Фонда.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
    </div>

    <hr class="divider">

    <!-- ДОПУСК -->
    <h2 id="clearance" class="reveal">🔐 Раздел II. Уровни допуска персонала</h2>

    <div class="clearance-grid">
      <div class="clearance-card level-1 reveal-left">
        <h4>УРОВЕНЬ 1</h4>
        <p><strong>Неважный персонал</strong></p>
        <ul>
          <li>Уборщики</li>
          <li>Обслуживающий персонал</li>
          <li>Стажёры без допуска</li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: только общественные зоны. Сопровождение обязательно.</p>
        <p><strong>Протоколы:</strong> не имеет права использовать.</p>
      </div>
      <div class="clearance-card level-2 reveal-right">
        <h4>УРОВЕНЬ 2</h4>
        <p><strong>Младший персонал</strong></p>
        <ul>
          <li>Капрал СБ</li>
          <li>Младший НС</li>
          <li>Инженер</li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: Лёгкая зона, подсобные помещения.</p>
        <p><strong>Протоколы:</strong> P-S-1.</p>
      </div>
      <div class="clearance-card level-3 reveal-left">
        <h4>УРОВЕНЬ 3</h4>
        <p><strong>Старший персонал</strong></p>
        <ul>
          <li>Сержант СБ</li>
          <li>Лейтенант СБ</li>
          <li>Старший НС</li>
          <li>НС</li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: Лёгкая и Тяжёлая зоны.</p>
        <p><strong>Протоколы:</strong> P-L-1, P-L-2, P-L-3, P-S-1, P-S-2, P-S-3.</p>
      </div>
      <div class="clearance-card level-4 reveal-right">
        <h4>УРОВЕНЬ 4</h4>
        <p><strong>Командование</strong></p>
        <ul>
          <li>Директор Участка</li>
          <li>Представитель КпЭ</li>
          <li>Агент ГАРШ-O4</li>
          <li>ГНС</li>
          <li>ГСБ</li>
          <li><strong>Капитан МОГ</strong></li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: все зоны Участка.</p>
        <p><strong>Протоколы:</strong> все P-L, P-S, P-B, P-I, P-E.</p>
      </div>
      <div class="clearance-card level-5 reveal-left">
        <h4>УРОВЕНЬ 5</h4>
        <p><strong>Совет О5</strong></p>
        <ul>
          <li>Совет О5</li>
          <li>Председатель КпЭ</li>
          <li>Инспектор КпЭ</li>
          <li>Старший агент ГАРШ-O4</li>
          <li>Суд-O3</li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: полный доступ.</p>
        <p><strong>Протоколы:</strong> все, включая CAP-1 — CAP-7.</p>
      </div>
    </div>

    <hr class="divider">

    <!-- КЛАССЫ ПЕРСОНАЛА -->
    <h2 id="classes-personnel" class="reveal">👤 Раздел III. Классы персонала</h2>

    <div class="clearance-grid">
      <div class="clearance-card level-a reveal-scale">
        <h4>КЛАСС A</h4>
        <p><strong>Стратегически важный персонал</strong></p>
        <ul>
          <li>Члены Совета О5</li>
          <li>Высшее руководство Фонда</li>
        </ul>
        <p><strong>Запрещено:</strong> Прямой доступ к аномалиям. Выход из защищённых зон.</p>
        <p><strong>Разрешено:</strong> Работа в защищённых зонах.</p>
      </div>
      <div class="clearance-card level-b reveal-scale">
        <h4>КЛАСС B</h4>
        <p><strong>Важный персонал</strong></p>
        <ul>
          <li>Руководители отделов</li>
          <li>Старшие научные сотрудники</li>
          <li>Ключевые инженеры</li>
        </ul>
        <p><strong>Запрещено:</strong> Доступ к аномалиям без карантина.</p>
        <p><strong>Разрешено:</strong> Доступ к карантинным аномалиям.</p>
      </div>
      <div class="clearance-card level-c reveal-scale">
        <h4>КЛАСС C</h4>
        <p><strong>Прямой доступ</strong></p>
        <ul>
          <li>Научные сотрудники</li>
          <li>Охрана</li>
          <li>Инженеры</li>
        </ul>
        <p><strong>Запрещено:</strong> Контакт с опасными аномалиями.</p>
        <p><strong>Разрешено:</strong> Работа с безопасными аномалиями.</p>
      </div>
      <div class="clearance-card level-d reveal-scale">
        <h4>КЛАСС D</h4>
        <p><strong>Расходный персонал</strong></p>
        <ul>
          <li>Заключённые</li>
          <li>Испытуемые</li>
        </ul>
        <p><strong>Запрещено:</strong> Контакт с классами A и B. Побег.</p>
        <p><strong>Разрешено:</strong> Участие в тестах.</p>
      </div>
      <div class="clearance-card level-e reveal-scale">
        <h4>КЛАСС E</h4>
        <p><strong>Временное обозначение</strong></p>
        <ul>
          <li>Полевые агенты</li>
          <li>Пострадавшие от аномалий</li>
        </ul>
        <p><strong>Запрещено:</strong> Возврат к работе до обследования.</p>
        <p><strong>Разрешено:</strong> Карантин и наблюдение.</p>
      </div>
    </div>

    <hr class="divider">

    <!-- МОГ -->
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

    <!-- ПРОТОКОЛЫ -->
    <h2 id="protocols" class="reveal">📋 Раздел V. Протоколы и изоляционные коды</h2>
    <p class="reveal">Использование протоколов разрешено только персоналу с соответствующим уровнем допуска.</p>

    <h3 id="prot-p-l" class="reveal">Протоколы P-L (блокировка) — УД 3+</h3>
    <div class="table-wrap reveal">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-L-1</strong></td><td>Блокировка гермо-ворот A и B.</td><td>3+</td></tr>
        <tr><td><strong>P-L-2</strong></td><td>Блокировка всех КПП.</td><td>3+</td></tr>
        <tr><td><strong>P-L-3</strong></td><td>Блокировка всех дверей.</td><td>3+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-s" class="reveal">Протоколы P-S (SCP) — УД 2+</h3>
    <div class="table-wrap reveal">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-S-1</strong></td><td>Отслеживание SCP-объектов.</td><td>2+</td></tr>
        <tr><td><strong>P-S-2</strong></td><td>Отслеживание статуса SCP.</td><td>3+</td></tr>
        <tr><td><strong>P-S-3</strong></td><td>Активация тесла-ворот.</td><td>3+</td></tr>
        <tr><td><strong>P-S-4</strong></td><td>Сканирование комплекса.</td><td>3+</td></tr>
        <tr><td><strong>P-S-5</strong></td><td>Полный блэкаут комплекса.</td><td>3+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-b" class="reveal">Протоколы P-B (био-безопасность) — УД 3+</h3>
    <div class="table-wrap reveal">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-B-1</strong></td><td>Запечатывание заражённых комнат.</td><td>3+</td></tr>
        <tr><td><strong>P-B-2</strong></td><td>Запечатывание камер содержания.</td><td>3+</td></tr>
        <tr><td><strong>P-B-3</strong></td><td>Деконтаминация ЛЗС.</td><td>3+</td></tr>
        <tr><td><strong>P-B-4</strong></td><td>Деконтаминация ТЗС.</td><td>3+</td></tr>
        <tr><td><strong>P-B-5</strong></td><td>Подрыв комплекса.</td><td>4+</td></tr>
        <tr><td><strong>P-B-6</strong></td><td>Подрыв комплекса и периметра.</td><td>4+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-i" class="reveal">Протоколы P-I (вторжение) — УД 3+</h3>
    <div class="table-wrap reveal">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-I-1</strong></td><td>Уничтожение техники у комплекса.</td><td>3+</td></tr>
        <tr><td><strong>P-I-2</strong></td><td>Блокировка мест взлома.</td><td>3+</td></tr>
        <tr><td><strong>P-I-3</strong></td><td>Уничтожение персонала в зоне.</td><td>4+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-e" class="reveal">Протоколы P-E (пожаротушение) — УД 3+</h3>
    <div class="table-wrap reveal">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-E-1</strong></td><td>Тушение в одной комнате; нет угрозы жизни.</td><td>3+</td></tr>
        <tr><td><strong>P-E-2</strong></td><td>Тушение в одной комнате; есть угроза.</td><td>3+</td></tr>
        <tr><td><strong>P-E-3</strong></td><td>Тушение в одной комнате; угроза взрыва.</td><td>3+</td></tr>
        <tr><td><strong>P-E-4</strong></td><td>Тушение в нескольких комнатах; нет угрозы.</td><td>3+</td></tr>
        <tr><td><strong>P-E-5</strong></td><td>Тушение в нескольких комнатах; есть угроза.</td><td>3+</td></tr>
        <tr><td><strong>P-E-6</strong></td><td>Тушение в целой зоне; большая угроза.</td><td>4+</td></tr>
        <tr><td><strong>P-E-7</strong></td><td>Тушение в КС SCP «Безопасный».</td><td>3+</td></tr>
        <tr><td><strong>P-E-8</strong></td><td>Тушение в КС SCP «Евклид».</td><td>3+</td></tr>
        <tr><td><strong>P-E-9</strong></td><td>Тушение в КС SCP «Кетер».</td><td>4+</td></tr>
      </table>
    </div>

    <h3 id="prot-kir" class="reveal">Изоляционные коды (КИР)</h3>
    <div class="table-wrap reveal">
      <table class="data-table">
        <tr><th>Код</th><th>Значение</th></tr>
        <tr><td><strong>Чёрный</strong></td><td>Полная изоляция комплекса. <span class="critical">Эвакуация запрещена!</span></td></tr>
        <tr><td><strong>Серый</strong></td><td>Внутренняя угроза.</td></tr>
        <tr><td><strong>Белый</strong></td><td>Внешнее вторжение.</td></tr>
        <tr><td><strong>Суперсиний</strong></td><td>Побег разумного SCP (высокий интеллект).</td></tr>
        <tr><td><strong>Синий</strong></td><td>Побег разумного SCP.</td></tr>
        <tr><td><strong>Красный</strong></td><td>Агрессивная сущность.</td></tr>
        <tr><td><strong>Зелёный</strong></td><td>Био-угроза.</td></tr>
        <tr><td><strong>Пурпурный</strong></td><td>Экстрамерная угроза.</td></tr>
        <tr><td><strong>Жёлтый</strong></td><td>Меметическая угроза.</td></tr>
        <tr><td><strong>Чистый</strong></td><td>НОУС — известная сущность, неизвестно какая.</td></tr>
        <tr><td><strong>Суперчистый</strong></td><td>Неизвестная аномальная угроза.</td></tr>
        <tr><td><strong>Хладное серебро</strong></td><td>Фатальный сбой Фонда.</td></tr>
        <tr><td><strong>Розовый</strong></td><td>Дополнительный код.</td></tr>
      </table>
    </div>

    <hr class="divider">

    <!-- ПРИВИЛЕГИИ -->
    <h2 id="privileges" class="reveal">⭐ Раздел VI. Правила привилегий и администрации</h2>
    <p class="reveal">Администрация сервера — это <strong>лицо проекта</strong>.</p>

    <div class="alert alert-danger reveal">
      <strong>⛔ ВАЖНО:</strong> Нарушение правил привилегий = понижение, ЧСА или снятие.
    </div>

    <div class="two-col-grid">
      <div class="priv-card reveal-left" id="priv-obligations">
        <h4>✅ Что ОБЯЗАН делать админ</h4>
        <ul>
          <li>Быть активным (3–4 раза в неделю).</li>
          <li>Знать правила наизусть.</li>
          <li>Реагировать на жалобы.</li>
          <li>Использовать команды по назначению.</li>
          <li>Быть вежливым.</li>
          <li>Помогать новичкам.</li>
          <li>Соблюдать иерархию.</li>
          <li>Фиксировать наказания.</li>
        </ul>
      </div>

      <div class="priv-card reveal-right" id="priv-forbidden" style="border-color:#ff0000;">
        <h4 style="color:#ff6666;">❌ Что ЗАПРЕЩЕНО админу</h4>
        <ul>
          <li>Оскорблять игроков или коллег.</li>
          <li>Злоупотреблять полномочиями.</li>
          <li>Игнорировать игроков.</li>
          <li>Читерить или использовать софт.</li>
          <li>Использовать команды в личных целях.</li>
          <li>Сливать информацию из админ-чата.</li>
          <li>Кормить читеров.</li>
          <li>Создавать конфликты на публике.</li>
          <li>Отсутствовать 7+ дней.</li>
        </ul>
      </div>

      <div class="priv-card reveal-left" id="priv-lies" style="border-color:#ffaa00;">
        <h4 style="color:#ffaa00;">⚠️ Наказания за враньё</h4>
        <ul>
          <li><strong>1-е:</strong> строгий выговор.</li>
          <li><strong>2-е:</strong> временный ЧСА (3–7 дней).</li>
          <li><strong>3-е:</strong> понижение или пожизненный ЧСА.</li>
        </ul>
      </div>

      <div class="priv-card reveal-right" id="priv-confidential" style="border-color:#ff0000;">
        <h4 style="color:#ff6666;">🚫 Конфиденциальность переписок</h4>
        <ul>
          <li>Запрещено публиковать скриншоты админ-чата.</li>
          <li>Запрещено пересылать личные сообщения.</li>
          <li>Запрещено рассказывать игрокам об обсуждениях.</li>
          <li><strong>Даже для обжалования</strong> нельзя показывать переписки.</li>
          <li><strong>Наказание:</strong> ПОЖИЗНЕННЫЙ ЧСА.</li>
        </ul>
      </div>

      <div class="priv-card reveal-left" id="priv-others" style="border-color:#9013fe;">
        <h4 style="color:#c07aff;">🛡️ Админство на других серверах</h4>
        <ul>
          <li>Запрещено быть админом на других серверах.</li>
          <li>Конфликт интересов.</li>
          <li><strong>Наказание:</strong> пожизненный ЧСА.</li>
        </ul>
      </div>

      <div class="priv-card reveal-right" id="priv-hierarchy" style="border-color:#00ff88;">
        <h4>👑 Иерархия должностей</h4>
        <ul>
          <li><strong>Высший состав:</strong> Владелец, Со-владелец, Гл. Админ, Зам., HR, Dev.</li>
          <li><strong>Кураторы:</strong> Ст. куратор и кураторы отделов.</li>
          <li><strong>Ивент-отдел:</strong> Гл. ивентолог, ивентолог.</li>
          <li><strong>Администраторы:</strong> Ст. админ, админ, мл. админ.</li>
          <li><strong>Модераторы:</strong> Ст. модер, модер, мл. модер.</li>
          <li><strong>Помощники:</strong> Ст. помощник, помощник, мл. помощник.</li>
          <li><strong>Стажёры:</strong> Ст. стажёр, стажёр, кандидат, испытательный.</li>
          <li><strong>Контент-мейкеры:</strong> Гл. КМ, ст. КМ, КМ, видео-оператор, стример, летсплейщик.</li>
        </ul>
      </div>

      <div class="priv-card reveal-left" id="priv-punish" style="border-color:#f5a623;">
        <h4 style="color:#f5a623;">⚖️ Виды взысканий</h4>
        <ul>
          <li><strong>Выговор устный</strong> — мелкие нарушения.</li>
          <li><strong>Выговор письменный</strong> — грубые или повторные.</li>
          <li><strong>Временный ЧСА</strong> — систематические (3–30 дней).</li>
          <li><strong>Понижение</strong> — неисполнение обязанностей.</li>
          <li><strong>Пожизненный ЧСА</strong> — за читерство, слив, оскорбления, враньё (3+), админство на других.</li>
        </ul>
      </div>

      <div class="priv-card reveal-right" id="priv-rights" style="border-color:#00ccff;">
        <h4 style="color:#00ccff;">📋 Права администрации</h4>
        <ul>
          <li>Право на ошибку, если готов её признать.</li>
          <li>Право на защиту своей позиции.</li>
          <li>Право обратиться к старшему или владельцу.</li>
          <li>Право на апелляцию наказания.</li>
        </ul>
      </div>
    </div>

    <hr class="divider">

    <!-- ФОРМА -->
    <h2 id="uniform" class="reveal">👔 Раздел VII. Что можно носить и делать</h2>

    <div class="two-col-grid">
      <div class="reveal-left">
        <h3>✅ Что можно носить сотрудникам</h3>
        <div class="table-wrap">
          <table class="data-table">
            <tr><th>Должность</th><th>Разрешено</th></tr>
            <tr><td><strong>Уборщики</strong></td><td>Спецодежда, перчатки, фонарь, пропуск 1 УД</td></tr>
            <tr><td><strong>Капрал СБ</strong></td><td>Форма СБ, дубинка, FSP-9, бронежилет</td></tr>
            <tr><td><strong>Мл. НС / Инженер</strong></td><td>Халат, очки, планшет, инструменты</td></tr>
            <tr><td><strong>Сержант / Лейтенант СБ</strong></td><td>Форма СБ, CrossVec, бронежилет, наручники</td></tr>
            <tr><td><strong>Ст. НС / НС</strong></td><td>Халат, очки, планшет, пропуск 3 УД</td></tr>
            <tr><td><strong>Директор / ГСБ / ГНС</strong></td><td>Официальная форма, Revolver, пропуск 4 УД</td></tr>
            <tr><td><strong>Совет О5 / КпЭ</strong></td><td>Официальная форма, Revolver, полный допуск</td></tr>
            <tr><td><strong>Капитан МОГ</strong></td><td>Тактическая форма, MTF E-11 SR, пропуск 4 УД</td></tr>
          </table>
        </div>
      </div>

      <div class="reveal-right">
        <h3>❌ Что носить ЗАПРЕЩЕНО</h3>
        <div class="alert alert-danger">
          <ul>
            <li>Одежда, не соответствующая роли (FailRP).</li>
            <li>Оружие, не входящее в экипировку роли.</li>
            <li>Маски, скрывающие лицо (кроме СБ и SCP-049).</li>
            <li>Уникальные предметы SCP без допуска.</li>
            <li>Чужие ключ-карты.</li>
            <li>Аксессуары, нарушающие RP.</li>
          </ul>
        </div>
      </div>
    </div>

    <hr class="divider">

    <!-- ПРЕДМЕТЫ И АРЕСТ -->
    <h2 id="items" class="reveal">🎒 Раздел VIII. Предметы, арест и расстрел</h2>
    <p class="reveal">Правила о том, что можно носить, что нельзя, и какие меры применяются к нарушителям.</p>

    <h3 id="items-can" class="reveal">✅ Что можно носить персоналу</h3>
    <div class="two-col-grid">
      <div class="item-card item-yes reveal-scale">
        <h4>🧪 Учёные (УД 2-3)</h4>
        <ul>
          <li>Аптечки (Medkit)</li>
          <li>Обезболивающие (Painkillers)</li>
          <li>Рация</li>
          <li>Ключ-карта строго своего УД</li>
          <li>Фонарь, планшет, очки</li>
        </ul>
      </div>

      <div class="item-card item-yes reveal-scale">
        <h4>🛡️ Охрана и МОГ (УД 2-4)</h4>
        <ul>
          <li>Штатное оружие (MTF E-11 SR, CrossVec, FSP-9, FR-MG-0, AK, Logicer)</li>
          <li>Дубинка/шокер</li>
          <li>Бронежилет</li>
          <li>Рация</li>
          <li>Наручники</li>
          <li>Аптечки и гранаты (по ситуации)</li>
        </ul>
      </div>

      <div class="item-card item-yes reveal-scale">
        <h4>⚙️ Инженеры (УД 2)</h4>
        <ul>
          <li>Инструменты (Toolkit)</li>
          <li>Оборудование для генераторов</li>
          <li>Ключ-карта 2 УД</li>
          <li>Рация, фонарь</li>
        </ul>
      </div>

      <div class="item-card item-yes reveal-scale">
        <h4>🧹 Класс D и уборщики (УД 1)</h4>
        <ul>
          <li>Метла и ведро (только уборщики)</li>
          <li>Фонарь</li>
          <li>Ключ-карта 1 УД (Janitor)</li>
          <li><strong>Больше ничего!</strong></li>
        </ul>
      </div>
    </div>

    <h3 id="items-cant" class="reveal">❌ Что носить ЗАПРЕЩЕНО</h3>
    <div class="two-col-grid">
      <div class="item-card item-no reveal-scale">
        <h4>🚫 Общие запреты (для всех)</h4>
        <ul>
          <li><strong>Карта выше своего уровня допуска</strong></li>
          <li>Чужие ключ-карты</li>
          <li>Оружие не по экипировке роли</li>
          <li>Компоненты боеголовки</li>
          <li>SCP-предметы без допуска</li>
          <li>SCP-018 (мяч)</li>
          <li>Micro H.I.D. и 3-X Particle Disruptor (кроме МОГ и офицеров)</li>
          <li>Маски, скрывающие лицо</li>
        </ul>
      </div>

      <div class="item-card item-no reveal-scale">
        <h4>🚫 Для класса D и уборщиков</h4>
        <ul>
          <li>Любое огнестрельное оружие</li>
          <li>Гранаты и взрывчатка</li>
          <li>Карты выше 1 УД</li>
          <li>Бронежилеты МОГ</li>
          <li>SCP-предметы</li>
          <li>Компоненты боеголовки</li>
          <li>SCP-500 и SCP-268</li>
        </ul>
      </div>

      <div class="item-card item-no reveal-scale">
        <h4>🚫 Для учёных</h4>
        <ul>
          <li>Тяжёлое оружие (MTF E-11 SR, Logicer, FR-MG-0, AK)</li>
          <li>Гранаты (кроме успокоительных)</li>
          <li>Карты 5 УД</li>
          <li>Бронежилеты МОГ</li>
          <li>Компоненты боеголовки</li>
          <li><strong>SCP-500</strong></li>
          <li>SCP-268</li>
        </ul>
      </div>

      <div class="item-card item-no reveal-scale">
        <h4>🚫 Для охраны</h4>
        <ul>
          <li>SCP-предметы без допуска</li>
          <li>Компоненты боеголовки</li>
          <li>Карты 5 УД</li>
          <li>Оружие не по экипировке СБ</li>
          <li>Предметы, украденные у МОГ</li>
        </ul>
      </div>
    </div>

    <h3 id="items-arrest" class="reveal">🚨 Арест персонала</h3>
    <p class="reveal">Арест — временное помещение сотрудника под стражу с последующим <strong>выводом на эвакуацию</strong> (удаление из Участка).</p>

    <div class="two-col-grid">
      <div class="item-card item-arrest reveal-left">
        <h4>⚠️ Арест + вывод на эвакуацию</h4>
        <p style="color:#ffaa00; font-size:.9em;">При обнаружении запрещённых предметов сотрудник СБ обязан:</p>
        <ul>
          <li>Обнаружено <strong>запрещённое оружие</strong> (не по экипировке).</li>
          <li>Обнаружена <strong>карта выше уровня допуска</strong>.</li>
          <li>Обнаружены <strong>компоненты боеголовки</strong>.</li>
          <li>Обнаружены <strong>SCP-предметы</strong> без допуска.</li>
          <li>Обнаружены <strong>чужие ключ-карты</strong>.</li>
          <li>Обнаружены <strong>запрещённые маски</strong>.</li>
        </ul>
        <p style="margin-top:10px; color:#88ffbb;"><strong>Действия:</strong></p>
        <ol>
          <li>Задержать сотрудника.</li>
          <li>Изъять запрещённые предметы.</li>
          <li>Провести допрос с объяснением причин.</li>
          <li><strong>Вывести на эвакуацию</strong> (удалить с Участка).</li>
        </ol>
      </div>

      <div class="item-card item-arrest reveal-right">
        <h4>🚨 Серьёзные нарушения</h4>
        <ul>
          <li>Проникновение в запрещённые зоны.</li>
          <li>Нападение на сотрудника СБ.</li>
          <li>Помощь Классу D в побеге.</li>
          <li>Саботаж оборудования.</li>
          <li>Попытка побега из Участка.</li>
          <li>Сотрудничество с ПХ.</li>
        </ul>
        <p style="margin-top:10px; color:#88ffbb;"><strong>Действия:</strong></p>
        <ol>
          <li>Задержать сотрудника.</li>
          <li>Провести допрос под стражей.</li>
          <li>Вывести на эвакуацию.</li>
          <li>При сопротивлении — разрешено применение силы.</li>
        </ol>
      </div>
    </div>

    <h3 id="items-execute" class="reveal">💀 Расстрел класса D</h3>
    <div class="two-col-grid">
      <div class="item-card item-execute reveal-left">
        <h4>🛑 Расстрел на месте (без ареста)</h4>
        <p style="color:#ff6666;">Класс D подлежит немедленному расстрелу при:</p>
        <ul>
          <li>Нападении на охрану или персонал.</li>
          <li>Завладении огнестрельным оружием.</li>
          <li>Попытке побега за пределы Участка.</li>
          <li>Попытке убийства учёного.</li>
          <li>Организации бунта.</li>
          <li>Умышленном саботаже оборудования.</li>
          <li>Любой угрозе жизни персонала.</li>
        </ul>
      </div>

      <div class="item-card item-execute reveal-right">
        <h4>⚠️ Важно для СБ и МОГ</h4>
        <ul>
          <li>Расстрел разрешён <strong>при ЛЮБОМ коде</strong>.</li>
          <li>Расстрел производится <strong>только при явной угрозе</strong>.</li>
          <li>При отсутствии угрозы — сначала предупреждение.</li>
          <li>Расстрел без причины = нарушение правил.</li>
          <li>Расстрел мирного класса D запрещён.</li>
        </ul>
      </div>
    </div>

    <div class="alert alert-info reveal">
      <strong>💡 Права задержанного (персонал):</strong>
      <ul>
        <li>Узнать причину ареста.</li>
        <li>Дать объяснение в своё оправдание.</li>
        <li>Подать жалобу на действия СБ администрации.</li>
        <li>Быть выведенным на эвакуацию (а не убитым).</li>
        <li>На адвоката от учёных (для класса B и выше).</li>
      </ul>
    </div>

    <hr class="divider">

    <!-- ОБЩИЕ -->
    <h2 id="general" class="reveal">📜 Раздел IX. Общие правила</h2>
    <div class="two-col-grid">
      <div class="section reveal-left" style="margin:0;">
        <h3>9.1. Принципы сервера</h3>
        <p>Сервер <strong>MV.Project</strong> — <span class="highlight">Medium RP</span> проект.</p>
        <ul>
          <li>Уважение — основа сервера.</li>
          <li>Запрещена дискриминация.</li>
          <li>Запрещены угрозы в реальной жизни.</li>
          <li>Запрещена пропаганда терроризма.</li>
          <li>Запрещены атаки на сервер.</li>
        </ul>
      </div>

      <div class="section reveal-right" style="margin:0;">
        <h3>9.2. Возраст и аккаунты</h3>
        <ul>
          <li>Минимальный возраст — <span class="highlight">13 лет</span>.</li>
          <li>Обман по возрасту = перманентный бан.</li>
          <li>Запрещено несколько аккаунтов.</li>
          <li>Запрещена передача аккаунта.</li>
          <li>Обход бана = перманентный бан + IP-бан.</li>
        </ul>
      </div>
    </div>

    <hr class="divider">

    <!-- RP -->
    <h2 id="rp" class="reveal">🎭 Раздел X. RP-правила</h2>
    <div class="section reveal">
      <h3>10.1. Что такое RP?</h3>
      <p><strong>RP (Roleplay)</strong> — отыгрыш роли персонажа. Medium RP = играть роль без фанатизма.</p>

      <div class="two-col-grid">
        <div>
          <h4>❌ No RDM</h4>
          <ul>
            <li>Запрещено убивать без RP-причины.</li>
            <li>Наказание: бан 1–30 дней.</li>
          </ul>

          <h4>❌ No Teamkill</h4>
          <ul>
            <li>Запрещено убивать союзников.</li>
            <li>Наказание: бан от 3 дней.</li>
          </ul>

          <h4>❌ No Metagaming</h4>
          <ul>
            <li>Запрещено использовать внеигровую инфу.</li>
            <li>Наказание: бан от 3 дней.</li>
          </ul>
        </div>

        <div>
          <h4>❌ No Powergaming</h4>
          <ul>
            <li>Запрещены действия, невозможные в реальности.</li>
            <li>Наказание: бан от 3 дней.</li>
          </ul>

          <h4>❌ No Banhop</h4>
          <ul>
            <li>Запрещён баннихоп при побеге.</li>
            <li>Наказание: бан от 1 дня.</li>
          </ul>

          <h4>❌ No FailRP</h4>
          <ul>
            <li>Запрещено нарушать логику персонажа.</li>
            <li>Наказание: предупреждение или бан.</li>
          </ul>
        </div>
      </div>
    </div>

    <hr class="divider">

    <!-- ИГРОВЫЕ КЛАССЫ -->
    <h2 id="classes" class="reveal">👥 Раздел XI. Правила игровых классов</h2>

    <div class="two-col-grid">
      <div class="acc reveal-scale">
        <button class="acc-head" type="button"><span>🟠</span> Класс D <span class="acc-arrow">▶</span></button>
        <div class="acc-body"><div class="acc-inner">
          <ul>
            <li>Обязаны слушаться охрану.</li>
            <li>Запрещено бунтовать без RP-причины.</li>
            <li>Побег разрешён, но без Banhop.</li>
            <li>Запрещено мешать тестам.</li>
            <li>При КОДЕ КРАСНОМ+ разрешено всё для выживания.</li>
          </ul>
        </div></div>
      </div>

      <div class="acc reveal-scale">
        <button class="acc-head" type="button"><span>🔵</span> Учёные <span class="acc-arrow">▶</span></button>
        <div class="acc-body"><div class="acc-inner">
          <ul>
            <li>Обязаны проводить тесты SCP.</li>
            <li>Запрещено покидать Участок.</li>
            <li>Обязаны сотрудничать с МОГ.</li>
            <li>Запрещено давать Класс D предметы.</li>
          </ul>
        </div></div>
      </div>

      <div class="acc reveal-scale">
        <button class="acc-head" type="button"><span>🟢</span> Охрана Фонда <span class="acc-arrow">▶</span></button>
        <div class="acc-body"><div class="acc-inner">
          <ul>
            <li>Обязаны следить за порядком.</li>
            <li>Запрещено убивать Класс D без причины.</li>
            <li>Обязаны сопровождать учёных.</li>
            <li>При КОДЕ 3+ — защищать Участок.</li>
          </ul>
        </div></div>
      </div>

      <div class="acc reveal-scale">
        <button class="acc-head" type="button"><span>🔴</span> МОГ (NTF) <span class="acc-arrow">▶</span></button>
        <div class="acc-body"><div class="acc-inner">
          <ul>
            <li>Действуют по протоколу.</li>
            <li>Запрещено убивать учёных и охрану.</li>
            <li>Обязаны защищать Участок.</li>
            <li>При КОДЕ 4 — вернуть SCP в камеры.</li>
          </ul>
        </div></div>
      </div>

      <div class="acc reveal-scale">
        <button class="acc-head" type="button"><span>⚫</span> ПХ (Chaos Insurgency) <span class="acc-arrow">▶</span></button>
        <div class="acc-body"><div class="acc-inner">
          <ul>
            <li>Цель — освобождение SCP.</li>
            <li>Запрещён RDM.</li>
            <li>Запрещено убивать своих.</li>
            <li>Обязаны подчиняться командиру.</li>
          </ul>
        </div></div>
      </div>

      <div class="acc reveal-scale">
        <button class="acc-head" type="button"><span>🟣</span> SCP-объекты <span class="acc-arrow">▶</span></button>
        <div class="acc-body"><div class="acc-inner">
          <ul>
            <li>Обязаны отыгрывать свою роль.</li>
            <li>Запрещено фармить убийства.</li>
            <li>SCP-049 обязан лечить.</li>
            <li>Запрещено кемперить.</li>
          </ul>
        </div></div>
      </div>
    </div>

    <hr class="divider">

    <!-- SCP -->
    <h2 id="scp" class="reveal">🧬 Раздел XII. Правила SCP-объектов</h2>
    <p class="reveal">Подробная информация о каждом SCP: здоровье, разумность, способности, что можно и что нельзя.</p>

    <div class="two-col-grid">
      <div class="scp-card reveal-scale">
        <h4>🧱 SCP-173 — Статуя</h4>
        <div class="hp-badge">❤️ 10 000 HP</div>
        <p><strong>Разумность:</strong> ❌ Нет (автомат, не мыслит)</p>
        <p><strong>Способности:</strong></p>
        <ul>
          <li><strong>Скачок</strong> — телепорт до 8 м при зрительном контакте. Убивает ближайшего человека.</li>
          <li><strong>Лужа грязи</strong> — замедляет людей (F).</li>
          <li>Сопротивление пулям (кроме Micro H.I.D.).</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> двигаться при отсутствии зрительного контакта, оставлять лужи.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> телепортироваться при 3+ наблюдателях, убивать без RP-причины.</p>
        <p><strong>Наказание за нарушение:</strong> бан 7-30 дней.</p>
      </div>

      <div class="scp-card reveal-scale">
        <h4>🩺 SCP-049 — Чумной Доктор</h4>
        <div class="hp-badge">❤️ 5 000 HP</div>
        <p><strong>Разумность:</strong> ✅ Да (имеет интеллект, общается)</p>
        <p><strong>Способности:</strong></p>
        <ul>
          <li><strong>Сердечный приступ</strong> — атака наносит продолжительный урон.</li>
          <li><strong>Воскрешение</strong> — поднимает мёртвых как SCP-049-2 (зомби).</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> лечить, воскрешать зомби по RP-причине.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> убивать всех подряд, воскрешать без RP-причины.</p>
        <p><strong>Наказание за нарушение:</strong> бан 3-7 дней.</p>
      </div>

      <div class="scp-card reveal-scale">
        <h4>👴 SCP-106 — Старик</h4>
        <div class="hp-badge">❤️ 7 000 HP</div>
        <p><strong>Разумность:</strong> ✅ Да (имеет интеллект)</p>
        <p><strong>Способности:</strong></p>
        <ul>
          <li><strong>Захват</strong> — отправляет человека в карманное измерение.</li>
          <li><strong>Погружение</strong> — скрывается в полу (Shift).</li>
          <li>Сопротивление пулям, слаб к другим источникам урона.</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> захватывать людей по RP-причине, скрываться.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> отправлять в карманное измерение без RP-причины.</p>
        <p><strong>Наказание за нарушение:</strong> бан 3-7 дней.</p>
      </div>

      <div class="scp-card reveal-scale" style="border-color: #ffaa00;">
        <h4>😢 SCP-096 — Застенчивый</h4>
        <div class="evacuated-badge">🚨 ЭВАКУИРОВАН ИЗ УЧАСТКА 11</div>
        <p style="color:#ffcc66;"><strong>Статус:</strong> SCP-096 был <strong>эвакуирован из Участка 11</strong> и переведён в другой объект Фонда. На данном Участке не содержится и не появляется.</p>
        <p style="color:#ffcc66;"><strong>Причина:</strong> Угроза признана слишком высокой для содержания на Участке 11. Все правила и механики, связанные с SCP-096, <strong>временно отключены</strong>.</p>
        <p style="color:#ff8888;"><strong>Внимание:</strong> Если вы заметили SCP-096 на территории Участка — немедленно сообщите администрации. Это может быть баг или ивент.</p>
      </div>

      <div class="scp-card reveal-scale">
        <h4>👄 SCP-939 — Многоголосый</h4>
        <div class="hp-badge">❤️ 7 000 HP</div>
        <p><strong>Разумность:</strong> ⚠️ Полуразумный (умеет охотиться, но не мыслит)</p>
        <p><strong>Особенности:</strong></p>
        <ul>
          <li>Умеет <strong>охотиться</strong> на людей по звуку.</li>
          <li><strong>Не умеет думать</strong> — действует на инстинктах.</li>
          <li>Может <strong>только произносить звуки</strong> (имитирует голоса), но не понимает их смысла.</li>
          <li>Не способен к RP-диалогу — издаёт звуки для приманки.</li>
        </ul>
        <p><strong>Способности:</strong></p>
        <ul>
          <li><strong>Мимикрия</strong> — имитирует голоса людей.</li>
          <li><strong>Укус</strong> — 65 урона + амнезия (нельзя перезарядиться).</li>
          <li>Чувствительность к звуку (видит сквозь стены).</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> использовать звук для охоты, имитировать голоса.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> игнорировать правила, кемперить.</p>
        <p><strong>Наказание за нарушение:</strong> предупреждение / бан 1 день.</p>
      </div>

      <div class="scp-card reveal-scale">
        <h4>💀 SCP-3114 — Скелет</h4>
        <div class="hp-badge">❤️ 6 000 HP</div>
        <p><strong>Разумность:</strong> ✅ Да (маскируется под человека)</p>
        <p><strong>Способности:</strong></p>
        <ul>
          <li><strong>Скелеты в шкафу</strong> — снимает кожу с трупов, маскируется.</li>
          <li><strong>Удушение</strong> — захват человека.</li>
          <li>Может использовать предметы в облике.</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> маскироваться, общаться с людьми в облике.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> быстро раскрываться, убивать без RP-причины.</p>
        <p><strong>Наказание за нарушение:</strong> бан 1-3 дня.</p>
      </div>

      <div class="scp-card reveal-scale">
        <h4>💻 SCP-079 — Старый ИИ</h4>
        <div class="hp-badge">❤️ 0 HP (уязвим к перегрузке)</div>
        <p><strong>Разумность:</strong> ✅ Да (искусственный интеллект)</p>
        <p><strong>Способности:</strong></p>
        <ul>
          <li>Управление дверями, лифтами, тесла-воротами.</li>
          <li>Громкоговоритель, блокировка дверей.</li>
          <li>Видит людей с SCP-268.</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> помогать другим SCP, управлять системами.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> игнорировать просьбы других SCP.</p>
        <p><strong>Наказание за нарушение:</strong> предупреждение / бан 1 день.</p>
      </div>

      <div class="scp-card reveal-scale" id="scp953">
        <h4>🦊 SCP-953 — Полиморфная рептилия</h4>
        <div class="hp-badge">❤️ 1 600 HP</div>
        <p><strong>Разумность:</strong> ✅ Да (лис-оборотень)</p>
        <p><strong>Способности:</strong></p>
        <ul>
          <li>Принимает облик человека.</li>
          <li>Невидимость в облике.</li>
          <li>Атаки в ближнем бою.</li>
        </ul>
        <p style="color:#88ffbb;"><strong>Можно:</strong> использовать облик для RP.</p>
        <p style="color:#ff6666;"><strong>Нельзя:</strong> использовать облик для RDM, заманивать в ловушки.</p>
        <p><strong>Наказание за нарушение:</strong> бан 7-14 дней.</p>
      </div>
    </div>

    <hr class="divider">

    <!-- SCP-914 -->
    <h2 id="scp914" class="reveal">⚙️ Раздел XIII. Правила SCP-914</h2>
    <div class="two-col-grid">
      <div class="section reveal-left" style="margin:0;">
        <h3>Правила использования</h3>
        <ul>
          <li>Запрещено использование 914 без RP-причины.</li>
          <li>Запрещено превращение в SCP-049-2 без RP-причины.</li>
          <li>Запрещено использование 914 для обхода правил.</li>
          <li>Обязательно соблюдать очередь.</li>
          <li>Запрещено закидывание людей на смертельные режимы.</li>
        </ul>
      </div>

      <div class="reveal-right">
        <h3>Режимы 914</h3>
        <div class="table-wrap">
          <table class="data-table">
            <tr><th>Режим</th><th>Эффект</th><th>ОК?</th></tr>
            <tr><td><strong>Rough</strong></td><td>Ломает предметы</td><td>Да</td></tr>
            <tr><td><strong>Coarse</strong></td><td>Может ухудшить</td><td>Да</td></tr>
            <tr><td><strong>1:1</strong></td><td>Обмен</td><td>Да</td></tr>
            <tr><td><strong>Fine</strong></td><td>Улучшение</td><td>Да</td></tr>
            <tr><td><strong>Very Fine</strong></td><td>SCP-049-2</td><td>Только по RP</td></tr>
          </table>
        </div>
      </div>
    </div>

    <hr class="divider">

    <!-- ИНТЕРКОМ -->
    <h2 id="intercom" class="reveal">📢 Раздел XIV. Правила интеркома и чата</h2>

    <div class="alert alert-info reveal">
      <strong>📢 Формат сообщения в интеркоме:</strong>
      <p>«[Имя/Позывной], [Уровень допуска], [Класс персонала], [Что требуется]».</p>
      <ul>
        <li><strong>Пример 1:</strong> «Говорит СБ-Капрал Иванов, 2 УД, класс C. Требуется подкрепление в ЛЗС».</li>
        <li><strong>Пример 2:</strong> «Говорит НС Петров, 3 УД, класс B. Побег SCP-173, КОД СИНИЙ».</li>
        <li><strong>Пример 3:</strong> «Говорит Капитан МОГ, 4 УД, класс B. Объявляю КОД КРАСНЫЙ».</li>
      </ul>
    </div>

    <div class="two-col-grid">
      <div class="reveal-left">
        <h3>Запрещено в интеркоме</h3>
        <div class="alert alert-danger">
          <ul>
            <li>Спам и троллинг.</li>
            <li>Музыка без RP-причины.</li>
            <li>Крики, оскорбления.</li>
            <li>Личные разговоры.</li>
            <li>Перебивание говорящего.</li>
            <li>Ложные коды.</li>
          </ul>
        </div>
      </div>

      <div class="reveal-right">
        <h3>Наказания за интерком</h3>
        <div class="table-wrap">
          <table class="data-table">
            <tr><th>Нарушение</th><th>1-е</th><th>2-е</th><th>3-е</th></tr>
            <tr><td>Спам</td><td>Мут 1 ч</td><td>Мут 6 ч</td><td>Бан 1 день</td></tr>
            <tr><td>Музыка</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
            <tr><td>Ложный код</td><td colspan="3">Повод для РП (НЕ бан)</td></tr>
            <tr><td>Оскорбления</td><td>Мут 6 ч</td><td>Бан 1 день</td><td>Бан 7 дней</td></tr>
          </table>
        </div>
      </div>
    </div>

    <h3 id="chat" class="reveal">Правила чата</h3>
    <div class="two-col-grid">
      <div class="section reveal-left" style="margin:0;">
        <h4>Текстовый чат</h4>
        <ul>
          <li>Запрещён спам (более 3 сообщений).</li>
          <li>Запрещён флуд.</li>
          <li>Запрещены оскорбления.</li>
          <li>Запрещён Caps Lock.</li>
          <li>Запрещена реклама серверов.</li>
          <li>Запрещена политика и религия.</li>
        </ul>
      </div>

      <div class="section reveal-right" style="margin:0;">
        <h4>Голосовой чат</h4>
        <ul>
          <li>Запрещены громкие звуки.</li>
          <li>Запрещён Soundpad.</li>
          <li>Запрещён спам.</li>
          <li>Запрещено перебивать.</li>
          <li>Рация — только для RP.</li>
        </ul>
      </div>
    </div>

    <hr class="divider">

    <!-- БАНЫ -->
    <h2 id="bans" class="reveal">⏱️ Раздел XV. Сроки наказаний</h2>
    <div class="table-wrap reveal">
      <table class="data-table">
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
      </table>
    </div>

    <div class="alert alert-warning reveal">
      <strong>⚠️ Примечание:</strong> Рецидивы = удвоение срока.
    </div>

    <hr class="divider">

    <!-- АПЕЛЛЯЦИЯ -->
    <h2 id="appeal" class="reveal">📩 Раздел XVI. Процедура апелляции</h2>
    <div class="two-col-grid">
      <div class="section reveal-left" style="margin:0;">
        <h3>Как подать апелляцию</h3>
        <ol>
          <li>Зайди на Discord-сервер.</li>
          <li>Перейди в канал <strong>#апелляции</strong>.</li>
          <li>Создай тикет по шаблону.</li>
          <li>Укажи SteamID, причину бана и объяснение.</li>
        </ol>

        <h3>Сроки рассмотрения</h3>
        <ul>
          <li>Обычная апелляция — до 24 часов.</li>
          <li>Сложная — до 72 часов.</li>
          <li>Перманентный бан — до 7 дней.</li>
        </ul>

        <h3>Связь с администрацией</h3>
        <p>Вся связь с администрацией осуществляется <strong>только через Discord-сервер</strong> проекта.</p>
        <p style="color:#ffcc66;">Не пишите в личные сообщения — там ваши обращения могут быть проигнорированы.</p>
      </div>

      <div class="reveal-right">
        <h3>Правила апелляции</h3>
        <div class="alert alert-danger">
          <ul>
            <li>Запрещено оскорблять администрацию.</li>
            <li>Запрещено дублировать апелляции.</li>
            <li>Запрещено подавать с другого аккаунта.</li>
            <li>Решение окончательное.</li>
            <li>Без доказательств — последняя очередь.</li>
          </ul>
        </div>

        <h3>Шаблон апелляции</h3>
        <div class="section" style="margin:0; padding:15px;">
          <p><strong>SteamID:</strong> [ваш ID]</p>
          <p><strong>Причина бана:</strong> [причина]</p>
          <p><strong>Кто забанил:</strong> [ник]</p>
          <p><strong>Объяснение:</strong> [почему несправедлив]</p>
          <p><strong>Доказательства:</strong> [ссылка]</p>
        </div>
      </div>
    </div>

    <hr class="divider">

    <div class="alert alert-info reveal">
      <strong>💡 Помни:</strong> Соблюдение правил — залог комфортной игры для всех.
    </div>

    <div class="center reveal">
      <a href="https://discord.gg/ZCGAhTH6ep" class="discord">💬 ВСТУПИТЬ В DISCORD</a>
      <a href="https://t.me/mvprojectru" class="telegram">📢 TELEGRAM-КАНАЛ</a>
      <a href="https://www.youtube.com/@mebnes" class="youtube">▶ YOUTUBE-КАНАЛ</a>
    </div>

    <div class="footer">
      <p>© 2026 MV.PROJECT | SCP FOUNDATION | MEDIUM ROLEPLAY</p>
      <p>Документ №SCP-RP-01 «ЗАСЛОН» | Версия 3.3 | Обновлено: сентябрь 2026</p>
      <p style="margin-top: 15px; color: #333;">CLASSIFIED — LEVEL 5 CLEARANCE REQUIRED</p>
    </div>

  </main>

  <button class="to-top" id="toTop" aria-label="Наверх">↑</button>

  <script>
    /* ============ БОКОВОЕ МЕНЮ ============ */
    function toggleSection(el) {
      el.classList.toggle('open');
      const sub = el.nextElementSibling;
      if (sub) sub.classList.toggle('open');
    }

    document.querySelectorAll('.nav-sub a').forEach(link => {
      link.addEventListener('click', () => {
        if (window.innerWidth <= 900) {
          document.querySelector('.sidebar').classList.remove('open');
        }
      });
    });

    /* ============ АКТИВНЫЙ ПУНКТ МЕНЮ ============ */
    const navLinks = document.querySelectorAll('.nav-sub a');
    const sections = document.querySelectorAll('h2[id], h3[id]');

    function updateActiveLink() {
      let current = '';
      sections.forEach(sec => {
        const top = sec.offsetTop - 150;
        if (window.scrollY >= top) current = sec.getAttribute('id');
      });
      navLinks.forEach(link => {
        link.classList.toggle('active', link.getAttribute('href') === '#' + current);
      });
    }

    /* ============ ПРОГРЕСС + КНОПКА НАВЕРХ ============ */
    const progressBar = document.getElementById('scrollProgress');
    const toTop = document.getElementById('toTop');

    function onScroll() {
      const doc = document.documentElement;
      const scrolled = doc.scrollTop;
      const max = doc.scrollHeight - doc.clientHeight;
      const pct = max > 0 ? (scrolled / max) * 100 : 0;
      progressBar.style.width = pct + '%';
      toTop.classList.toggle('show', scrolled > 400);
      updateActiveLink();
    }

    let ticking = false;
    window.addEventListener('scroll', () => {
      if (!ticking) {
        requestAnimationFrame(() => { onScroll(); ticking = false; });
        ticking = true;
      }
    }, { passive: true });

    toTop.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    /* ============ REVEAL НА СКРОЛЛЕ ============ */
    (function initReveal() {
      const items = document.querySelectorAll('.reveal, .reveal-left, .reveal-right, .reveal-scale');
      if (!('IntersectionObserver' in window)) {
        items.forEach(i => i.classList.add('in'));
        return;
      }

      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (!entry.isIntersecting) return;
          const el = entry.target;
          const parent = el.parentElement;
          let delay = 0;
          if (parent) {
            const siblings = Array.from(parent.children).filter(c =>
              c.classList.contains('reveal') || c.classList.contains('reveal-left') ||
              c.classList.contains('reveal-right') || c.classList.contains('reveal-scale')
            );
            const idx = siblings.indexOf(el);
            if (idx > 0) delay = Math.min(idx * 70, 420);
          }
          setTimeout(() => el.classList.add('in'), delay);
          observer.unobserve(el);
        });
      }, { threshold: 0.12, rootMargin: '0px 0px -60px 0px' });

      items.forEach(i => observer.observe(i));
    })();

    /* ============ АККОРДЕОН ============ */
    document.querySelectorAll('.acc-head').forEach(head => {
      head.addEventListener('click', () => {
        const acc = head.parentElement;
        acc.classList.toggle('open');
      });
    });

    /* ============ ВОДЯНЫЕ ЗНАКИ ============
       Каждое MV.PROJECT — отдельный элемент.
       Отступы и по горизонтали, и по вертикали.
       Шахматное смещение нечётных рядов — чтобы не сливались. */
    (function createWatermarks() {
      const overlay = document.getElementById('watermark-overlay');
      const cols = 5;     // количество по горизонтали
      const rows = 9;     // количество по вертикали
      const text = 'MV.PROJECT';

      for (let i = 0; i < rows; i++) {
        for (let j = 0; j < cols; j++) {
          const wm = document.createElement('div');
          wm.className = 'wm';
          wm.textContent = text;

          // шахматное смещение нечётных рядов вправо на полшага
          const rowOffset = (i % 2 === 0) ? 0 : 10;

          // 5% отступ от левого края + шаг 20% по X + смещение
          wm.style.left = (5 + j * 20 + rowOffset) + '%';
          // 6% отступ от верхнего края + шаг 11% по Y
          wm.style.top  = (6 + i * 11) + '%';

          overlay.appendChild(wm);
        }
      }
    })();

    /* ============ ПАРАЛЛАКС-СЛОИ (LEVEL 5 убран с фона) ============ */
    (function fillParallaxLayers() {
      const backEl = document.getElementById('layer-back');
      const middleEl = document.getElementById('layer-middle');
      const frontEl = document.getElementById('layer-front');

      const backText = 'MV.PROJECT  MV.PROJECT  MV.PROJECT  MV.PROJECT';
      const middleText = 'SCP FOUNDATION  SCP FOUNDATION  SCP FOUNDATION';
      const frontText = ''; // передний слой пустой

      const linesCount = 80;
      let backHTML = '', middleHTML = '', frontHTML = '';
      for (let i = 0; i < linesCount; i++) {
        backHTML += '<div class="parallax-line">' + backText + '</div>';
        middleHTML += '<div class="parallax-line">' + middleText + '</div>';
        frontHTML += '<div class="parallax-line">' + frontText + '</div>';
      }
      backEl.innerHTML = backHTML;
      middleEl.innerHTML = middleHTML;
      frontEl.innerHTML = frontHTML;
    })();

    (function parallaxScroll() {
      const backEl = document.getElementById('layer-back');
      const middleEl = document.getElementById('layer-middle');
      const frontEl = document.getElementById('layer-front');

      let currentBack = 0, currentMiddle = 0, currentFront = 0;

      function animate() {
        const targetScroll = window.scrollY;
        currentBack   += (targetScroll * 0.15  - currentBack)   * 0.08;
        currentMiddle += (targetScroll * -0.10 - currentMiddle) * 0.08;
        currentFront  += (targetScroll * 0.25  - currentFront)  * 0.08;

        backEl.style.transform   = 'translateY(' + (-currentBack)   + 'px)';
        middleEl.style.transform = 'translateY(' + (-currentMiddle) + 'px)';
        frontEl.style.transform  = 'translateY(' + (-currentFront)  + 'px)';

        requestAnimationFrame(animate);
      }
      animate();
    })();

    /* ============ ПОИСК ============ */
    (function initSearch() {
      const searchBox = document.getElementById('searchBox');
      const searchInput = document.getElementById('searchInput');
      const searchResults = document.getElementById('searchResults');
      const searchClear = document.getElementById('searchClear');
      if (!searchBox || !searchInput) return;

      const index = [];
      document.querySelectorAll('h2[id], h3[id], h4').forEach(el => {
        const raw = el.textContent.trim().replace(/\s+/g, ' ');
        if (raw.length < 2) return;
        index.push({ el, raw, lower: raw.toLowerCase(), isSub: el.tagName !== 'H2' });
      });

      let activeIdx = -1;

      const escapeHTML = s => s.replace(/[&<>"']/g,
        c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));

      function highlight(raw, q) {
        const idx = raw.toLowerCase().indexOf(q);
        if (idx === -1) return escapeHTML(raw);
        return escapeHTML(raw.slice(0, idx)) +
               '<mark>' + escapeHTML(raw.slice(idx, idx + q.length)) + '</mark>' +
               escapeHTML(raw.slice(idx + q.length));
      }

      function render(query) {
        const q = query.toLowerCase().trim();
        searchResults.innerHTML = '';
        activeIdx = -1;

        if (q.length < 2) { searchResults.classList.remove('show'); return; }

        const matches = index.filter(it => it.lower.includes(q)).slice(0, 30);

        if (matches.length === 0) {
          const empty = document.createElement('div');
          empty.className = 'search-empty';
          empty.innerHTML = 'Ничего не найдено по запросу <strong>' + escapeHTML(query) + '</strong>';
          searchResults.appendChild(empty);
          searchResults.classList.add('show');
          return;
        }

        matches.forEach((item, i) => {
          const a = document.createElement('div');
          a.className = 'search-item';
          a.dataset.idx = i;
          const tag = item.isSub ? 'Подраздел' : 'Раздел';
          a.innerHTML = '<span class="search-tag">' + tag + '</span>' + highlight(item.raw, q);
          a.addEventListener('click', () => { goTo(item.el); closeSearch(); });
          searchResults.appendChild(a);
        });
        searchResults.classList.add('show');
      }

      function goTo(el) {
        el.scrollIntoView({ behavior: 'smooth', block: 'start' });
        el.style.transition = 'background-color .4s, box-shadow .4s';
        el.style.backgroundColor = 'rgba(0,255,136,.15)';
        el.style.boxShadow = '0 0 30px rgba(0,255,136,.4)';
        setTimeout(() => {
          el.style.backgroundColor = '';
          el.style.boxShadow = '';
        }, 1400);
      }

      function closeSearch() {
        searchResults.classList.remove('show');
        searchInput.blur();
      }

      function updateActive() {
        const items = searchResults.querySelectorAll('.search-item');
        items.forEach((it, i) => it.classList.toggle('active', i === activeIdx));
        if (items[activeIdx]) items[activeIdx].scrollIntoView({ block: 'nearest' });
      }

      searchInput.addEventListener('input', () => {
        searchBox.classList.toggle('has-value', searchInput.value.length > 0);
        render(searchInput.value);
      });

      searchInput.addEventListener('keydown', e => {
        const items = searchResults.querySelectorAll('.search-item');
        if (e.key === 'Escape') { closeSearch(); return; }
        if (e.key === 'ArrowDown') {
          e.preventDefault();
          if (!items.length) return;
          activeIdx = (activeIdx + 1) % items.length; updateActive(); return;
        }
        if (e.key === 'ArrowUp') {
          e.preventDefault();
          if (!items.length) return;
          activeIdx = activeIdx <= 0 ? items.length - 1 : activeIdx - 1;
          updateActive(); return;
        }
        if (e.key === 'Enter') {
          e.preventDefault();
          const t = activeIdx >= 0 ? items[activeIdx] : items[0];
          if (t) t.click();
        }
      });

      searchClear.addEventListener('click', () => {
        searchInput.value = '';
        searchBox.classList.remove('has-value');
        searchResults.classList.remove('show');
        searchInput.focus();
      });

      document.addEventListener('click', e => {
        if (!searchBox.contains(e.target)) searchResults.classList.remove('show');
      });

      searchInput.addEventListener('focus', () => {
        if (searchInput.value.length >= 2) render(searchInput.value);
      });
    })();

    /* Первичный запуск */
    onScroll();
  </script>

</body>
</html>
