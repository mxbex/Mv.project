<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MV.Project | Устав Фонда SCP</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html, body { width: 100%; min-height: 100%; }
  body {
    font-family: 'Consolas', 'Courier New', monospace;
    background: #050505; color: #c0c0c0; line-height: 1.9;
    background-image: 
      radial-gradient(circle at 20% 30%, rgba(255, 0, 0, 0.05) 0%, transparent 40%),
      radial-gradient(circle at 80% 70%, rgba(0, 255, 136, 0.05) 0%, transparent 40%);
  }

  .sidebar {
    position: fixed; top: 0; left: 0;
    width: 290px; height: 100vh;
    background: #080808; border-right: 2px solid #00ff88;
    padding: 25px 0; overflow-y: auto; z-index: 1000;
    box-shadow: 5px 0 30px rgba(0,0,0,0.8);
  }
  .sidebar::-webkit-scrollbar { width: 6px; }
  .sidebar::-webkit-scrollbar-track { background: #0a0a0a; }
  .sidebar::-webkit-scrollbar-thumb { background: #00ff88; border-radius: 3px; }

  .sidebar-logo {
    padding: 0 25px 25px;
    border-bottom: 1px solid #1a1a1a;
    margin-bottom: 20px;
  }
  .sidebar-logo .name {
    font-size: 1.5em; font-weight: bold; letter-spacing: 3px;
    background: linear-gradient(90deg, #00ff88, #00cc66);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    display: block; margin-bottom: 8px;
  }
  .sidebar-logo .classif {
    display: inline-block; background: #ff0000; color: #fff;
    padding: 3px 10px; font-size: 0.65em; letter-spacing: 2px;
    font-weight: bold; animation: blink 2s infinite;
  }
  @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0.5; } }

  .sidebar-nav { padding: 0 12px; }
  .nav-section { margin-bottom: 3px; }
  .nav-section-header {
    display: flex; align-items: center; justify-content: space-between;
    color: #00ff88; text-decoration: none;
    padding: 10px 14px; margin: 2px 0; border-radius: 6px;
    font-size: 0.88em; letter-spacing: 1px; transition: 0.2s;
    border-left: 3px solid transparent;
    cursor: pointer; user-select: none;
  }
  .nav-section-header:hover {
    background: rgba(0,255,136,0.08);
    border-left-color: #00ff88;
  }
  .nav-section-header .arrow {
    font-size: 0.7em; transition: transform 0.2s; color: #00ff88;
  }
  .nav-section-header.open .arrow { transform: rotate(90deg); }
  .nav-section-header .label { flex: 1; margin-left: 8px; }

  .nav-sub {
    max-height: 0; overflow: hidden;
    transition: max-height 0.3s ease;
    padding-left: 10px;
    border-left: 1px dashed #1f1f1f;
    margin-left: 15px;
  }
  .nav-sub.open { max-height: 1000px; }
  .nav-sub a {
    display: block; color: #88bbaa; text-decoration: none;
    padding: 7px 14px; margin: 2px 0; border-radius: 5px;
    font-size: 0.78em; letter-spacing: 0.5px;
    transition: 0.2s; border-left: 2px solid transparent;
  }
  .nav-sub a:hover {
    background: rgba(0,255,136,0.06);
    color: #00ff88; border-left-color: #00cc66;
    padding-left: 18px;
  }
  .nav-sub a.active {
    background: rgba(0,255,136,0.1);
    color: #00ff88; border-left-color: #00ff88;
  }

  .main-content {
    margin-left: 290px;
    padding: 45px 40px;
    min-height: 100vh;
    width: calc(100% - 290px);
  }

  .menu-toggle {
    display: none; position: fixed;
    top: 15px; left: 15px; z-index: 1100;
    background: #00ff88; color: #000;
    border: none; padding: 10px 15px;
    border-radius: 6px; font-weight: bold;
    cursor: pointer; font-size: 1.2em;
  }
  @media (max-width: 900px) {
    .sidebar { transform: translateX(-100%); transition: 0.3s; }
    .sidebar.open { transform: translateX(0); }
    .main-content { margin-left: 0; padding: 70px 15px 30px; width: 100%; }
    .menu-toggle { display: block; }
  }

  .header { text-align: center; padding-bottom: 40px; border-bottom: 3px solid #00ff88; margin-bottom: 50px; }
  .classification {
    display: inline-block; background: #ff0000; color: #fff;
    padding: 8px 25px; font-weight: bold; letter-spacing: 4px;
    font-size: 0.9em; margin-bottom: 25px; animation: blink 2s infinite;
  }
  h1 {
    font-size: clamp(2em, 6vw, 4em);
    background: linear-gradient(90deg, #00ff88, #00cc66, #009944);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    letter-spacing: 5px; margin-bottom: 15px;
  }
  .subtitle { color: #00ff88; font-size: clamp(0.9em, 2vw, 1.2em); letter-spacing: 3px; }
  .codename { color: #666; font-size: 0.9em; margin-top: 15px; letter-spacing: 2px; }

  h2 {
    color: #00ff88; font-size: clamp(1.3em, 3vw, 1.9em);
    margin: 55px 0 25px; padding: 18px 0 18px 25px;
    border-left: 6px solid #00ff88;
    background: linear-gradient(90deg, rgba(0,255,136,0.12), transparent);
    letter-spacing: 2px; text-transform: uppercase;
    scroll-margin-top: 20px;
  }
  h3 {
    color: #66ffaa; font-size: clamp(1.05em, 2.2vw, 1.35em);
    margin: 35px 0 18px; padding-left: 18px;
    border-left: 4px solid #00cc66; letter-spacing: 1px;
    scroll-margin-top: 20px;
  }
  h4 { color: #88ffbb; font-size: 1.1em; margin: 25px 0 12px; letter-spacing: 1px; }

  p { margin: 12px 0; color: #b0b0b0; max-width: 65ch; }
  strong { color: #00ff88; }

  ul, ol { padding-left: 30px; margin: 18px 0; }
  li { padding: 8px 0 8px 10px; color: #b0b0b0; border-bottom: 1px dotted #1a1a1a; max-width: 70ch; }
  li:hover { color: #e0e0e0; }

  .two-col-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 30px;
    margin: 25px 0;
    width: 100%;
  }
  @media (max-width: 1200px) {
    .two-col-grid { grid-template-columns: 1fr; }
  }

  .data-table {
    width: 100%; border-collapse: collapse;
    background: #0a0a0a; border: 1px solid #1a1a1a;
    font-size: 0.92em;
    table-layout: auto;
  }
  .data-table th {
    background: #0f1a12; color: #00ff88; padding: 16px 18px;
    text-align: left; font-weight: bold; letter-spacing: 1px;
    border-bottom: 2px solid #00ff88;
    text-transform: uppercase; font-size: 0.85em;
  }
  .data-table td {
    padding: 14px 18px;
    border-bottom: 1px solid #1a1a1a;
    color: #c0c0c0; vertical-align: top;
    background: #0a0a0a;
    line-height: 1.7;
    max-width: 340px;
  }
  .data-table tr { background: #0a0a0a; }
  .data-table tr:hover,
  .data-table tr:hover td,
  .data-table tr:hover th {
    background: #0f0f0f; color: #e0e0e0;
  }
  .data-table strong { color: #00ff88; }
  .table-wrap {
    background: #0a0a0a;
    border-radius: 8px;
    overflow: hidden;
    margin: 20px 0;
    width: 100%;
  }

  .code-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 30px; margin: 35px 0;
    width: 100%;
  }
  @media (max-width: 1200px) {
    .code-grid { grid-template-columns: 1fr; }
  }
  .code-card {
    padding: 28px; border-radius: 10px; background: #0f0f0f;
    border: 2px solid; transition: 0.3s;
    position: relative; overflow: hidden;
  }
  .code-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.6); }
  .code-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px; }
  .code-card h4 { font-size: 1.4em; margin-bottom: 15px; letter-spacing: 3px; }
  .code-card p { font-size: 0.92em; color: #999; margin-bottom: 12px; max-width: 50ch; }
  .code-card ul { margin-top: 10px; font-size: 0.88em; }
  .code-card li { border-bottom: 1px dotted rgba(255,255,255,0.05); max-width: 50ch; }
  .code-red { border-color: #ff0000; background: linear-gradient(135deg, #0f0f0f, rgba(255,0,0,0.08)); }
  .code-red::before { background: #ff0000; }
  .code-red h4 { color: #ff0000; text-shadow: 0 0 15px rgba(255,0,0,0.5); }
  .code-black { border-color: #444; background: linear-gradient(135deg, #0f0f0f, rgba(50,50,50,0.15)); }
  .code-black::before { background: #444; }
  .code-black h4 { color: #999; text-shadow: 0 0 15px rgba(150,150,150,0.5); }
  .code-green { border-color: #00ff88; background: linear-gradient(135deg, #0f0f0f, rgba(0,255,136,0.08)); }
  .code-green::before { background: #00ff88; }
  .code-green h4 { color: #00ff88; text-shadow: 0 0 15px rgba(0,255,136,0.5); }
  .code-blue { border-color: #4a90d9; background: linear-gradient(135deg, #0f0f0f, rgba(74,144,217,0.08)); }
  .code-blue::before { background: #4a90d9; }
  .code-blue h4 { color: #4a90d9; text-shadow: 0 0 15px rgba(74,144,217,0.5); }
  .code-superblue { border-color: #00ccff; background: linear-gradient(135deg, #0f0f0f, rgba(0,204,255,0.08)); }
  .code-superblue::before { background: #00ccff; }
  .code-superblue h4 { color: #00ccff; text-shadow: 0 0 15px rgba(0,204,255,0.5); }
  .code-yellow { border-color: #ffcc00; background: linear-gradient(135deg, #0f0f0f, rgba(255,204,0,0.08)); }
  .code-yellow::before { background: #ffcc00; }
  .code-yellow h4 { color: #ffcc00; text-shadow: 0 0 15px rgba(255,204,0,0.5); }
  .code-orange { border-color: #ff8800; background: linear-gradient(135deg, #0f0f0f, rgba(255,136,0,0.08)); }
  .code-orange::before { background: #ff8800; }
  .code-orange h4 { color: #ff8800; text-shadow: 0 0 15px rgba(255,136,0,0.5); }
  .code-purple { border-color: #9013fe; background: linear-gradient(135deg, #0f0f0f, rgba(144,19,254,0.08)); }
  .code-purple::before { background: #9013fe; }
  .code-purple h4 { color: #9013fe; text-shadow: 0 0 15px rgba(144,19,254,0.5); }
  .code-white { border-color: #cccccc; background: linear-gradient(135deg, #0f0f0f, rgba(200,200,200,0.08)); }
  .code-white::before { background: #cccccc; }
  .code-white h4 { color: #dddddd; text-shadow: 0 0 15px rgba(200,200,200,0.4); }
  .code-gray { border-color: #888; background: linear-gradient(135deg, #0f0f0f, rgba(136,136,136,0.1)); }
  .code-gray::before { background: #888; }
  .code-gray h4 { color: #aaa; text-shadow: 0 0 15px rgba(150,150,150,0.5); }
  .code-clean { border-color: #e0e0e0; background: linear-gradient(135deg, #0f0f0f, rgba(224,224,224,0.06)); }
  .code-clean::before { background: #e0e0e0; }
  .code-clean h4 { color: #e0e0e0; text-shadow: 0 0 15px rgba(224,224,224,0.5); }
  .code-superclean { border-color: #ff69b4; background: linear-gradient(135deg, #0f0f0f, rgba(255,105,180,0.08)); }
  .code-superclean::before { background: #ff69b4; }
  .code-superclean h4 { color: #ff69b4; text-shadow: 0 0 15px rgba(255,105,180,0.5); }
  .code-silver { border-color: #c0c0c0; background: linear-gradient(135deg, #0f0f0f, rgba(192,192,192,0.08)); }
  .code-silver::before { background: #c0c0c0; }
  .code-silver h4 { color: #c0c0c0; text-shadow: 0 0 15px rgba(192,192,192,0.5); }

  .alert {
    padding: 22px 28px; border-radius: 8px; margin: 25px 0;
    border-left: 6px solid; font-size: 0.95em;
  }
  .alert p, .alert li { max-width: 65ch; }
  .alert-danger { background: rgba(255, 0, 0, 0.08); border-color: #ff0000; color: #ff8888; }
  .alert-warning { background: rgba(255, 170, 0, 0.08); border-color: #ffaa00; color: #ffcc66; }
  .alert-info { background: rgba(0, 255, 136, 0.05); border-color: #00ff88; color: #88ffbb; }

  .section {
    margin: 40px 0; padding: 32px;
    background: #0d0d0d; border-radius: 10px;
    border: 1px solid #1a1a1a;
  }
  .section p, .section li { max-width: 60ch; }

  .footer {
    text-align: center; margin-top: 70px; padding: 40px 20px;
    border-top: 2px solid #1a1a1a; color: #555;
    font-size: 0.85em; letter-spacing: 1px; background: #080808;
    border-radius: 10px;
  }
  .discord {
    display: inline-block; background: #5865F2; color: white;
    padding: 15px 40px; border-radius: 10px; text-decoration: none;
    font-weight: bold; margin: 10px; transition: 0.3s;
    letter-spacing: 2px; font-size: 1em;
  }
  .discord:hover { background: #4752c4; transform: scale(1.05); box-shadow: 0 0 40px rgba(88, 101, 242, 0.6); }
  .telegram {
    display: inline-block; background: #0088cc; color: white;
    padding: 15px 40px; border-radius: 10px; text-decoration: none;
    font-weight: bold; margin: 10px; transition: 0.3s;
    letter-spacing: 2px; font-size: 1em;
  }
  .telegram:hover { background: #006699; transform: scale(1.05); box-shadow: 0 0 40px rgba(0, 136, 204, 0.6); }
  .center { text-align: center; }
  details { background: #0d0d0d; border: 1px solid #1a1a1a; border-radius: 6px; margin: 12px 0; overflow: hidden; }
  details summary {
    padding: 18px 22px; cursor: pointer; color: #00ff88;
    font-weight: bold; letter-spacing: 1px; background: #0f0f0f;
    list-style: none; border-left: 5px solid #00ff88; transition: 0.2s;
  }
  details summary:hover { background: #141414; }
  details[open] summary { border-left-color: #ffaa00; color: #ffaa00; }
  details > *:not(summary) { padding: 18px 22px; }
  .highlight { background: rgba(0, 255, 136, 0.1); padding: 2px 8px; border-radius: 3px; color: #00ff88; }
  .critical { background: rgba(255, 0, 0, 0.15); padding: 2px 8px; border-radius: 3px; color: #ff6666; font-weight: bold; }
  .divider { height: 2px; background: linear-gradient(90deg, transparent, #00ff88, transparent); margin: 50px 0; border: none; }

  .clearance-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 30px; margin: 30px 0;
    width: 100%;
  }
  @media (max-width: 1200px) {
    .clearance-grid { grid-template-columns: 1fr; }
  }
  .clearance-card {
    padding: 28px; border-radius: 10px; border: 2px solid;
    background: #0f0f0f; transition: 0.3s;
  }
  .clearance-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.6); }
  .clearance-card h4 { font-size: 1.5em; margin-bottom: 15px; letter-spacing: 2px; }
  .clearance-card p { font-size: 0.9em; color: #999; max-width: 45ch; }
  .clearance-card ul { margin-top: 10px; font-size: 0.9em; }
  .clearance-card li { max-width: 45ch; }
  .level-1 { border-color: #666; }
  .level-1 h4 { color: #999; }
  .level-2 { border-color: #f5a623; }
  .level-2 h4 { color: #f5a623; }
  .level-3 { border-color: #d0021b; }
  .level-3 h4 { color: #d0021b; }
  .level-4 { border-color: #9013fe; }
  .level-4 h4 { color: #9013fe; }
  .level-5 { border-color: #00ff88; }
  .level-5 h4 { color: #00ff88; }
  .level-a { border-color: #ff0000; }
  .level-a h4 { color: #ff0000; }
  .level-b { border-color: #ff8800; }
  .level-b h4 { color: #ff8800; }
  .level-c { border-color: #00ccff; }
  .level-c h4 { color: #00ccff; }
  .level-d { border-color: #666; }
  .level-d h4 { color: #999; }
  .level-e { border-color: #9013fe; }
  .level-e h4 { color: #9013fe; }

  .priv-card {
    padding: 28px; border-radius: 10px;
    background: #0f0f0f;
    border: 2px solid #00ff88;
    transition: 0.3s;
  }
  .priv-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,255,136,0.15); }
  .priv-card h4 { color: #00ff88; font-size: 1.3em; margin-bottom: 15px; letter-spacing: 2px; }
  .priv-card p { font-size: 0.9em; color: #999; max-width: 45ch; }
  .priv-card ul { margin-top: 10px; font-size: 0.9em; }
  .priv-card li { max-width: 45ch; }

  .item-card {
    padding: 28px; border-radius: 10px;
    background: #0f0f0f;
    border: 2px solid;
    transition: 0.3s;
  }
  .item-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.6); }
  .item-card h4 { font-size: 1.3em; margin-bottom: 15px; letter-spacing: 2px; }
  .item-card ul { margin-top: 10px; font-size: 0.9em; }
  .item-card li { max-width: 45ch; }
  .item-yes { border-color: #00ff88; }
  .item-yes h4 { color: #00ff88; }
  .item-no { border-color: #ff0000; }
  .item-no h4 { color: #ff6666; }
  .item-arrest { border-color: #ffaa00; }
  .item-arrest h4 { color: #ffaa00; }
  .item-execute { border-color: #d0021b; }
  .item-execute h4 { color: #ff3333; }
</style>
</head>
<body>

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
        <div class="nav-sub">
          <a href="#codes">Все коды угроз</a>
        </div>
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
        <div class="nav-sub">
          <a href="#uniform">Что можно носить</a>
        </div>
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
        <div class="nav-sub">
          <a href="#general">Принципы и возраст</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>🎭</span><span class="label">RP</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#rp">Все RP-правила</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>👥</span><span class="label">КЛАССЫ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#classes">Игровые классы</a>
        </div>
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
        <div class="nav-sub">
          <a href="#scp914">Правила 914</a>
        </div>
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
        <div class="nav-sub">
          <a href="#bans">Сроки наказаний</a>
        </div>
      </div>

      <div class="nav-section">
        <div class="nav-section-header" onclick="toggleSection(this)">
          <span>📩</span><span class="label">АПЕЛЛЯЦИЯ</span><span class="arrow">▶</span>
        </div>
        <div class="nav-sub">
          <a href="#appeal">Процедура апелляции</a>
        </div>
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

    <div class="alert alert-danger">
      <strong>⛔ ВНИМАНИЕ:</strong> Данный устав обязателен к прочтению каждому сотруднику Участка. 
      Заходя на сервер <strong>MV.Project</strong>, вы автоматически соглашаетесь с правилами. 
      <span class="critical">Незнание правил не освобождает от ответственности.</span>
    </div>

    <!-- КОДЫ -->
    <h2 id="codes">🚨 Раздел I. Цветовые коды угроз</h2>
    <p>Коды угроз — стандартная система оповещения Фонда. Персонал обязан знать их значение.</p>

    <div class="alert alert-info">
      <strong>📢 Общие правила при ЛЮБОМ коде:</strong>
      <ul>
        <li>Персонал обязан слушаться <strong>СБ или любую МОГ</strong>.</li>
        <li>Разрешён <strong>расстрел класса D</strong> при угрозе жизни персонала.</li>
        <li><strong>Ложное объявление кода — НЕ повод для бана</strong>, это повод для интересного РП.</li>
      </ul>
    </div>

    <div class="code-grid">
      <div class="code-card code-green">
        <h4>🟢 КОД ЗЕЛЁНЫЙ</h4>
        <p><strong>Био-угроза / Заражение</strong></p>
        <p>Опасность, связанная с био-угрозой, инфекцией или источником заражения.</p>
        <p><strong>Указания:</strong> Избегайте контакта с источниками. Не покидайте Участок.</p>
        <p><strong>МОГ:</strong> Бета-7 «Шляпные болванчики»</p>
      </div>
      <div class="code-card code-blue">
        <h4>🔵 КОД СИНИЙ</h4>
        <p><strong>Побег разумного объекта</strong></p>
        <p>Побег объекта с интеллектом ниже человеческого.</p>
        <p><strong>Указания:</strong> Следуйте указаниям охраны.</p>
        <p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p>
      </div>
      <div class="code-card code-superblue">
        <h4>🔷 КОД СУПЕРСИНИЙ</h4>
        <p><strong>Побег разумного объекта (высокий интеллект)</strong></p>
        <p>Побег объекта с интеллектом, равным или превышающим человеческий.</p>
        <p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p>
      </div>
      <div class="code-card code-yellow">
        <h4>🟡 КОД ЖЁЛТЫЙ</h4>
        <p><strong>Меметическая / когнитивная угроза</strong></p>
        <p>Присутствие меметической или информационной угрозы.</p>
        <p><strong>МОГ:</strong> Эта-10, Эта-11</p>
      </div>
      <div class="code-card code-red">
        <h4>🔴 КОД КРАСНЫЙ</h4>
        <p><strong>Агрессивная сущность (АНС)</strong></p>
        <p>Побег опасной агрессивной сущности.</p>
        <p><strong>МОГ:</strong> Ню-7, Эта-5, Гамма-5</p>
      </div>
      <div class="code-card code-black">
        <h4>⚫ КОД ЧЁРНЫЙ</h4>
        <p><strong>Нарушение содержания НЛУ</strong></p>
        <p>Нарушение содержания Неликвидируемой Угрозы.</p>
        <p><strong>⚠️ ВАЖНО:</strong> <span class="critical">Эвакуация ЗАПРЕЩЕНА!</span> Код чёрный может быть и на SCP-106 — покидание комплекса смертельно опасно.</p>
        <p><strong>МОГ:</strong> Эпсилон-11, Сигма-23</p>
      </div>
      <div class="code-card code-white">
        <h4>⚪ КОД БЕЛЫЙ</h4>
        <p><strong>Вторжение сил захвата</strong></p>
        <p>Вторжение высокоорганизованных сил захвата.</p>
        <p><strong>МОГ:</strong> Все ММОГ уровня батальона</p>
      </div>
      <div class="code-card code-gray">
        <h4>🌫️ КОД СЕРЫЙ</h4>
        <p><strong>Внутренняя угроза</strong></p>
        <p>Аналог БЕЛОГО, но угроза изнутри Участка.</p>
        <p><strong>МОГ:</strong> Все ММОГ уровня батальона</p>
      </div>
      <div class="code-card code-purple">
        <h4>🟣 КОД ПУРПУРНЫЙ</h4>
        <p><strong>Экстрамерная угроза</strong></p>
        <p>Нарушения пространства, времени, причинности.</p>
        <p><strong>МОГ:</strong> Дзета-9, Лямбда-5, Мю-13</p>
      </div>
      <div class="code-card code-clean">
        <h4>⬜ КОД ЧИСТЫЙ</h4>
        <p><strong>НОУС</strong></p>
        <p>Нарушение Удержания Объекта Содержания — <strong>известная сущность, но неизвестно какая именно</strong>.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
      <div class="code-card code-superclean">
        <h4>💗 КОД СУПЕРЧИСТЫЙ</h4>
        <p><strong>Неизвестная аномальная угроза</strong></p>
        <p>Обозначает <strong>неизвестную аномальную угрозу</strong> (сама угроза не идентифицирована).</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
      <div class="code-card code-silver">
        <h4>🥈 КОД ХЛАДНОЕ СЕРЕБРО</h4>
        <p><strong>Фатальный сбой Фонда</strong></p>
        <p>Событие, ведущее к краху Фонда.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
    </div>

    <hr class="divider">

    <!-- ДОПУСК -->
    <h2 id="clearance">🔐 Раздел II. Уровни допуска персонала</h2>

    <div class="clearance-grid">
      <div class="clearance-card level-1">
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
      <div class="clearance-card level-2">
        <h4>УРОВЕНЬ 2</h4>
        <p><strong>Младший персонал</strong></p>
        <ul>
          <li>Капрал СБ</li>
          <li>Младший НС</li>
          <li>Инженер</li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: Лёгкая зона, подсобные помещения.</p>
        <p><strong>Протоколы:</strong> P-L-1, P-L-3, P-S-1.</p>
      </div>
      <div class="clearance-card level-3">
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
      <div class="clearance-card level-4">
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
      <div class="clearance-card level-5">
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
    <h2 id="classes-personnel">👤 Раздел III. Классы персонала</h2>

    <div class="clearance-grid">
      <div class="clearance-card level-a">
        <h4>КЛАСС A</h4>
        <p><strong>Стратегически важный персонал</strong></p>
        <ul>
          <li>Члены Совета О5</li>
          <li>Высшее руководство Фонда</li>
        </ul>
        <p><strong>Запрещено:</strong> Прямой доступ к аномалиям. Выход из защищённых зон.</p>
        <p><strong>Разрешено:</strong> Работа в защищённых зонах.</p>
      </div>
      <div class="clearance-card level-b">
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
      <div class="clearance-card level-c">
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
      <div class="clearance-card level-d">
        <h4>КЛАСС D</h4>
        <p><strong>Расходный персонал</strong></p>
        <ul>
          <li>Заключённые</li>
          <li>Испытуемые</li>
        </ul>
        <p><strong>Запрещено:</strong> Контакт с классами A и B. Побег.</p>
        <p><strong>Разрешено:</strong> Участие в тестах.</p>
      </div>
      <div class="clearance-card level-e">
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
    <h2 id="mtf">🛡️ Раздел IV. Мобильные Оперативные Группы (МОГ)</h2>

    <h3>Основные МОГ</h3>
    <div class="table-wrap">
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

    <h3 id="mtf-dop">Дополнительные МОГ</h3>
    <div class="table-wrap">
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

    <h3 id="mtf-tg">Тактические группы (ТГ)</h3>
    <div class="table-wrap">
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
    <h2 id="protocols">📋 Раздел V. Протоколы и изоляционные коды</h2>
    <p>Использование протоколов разрешено только персоналу с соответствующим уровнем допуска.</p>

    <h3 id="prot-p-l">Протоколы P-L (блокировка) — УД 2+</h3>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-L-1</strong></td><td>Блокировка гермо-ворот A и B.</td><td>2+</td></tr>
        <tr><td><strong>P-L-2</strong></td><td>Блокировка всех КПП.</td><td>3+</td></tr>
        <tr><td><strong>P-L-3</strong></td><td>Блокировка всех дверей.</td><td>2+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-s">Протоколы P-S (SCP) — УД 2+</h3>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-S-1</strong></td><td>Отслеживание SCP-объектов.</td><td>2+</td></tr>
        <tr><td><strong>P-S-2</strong></td><td>Отслеживание статуса SCP.</td><td>3+</td></tr>
        <tr><td><strong>P-S-3</strong></td><td>Активация тесла-ворот.</td><td>3+</td></tr>
        <tr><td><strong>P-S-4</strong></td><td>Сканирование комплекса.</td><td>3+</td></tr>
        <tr><td><strong>P-S-5</strong></td><td>Полный блэкаут комплекса.</td><td>3+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-b">Протоколы P-B (био-безопасность) — УД 3+</h3>
    <div class="table-wrap">
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

    <h3 id="prot-p-i">Протоколы P-I (вторжение) — УД 3+</h3>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Протокол</th><th>Описание</th><th>УД</th></tr>
        <tr><td><strong>P-I-1</strong></td><td>Уничтожение техники у комплекса.</td><td>3+</td></tr>
        <tr><td><strong>P-I-2</strong></td><td>Блокировка мест взлома.</td><td>3+</td></tr>
        <tr><td><strong>P-I-3</strong></td><td>Уничтожение персонала в зоне.</td><td>4+</td></tr>
      </table>
    </div>

    <h3 id="prot-p-e">Протоколы P-E (пожаротушение) — УД 3+</h3>
    <div class="table-wrap">
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

    <h3 id="prot-kir">Изоляционные коды (КИР)</h3>
    <div class="table-wrap">
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
    <h2 id="privileges">⭐ Раздел VI. Правила привилегий и администрации</h2>
    <p>Администрация сервера — это <strong>лицо проекта</strong>.</p>

    <div class="alert alert-danger">
      <strong>⛔ ВАЖНО:</strong> Нарушение правил привилегий = понижение, ЧСА или снятие.
    </div>

    <div class="two-col-grid">
      <div class="priv-card" id="priv-obligations">
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

      <div class="priv-card" id="priv-forbidden" style="border-color:#ff0000;">
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

      <div class="priv-card" id="priv-lies" style="border-color:#ffaa00;">
        <h4 style="color:#ffaa00;">⚠️ Наказания за враньё</h4>
        <ul>
          <li><strong>1-е:</strong> строгий выговор.</li>
          <li><strong>2-е:</strong> временный ЧСА (3–7 дней).</li>
          <li><strong>3-е:</strong> понижение или пожизненный ЧСА.</li>
        </ul>
      </div>

      <div class="priv-card" id="priv-confidential" style="border-color:#ff0000;">
        <h4 style="color:#ff6666;">🚫 Конфиденциальность переписок</h4>
        <ul>
          <li>Запрещено публиковать скриншоты админ-чата.</li>
          <li>Запрещено пересылать личные сообщения.</li>
          <li>Запрещено рассказывать игрокам об обсуждениях.</li>
          <li><strong>Даже для обжалования</strong> нельзя показывать переписки.</li>
          <li><strong>Наказание:</strong> ПОЖИЗНЕННЫЙ ЧСА.</li>
        </ul>
      </div>

      <div class="priv-card" id="priv-others" style="border-color:#9013fe;">
        <h4 style="color:#c07aff;">🛡️ Админство на других серверах</h4>
        <ul>
          <li>Запрещено быть админом на других серверах.</li>
          <li>Конфликт интересов.</li>
          <li><strong>Наказание:</strong> пожизненный ЧСА.</li>
        </ul>
      </div>

      <div class="priv-card" id="priv-hierarchy" style="border-color:#00ff88;">
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

      <div class="priv-card" id="priv-punish" style="border-color:#f5a623;">
        <h4 style="color:#f5a623;">⚖️ Виды взысканий</h4>
        <ul>
          <li><strong>Выговор устный</strong> — мелкие нарушения.</li>
          <li><strong>Выговор письменный</strong> — грубые или повторные.</li>
          <li><strong>Временный ЧСА</strong> — систематические (3–30 дней).</li>
          <li><strong>Понижение</strong> — неисполнение обязанностей.</li>
          <li><strong>Пожизненный ЧСА</strong> — за читерство, слив, оскорбления, враньё (3+), админство на других.</li>
        </ul>
      </div>

      <div class="priv-card" id="priv-rights" style="border-color:#00ccff;">
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
    <h2 id="uniform">👔 Раздел VII. Что можно носить и делать</h2>

    <div class="two-col-grid">
      <div>
        <h3>✅ Что можно носить сотрудникам</h3>
        <table class="data-table">
          <tr><th>Должность</th><th>Разрешено</th></tr>
          <tr><td><strong>Уборщики</strong></td><td>Спецодежда, перчатки, фонарь, пропуск 1 УД</td></tr>
          <tr><td><strong>Капрал СБ</strong></td><td>Форма СБ, дубинка, пистолет, бронежилет</td></tr>
          <tr><td><strong>Мл. НС / Инженер</strong></td><td>Халат, очки, планшет, инструменты</td></tr>
          <tr><td><strong>Сержант / Лейтенант СБ</strong></td><td>Форма СБ, ПП, бронежилет, наручники</td></tr>
          <tr><td><strong>Ст. НС / НС</strong></td><td>Халат, очки, планшет, пропуск 3 УД</td></tr>
          <tr><td><strong>Директор / ГСБ / ГНС</strong></td><td>Официальная форма, пистолет, пропуск 4 УД</td></tr>
          <tr><td><strong>Совет О5 / КпЭ</strong></td><td>Официальная форма, пистолет, полный допуск</td></tr>
          <tr><td><strong>Капитан МОГ</strong></td><td>Тактическая форма, винтовка, пропуск 4 УД</td></tr>
        </table>
      </div>

      <div>
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
    <h2 id="items">🎒 Раздел VIII. Предметы, арест и расстрел</h2>
    <p>Правила о том, что можно носить, что нельзя, и какие меры применяются к нарушителям.</p>

    <h3 id="items-can">✅ Что можно носить персоналу</h3>
    <div class="two-col-grid">
      <div class="item-card item-yes">
        <h4>🧪 Учёные (УД 2-3)</h4>
        <ul>
          <li>Аптечки (Medkit)</li>
          <li>Обезболивающие (Painkillers)</li>
          <li>SCP-500 (только с разрешения ГНС)</li>
          <li>Рация</li>
          <li>Ключ-карта строго своего УД</li>
          <li>Фонарь, планшет, очки</li>
        </ul>
      </div>

      <div class="item-card item-yes">
        <h4>🛡️ Охрана и МОГ (УД 2-4)</h4>
        <ul>
          <li>Штатное оружие (P90, E11, MP7)</li>
          <li>Дубинка/шокер</li>
          <li>Бронежилет</li>
          <li>Рация</li>
          <li>Наручники</li>
          <li>Аптечки и гранаты (по ситуации)</li>
        </ul>
      </div>

      <div class="item-card item-yes">
        <h4>⚙️ Инженеры (УД 2)</h4>
        <ul>
          <li>Инструменты (Toolkit)</li>
          <li>Оборудование для генераторов</li>
          <li>Ключ-карта 2 УД</li>
          <li>Рация, фонарь</li>
        </ul>
      </div>

      <div class="item-card item-yes">
        <h4>🧹 Класс D и уборщики (УД 1)</h4>
        <ul>
          <li>Метла и ведро (только уборщики)</li>
          <li>Фонарь</li>
          <li>Ключ-карта 1 УД (Janitor)</li>
          <li><strong>Больше ничего!</strong></li>
        </ul>
      </div>
    </div>

    <h3 id="items-cant">❌ Что носить ЗАПРЕЩЕНО</h3>
    <div class="two-col-grid">
      <div class="item-card item-no">
        <h4>🚫 Общие запреты (для всех)</h4>
        <ul>
          <li><strong>Карта выше своего уровня допуска</strong></li>
          <li>Чужие ключ-карты</li>
          <li>Оружие не по экипировке роли</li>
          <li>Компоненты боеголовки</li>
          <li>SCP-предметы без допуска</li>
          <li>SCP-018 (мяч)</li>
          <li>MicroHID (кроме МОГ и офицеров)</li>
          <li>Маски, скрывающие лицо</li>
        </ul>
      </div>

      <div class="item-card item-no">
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

      <div class="item-card item-no">
        <h4>🚫 Для учёных</h4>
        <ul>
          <li>Тяжёлое оружие (E11, Logicer)</li>
          <li>Гранаты (кроме успокоительных)</li>
          <li>Карты 5 УД</li>
          <li>Бронежилеты МОГ</li>
          <li>Компоненты боеголовки</li>
        </ul>
      </div>

      <div class="item-card item-no">
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

    <h3 id="items-arrest">🚨 Арест персонала</h3>
    <p>Арест — временное помещение сотрудника под стражу с последующим <strong>выводом на эвакуацию</strong> (удаление из Участка).</p>

    <div class="two-col-grid">
      <div class="item-card item-arrest">
        <h4>⚠️ Арест + вывод на эвакуацию</h4>
        <p style="color:#ffaa00; font-size:0.9em;">При обнаружении запрещённых предметов сотрудник СБ обязан:</p>
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

      <div class="item-card item-arrest">
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

    <h3 id="items-execute">💀 Расстрел класса D</h3>
    <div class="two-col-grid">
      <div class="item-card item-execute">
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

      <div class="item-card item-execute">
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

    <div class="alert alert-info">
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
    <h2 id="general">📜 Раздел IX. Общие правила</h2>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
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

      <div class="section" style="margin:0;">
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
    <h2 id="rp">🎭 Раздел X. RP-правила</h2>
    <div class="section">
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
    <h2 id="classes">👥 Раздел XI. Правила игровых классов</h2>

    <div class="two-col-grid">
      <details>
        <summary>🟠 Класс D</summary>
        <ul>
          <li>Обязаны слушаться охрану.</li>
          <li>Запрещено бунтовать без RP-причины.</li>
          <li>Побег разрешён, но без Banhop.</li>
          <li>Запрещено мешать тестам.</li>
          <li>При КОДЕ КРАСНОМ+ разрешено всё для выживания.</li>
        </ul>
      </details>

      <details>
        <summary>🔵 Учёные</summary>
        <ul>
          <li>Обязаны проводить тесты SCP.</li>
          <li>Запрещено покидать Участок.</li>
          <li>Обязаны сотрудничать с МОГ.</li>
          <li>Запрещено давать Класс D предметы.</li>
        </ul>
      </details>

      <details>
        <summary>🟢 Охрана Фонда</summary>
        <ul>
          <li>Обязаны следить за порядком.</li>
          <li>Запрещено убивать Класс D без причины.</li>
          <li>Обязаны сопровождать учёных.</li>
          <li>При КОДЕ 3+ — защищать Участок.</li>
        </ul>
      </details>

      <details>
        <summary>🔴 МОГ (NTF)</summary>
        <ul>
          <li>Действуют по протоколу.</li>
          <li>Запрещено убивать учёных и охрану.</li>
          <li>Обязаны защищать Участок.</li>
          <li>При КОДЕ 4 — вернуть SCP в камеры.</li>
        </ul>
      </details>

      <details>
        <summary>⚫ ПХ (Chaos Insurgency)</summary>
        <ul>
          <li>Цель — освобождение SCP.</li>
          <li>Запрещён RDM.</li>
          <li>Запрещено убивать своих.</li>
          <li>Обязаны подчиняться командиру.</li>
        </ul>
      </details>

      <details>
        <summary>🟣 SCP-объекты</summary>
        <ul>
          <li>Обязаны отыгрывать свою роль.</li>
          <li>Запрещено фармить убийства.</li>
          <li>SCP-049 обязан лечить.</li>
          <li>Запрещено кемперить.</li>
        </ul>
      </details>
    </div>

    <hr class="divider">

    <!-- SCP -->
    <h2 id="scp">🧬 Раздел XII. Правила SCP-объектов</h2>

    <div class="two-col-grid">
      <div>
        <h3>Основные SCP</h3>
        <table class="data-table">
          <tr><th>SCP</th><th>Правило</th></tr>
          <tr><td><strong>173</strong></td><td>Двигается только при отсутствии зрительного контакта. Запрещён телепорт при 3+ наблюдателях.</td></tr>
          <tr><td><strong>049</strong></td><td>Обязан лечить. Поднимает зомби только по RP-причине.</td></tr>
          <tr><td><strong>106</strong></td><td>Запрещено отправлять игроков в карманное измерение без RP-причины.</td></tr>
          <tr><td><strong>096</strong></td><td>Запрещено намеренно смотреть на 096.</td></tr>
          <tr><td><strong>939</strong></td><td>Обязан использовать звук для охоты.</td></tr>
          <tr><td><strong>3114</strong></td><td>Обязан маскироваться. Запрещено быстрое раскрытие.</td></tr>
          <tr><td><strong>079</strong></td><td>Обязан сотрудничать с SCP.</td></tr>
        </table>
      </div>

      <div id="scp953">
        <h3>SCP-953 — Полиморфная рептилия</h3>
        <p><strong>SCP-953</strong> — опасный SCP, способный принимать облик человека. Класс: <span class="highlight">Кетер</span>.</p>
        <table class="data-table">
          <tr><th>Правило</th></tr>
          <tr><td>Запрещено использование облика для нарушения RP.</td></tr>
          <tr><td>Запрещено заманивание игроков в ловушки.</td></tr>
          <tr><td>Запрещено использование невидимости для атак без RP-причины.</td></tr>
          <tr><td>Обязан отыгрывать роль согласно лору.</td></tr>
          <tr><td>Запрещено убивать без RP-причины даже в облике.</td></tr>
        </table>
      </div>
    </div>

    <hr class="divider">

    <!-- SCP-914 -->
    <h2 id="scp914">⚙️ Раздел XIII. Правила SCP-914</h2>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
        <h3>Правила использования</h3>
        <ul>
          <li>Запрещено использование 914 без RP-причины.</li>
          <li>Запрещено превращение в SCP-049-2 без RP-причины.</li>
          <li>Запрещено использование 914 для обхода правил.</li>
          <li>Обязательно соблюдать очередь.</li>
          <li>Запрещено закидывание людей на смертельные режимы.</li>
        </ul>
      </div>

      <div>
        <h3>Режимы 914</h3>
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

    <hr class="divider">

    <!-- ИНТЕРКОМ -->
    <h2 id="intercom">📢 Раздел XIV. Правила интеркома и чата</h2>

    <div class="alert alert-info">
      <strong>📢 Формат сообщения в интеркоме:</strong>
      <p>«[Имя/Позывной], [Уровень допуска], [Класс персонала], [Что требуется]».</p>
      <ul>
        <li><strong>Пример 1:</strong> «Говорит СБ-Капрал Иванов, 2 УД, класс C. Требуется подкрепление в ЛЗС».</li>
        <li><strong>Пример 2:</strong> «Говорит НС Петров, 3 УД, класс B. Побег SCP-173, КОД СИНИЙ».</li>
        <li><strong>Пример 3:</strong> «Говорит Капитан МОГ, 4 УД, класс B. Объявляю КОД КРАСНЫЙ».</li>
      </ul>
    </div>

    <div class="two-col-grid">
      <div>
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

      <div>
        <h3>Наказания за интерком</h3>
        <table class="data-table">
          <tr><th>Нарушение</th><th>1-е</th><th>2-е</th><th>3-е</th></tr>
          <tr><td>Спам</td><td>Мут 1 ч</td><td>Мут 6 ч</td><td>Бан 1 день</td></tr>
          <tr><td>Музыка</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
          <tr><td>Ложный код</td><td colspan="3">Повод для РП (НЕ бан)</td></tr>
          <tr><td>Оскорбления</td><td>Мут 6 ч</td><td>Бан 1 день</td><td>Бан 7 дней</td></tr>
        </table>
      </div>
    </div>

    <h3 id="chat">Правила чата</h3>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
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

      <div class="section" style="margin:0;">
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
    <h2 id="bans">⏱️ Раздел XV. Сроки наказаний</h2>
    <div class="table-wrap">
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

    <div class="alert alert-warning">
      <strong>⚠️ Примечание:</strong> Рецидивы = удвоение срока.
    </div>

    <hr class="divider">

    <!-- АПЕЛЛЯЦИЯ -->
    <h2 id="appeal">📩 Раздел XVI. Процедура апелляции</h2>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
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
      </div>

      <div>
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

    <div class="alert alert-info">
      <strong>💡 Помни:</strong> Соблюдение правил — залог комфортной игры для всех.
    </div>

    <div class="center">
      <a href="https://discord.gg/ZCGAhTH6ep" class="discord">💬 ВСТУПИТЬ В DISCORD</a>
      <a href="https://t.me/mvprojectru" class="telegram">📢 TELEGRAM-КАНАЛ</a>
    </div>

    <div class="footer">
      <p>© 2026 MV.PROJECT | SCP FOUNDATION | MEDIUM ROLEPLAY</p>
      <p>Документ №SCP-RP-01 «ЗАСЛОН» | Версия 2.5 | Обновлено: сентябрь 2026</p>
      <p style="margin-top: 15px; color: #333;">CLASSIFIED — LEVEL 5 CLEARANCE REQUIRED</p>
    </div>

  </main>

  <script>
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

    window.addEventListener('scroll', () => {
      const sections = document.querySelectorAll('h2[id], h3[id]');
      const links = document.querySelectorAll('.nav-sub a');
      let current = '';
      sections.forEach(sec => {
        const top = sec.offsetTop - 150;
        if (window.scrollY >= top) current = sec.getAttribute('id');
      });
      links.forEach(link => {
        link.classList.remove('active');
        if (link.getAttribute('href') === '#' + current) {
          link.classList.add('active');
        }
      });
    });
  </script>

</body>
</html>
