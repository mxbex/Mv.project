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

  /* ЛЕВОЕ МЕНЮ */
  .sidebar {
    position: fixed; top: 0; left: 0;
    width: 280px; height: 100vh;
    background: #080808; border-right: 2px solid #00ff88;
    padding: 25px 0; overflow-y: auto; z-index: 1000;
    box-shadow: 5px 0 30px rgba(0,0,0,0.8);
  }
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

  .sidebar-nav { padding: 0 15px; }
  .sidebar-nav a {
    display: block; color: #00ff88; text-decoration: none;
    padding: 12px 18px; margin: 4px 0; border-radius: 6px;
    font-size: 0.9em; letter-spacing: 1px; transition: 0.2s;
    border-left: 3px solid transparent;
  }
  .sidebar-nav a:hover {
    background: rgba(0,255,136,0.08);
    border-left-color: #00ff88; transform: translateX(4px);
  }
  .sidebar-nav a.active {
    background: rgba(0,255,136,0.12);
    border-left-color: #00ff88;
  }

  /* КОНТЕНТ */
  .main-content {
    margin-left: 280px;
    padding: 50px 60px;
    min-height: 100vh;
    max-width: calc(100vw - 280px);
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
    .main-content { margin-left: 0; padding: 70px 20px 30px; max-width: 100%; }
    .menu-toggle { display: block; }
  }

  /* Шапка */
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

  /* Заголовки */
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
  }
  h4 { color: #88ffbb; font-size: 1.1em; margin: 25px 0 12px; letter-spacing: 1px; }

  p { margin: 12px 0; color: #b0b0b0; }
  strong { color: #00ff88; }

  ul, ol { padding-left: 30px; margin: 18px 0; }
  li { padding: 8px 0 8px 10px; color: #b0b0b0; border-bottom: 1px dotted #1a1a1a; }
  li:hover { color: #e0e0e0; }

  /* СЕТКА 2 В РЯД */
  .two-col-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 25px;
    margin: 25px 0;
  }
  @media (max-width: 1100px) {
    .two-col-grid { grid-template-columns: 1fr; }
  }

  /* Таблицы */
  .data-table {
    width: 100%; border-collapse: collapse;
    background: #0a0a0a; border: 1px solid #1a1a1a;
    font-size: 0.88em;
  }
  .data-table th {
    background: #0f1a12; color: #00ff88; padding: 14px;
    text-align: left; font-weight: bold; letter-spacing: 1px;
    border-bottom: 2px solid #00ff88;
    text-transform: uppercase; font-size: 0.85em;
  }
  .data-table td {
    padding: 12px 14px;
    border-bottom: 1px solid #1a1a1a;
    color: #c0c0c0; vertical-align: top;
    background: #0a0a0a;
  }
  .data-table tr { background: #0a0a0a; }
  .data-table tr:hover,
  .data-table tr:hover td,
  .data-table tr:hover th {
    background: #0f0f0f; color: #e0e0e0;
  }
  .data-table strong { color: #00ff88; }
  .table-wrap { background: #0a0a0a; }

  /* Цветные коды */
  .code-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 25px; margin: 35px 0;
  }
  @media (max-width: 1100px) {
    .code-grid { grid-template-columns: 1fr; }
  }
  .code-card {
    padding: 25px; border-radius: 10px; background: #0f0f0f;
    border: 2px solid; transition: 0.3s;
    position: relative; overflow: hidden;
  }
  .code-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.6); }
  .code-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px; }
  .code-card h4 { font-size: 1.4em; margin-bottom: 15px; letter-spacing: 3px; }
  .code-card p { font-size: 0.92em; color: #999; margin-bottom: 12px; }
  .code-card ul { margin-top: 10px; font-size: 0.85em; }
  .code-card li { border-bottom: 1px dotted rgba(255,255,255,0.05); }
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
    padding: 20px 25px; border-radius: 8px; margin: 25px 0;
    border-left: 6px solid; font-size: 0.95em;
  }
  .alert-danger { background: rgba(255, 0, 0, 0.08); border-color: #ff0000; color: #ff8888; }
  .alert-warning { background: rgba(255, 170, 0, 0.08); border-color: #ffaa00; color: #ffcc66; }
  .alert-info { background: rgba(0, 255, 136, 0.05); border-color: #00ff88; color: #88ffbb; }
  .section { margin: 40px 0; padding: 30px; background: #0d0d0d; border-radius: 10px; border: 1px solid #1a1a1a; }

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
    grid-template-columns: repeat(2, 1fr);
    gap: 25px; margin: 30px 0;
  }
  @media (max-width: 1100px) {
    .clearance-grid { grid-template-columns: 1fr; }
  }
  .clearance-card {
    padding: 25px; border-radius: 10px; border: 2px solid;
    background: #0f0f0f; transition: 0.3s;
  }
  .clearance-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.6); }
  .clearance-card h4 { font-size: 1.5em; margin-bottom: 15px; letter-spacing: 2px; }
  .clearance-card p { font-size: 0.9em; color: #999; }
  .clearance-card ul { margin-top: 10px; font-size: 0.9em; }
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

  /* Привилегии */
  .priv-card {
    padding: 25px; border-radius: 10px;
    background: #0f0f0f;
    border: 2px solid #00ff88;
    transition: 0.3s;
  }
  .priv-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,255,136,0.15); }
  .priv-card h4 { color: #00ff88; font-size: 1.3em; margin-bottom: 15px; letter-spacing: 2px; }
  .priv-card p { font-size: 0.9em; color: #999; }
  .priv-card ul { margin-top: 10px; font-size: 0.9em; }
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
      <a href="#codes">🚨 КОДЫ</a>
      <a href="#clearance">🔐 ДОПУСК</a>
      <a href="#classes-personnel">👤 КЛАССЫ ПЕРСОНАЛА</a>
      <a href="#mtf">🛡️ МОГ</a>
      <a href="#protocols">📋 ПРОТОКОЛЫ</a>
      <a href="#privileges">⭐ ПРИВИЛЕГИИ</a>
      <a href="#uniform">👔 ФОРМА</a>
      <a href="#general">📜 ОБЩИЕ</a>
      <a href="#rp">🎭 RP</a>
      <a href="#classes">👥 КЛАССЫ</a>
      <a href="#scp">🧬 SCP</a>
      <a href="#scp914">⚙️ SCP-914</a>
      <a href="#intercom">📢 ИНТЕРКОМ</a>
      <a href="#bans">⏱️ БАНЫ</a>
      <a href="#appeal">📩 АПЕЛЛЯЦИЯ</a>
    </nav>
  </aside>

  <main class="main-content">

    <div class="header">
      <div class="classification">⚠ CLASSIFIED — LEVEL 5 CLEARANCE ⚠</div>
      <h1>MV.PROJECT</h1>
      <p class="subtitle">SCP FOUNDATION | MEDIUM ROLEPLAY</p>
      <p class="codename">Уставной документ №SCP-RP-01 «ЗАСЛОН» | Зона 19 | Возрастной рейтинг: 13+</p>
    </div>

    <div class="alert alert-danger">
      <strong>⛔ ВНИМАНИЕ:</strong> Данный устав обязателен к прочтению каждому сотруднику Зоны. 
      Заходя на сервер <strong>MV.Project</strong>, вы автоматически соглашаетесь с правилами. 
      <span class="critical">Незнание правил не освобождает от ответственности.</span>
    </div>

    <!-- КОДЫ -->
    <h2 id="codes">🚨 Раздел I. Цветовые коды угроз</h2>
    <p>Коды угроз — стандартная система оповещения Фонда. Персонал обязан знать их значение и правильно реагировать при объявлении.</p>

    <div class="code-grid">
      <div class="code-card code-green">
        <h4>🟢 КОД ЗЕЛЁНЫЙ</h4>
        <p><strong>Био-угроза / Заражение</strong></p>
        <p>Обозначает любую опасность, связанную с био-угрозой, инфекцией или источником заражения.</p>
        <p><strong>Указания:</strong> Избегайте контакта с источниками заражения. Не покидайте Зону.</p>
        <p><strong>МОГ:</strong> Бета-7 «Шляпные болванчики»</p>
      </div>
      <div class="code-card code-blue">
        <h4>🔵 КОД СИНИЙ</h4>
        <p><strong>Побег разумного объекта</strong></p>
        <p>Побег разумного объекта с интеллектом ниже человеческого.</p>
        <p><strong>Указания:</strong> Следуйте указаниям охраны.</p>
        <p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p>
      </div>
      <div class="code-card code-superblue">
        <h4>🔷 КОД СУПЕРСИНИЙ</h4>
        <p><strong>Побег разумного объекта (высокий интеллект)</strong></p>
        <p>Побег разумного объекта с интеллектом, равным или превышающим человеческий.</p>
        <p><strong>МОГ:</strong> Эпсилон-11 «Девятихвостая лиса»</p>
      </div>
      <div class="code-card code-yellow">
        <h4>🟡 КОД ЖЁЛТЫЙ</h4>
        <p><strong>Меметическая / когнитивная угроза</strong></p>
        <p>Присутствие меметической, информационной или когнитивной угрозы.</p>
        <p><strong>МОГ:</strong> Эта-10 «Не вижу зла», Эта-11 «Дикие твари»</p>
      </div>
      <div class="code-card code-red">
        <h4>🔴 КОД КРАСНЫЙ</h4>
        <p><strong>Агрессивная настроенная сущность (АНС)</strong></p>
        <p>Побег агрессивно настроенной сущности, представляющей опасность для Зоны.</p>
        <p><strong>МОГ:</strong> Ню-7 «Удар молота», Эта-5 «Бомбардиры Егеря»</p>
      </div>
      <div class="code-card code-black">
        <h4>⚫ КОД ЧЁРНЫЙ</h4>
        <p><strong>Нарушение содержания НЛУ</strong></p>
        <p>Нарушение содержания Неликвидируемой Угрозы (например, SCP-096).</p>
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
        <p>Аналог БЕЛОГО, но угроза исходит изнутри Зоны.</p>
        <p><strong>МОГ:</strong> Все ММОГ уровня батальона</p>
      </div>
      <div class="code-card code-purple">
        <h4>🟣 КОД ПУРПУРНЫЙ</h4>
        <p><strong>Экстрамерная угроза</strong></p>
        <p>Нарушения пространства, времени, причинности, нематериальные объекты.</p>
        <p><strong>МОГ:</strong> Дзета-9, Лямбда-5, Мю-13</p>
      </div>
      <div class="code-card code-clean">
        <h4>⬜ КОД ЧИСТЫЙ</h4>
        <p><strong>Неизвестная угроза</strong></p>
        <p>Обозначает неизвестную угрозу.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
      <div class="code-card code-superclean">
        <h4>💗 КОД СУПЕРЧИСТЫЙ</h4>
        <p><strong>Неописуемая угроза</strong></p>
        <p>Обозначает угрозу, не поддающуюся описанию.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
      <div class="code-card code-silver">
        <h4>🥈 КОД ХЛАДНОЕ СЕРЕБРО</h4>
        <p><strong>Фатальный сбой Фонда</strong></p>
        <p>Событие, послужившее причиной фатального нарушения функционирования Фонда.</p>
        <p><strong>МОГ:</strong> Отсутствуют</p>
      </div>
    </div>

    <div class="alert alert-info">
      <strong>📢 Правила поведения при кодах:</strong>
      <ul>
        <li>При КОДЕ СИНЕМ и выше — персонал обязан подчиняться приказам МОГ.</li>
        <li>При КОДЕ КРАСНОМ — Класс D разрешено ликвидировать без предупреждения (при сопротивлении).</li>
        <li>При КОДЕ ЧЁРНОМ — все обязаны немедленно эвакуироваться на поверхность.</li>
        <li>Ложное объявление кода = бан на 7 дней.</li>
      </ul>
    </div>

    <hr class="divider">

    <!-- ДОПУСК -->
    <h2 id="clearance">🔐 Раздел II. Уровни допуска персонала</h2>
    <p>Система допуска определяет, к каким зонам и информации имеет доступ сотрудник.</p>

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
      </div>
      <div class="clearance-card level-4">
        <h4>УРОВЕНЬ 4</h4>
        <p><strong>Командование</strong></p>
        <ul>
          <li>Директор Зоны</li>
          <li>Представитель КпЭ</li>
          <li>Агент ГАРШ-O4</li>
          <li>ГНС (Главный Научный Сотрудник)</li>
          <li>ГСБ (Глава Службы Безопасности)</li>
          <li><strong>Капитан МОГ</strong> (командир оперативной группы)</li>
        </ul>
        <p style="margin-top:10px; color:#ff6666;">Доступ: все зоны комплекса. Командование операциями.</p>
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
        <p style="margin-top:10px; color:#ff6666;">Доступ: полный доступ ко всем зонам.</p>
      </div>
    </div>

    <hr class="divider">

    <!-- КЛАССЫ ПЕРСОНАЛА -->
    <h2 id="classes-personnel">👤 Раздел III. Классы персонала</h2>
    <p>Классы присваиваются персоналу на основании плотности их контакта с потенциально опасными аномальными объектами.</p>

    <div class="clearance-grid">
      <div class="clearance-card level-a">
        <h4>КЛАСС A</h4>
        <p><strong>Стратегически важный персонал</strong></p>
        <ul>
          <li>Члены Совета О5</li>
          <li>Высшее руководство Фонда</li>
        </ul>
        <p><strong>Запрещено:</strong> Любой прямой доступ к аномальным объектам. Выход из защищённых областей.</p>
        <p><strong>Разрешено:</strong> Работа в защищённых областях. Немедленная эвакуация при ЧС.</p>
      </div>
      <div class="clearance-card level-b">
        <h4>КЛАСС B</h4>
        <p><strong>Важный персонал</strong></p>
        <ul>
          <li>Руководители отделов</li>
          <li>Старшие научные сотрудники</li>
          <li>Ключевые инженеры</li>
        </ul>
        <p><strong>Запрещено:</strong> Доступ к аномалиям без карантина и блокировки ментального воздействия.</p>
        <p><strong>Разрешено:</strong> Доступ к карантинным аномалиям.</p>
      </div>
      <div class="clearance-card level-c">
        <h4>КЛАСС C</h4>
        <p><strong>Прямой доступ к аномалиям</strong></p>
        <ul>
          <li>Научные сотрудники</li>
          <li>Охрана</li>
          <li>Инженеры</li>
        </ul>
        <p><strong>Запрещено:</strong> Контакт с опасными аномалиями без защиты.</p>
        <p><strong>Разрешено:</strong> Работа с безопасными аномалиями.</p>
      </div>
      <div class="clearance-card level-d">
        <h4>КЛАСС D</h4>
        <p><strong>Расходный персонал</strong></p>
        <ul>
          <li>Заключённые</li>
          <li>Испытуемые</li>
        </ul>
        <p><strong>Запрещено:</strong> Контакт с сотрудниками класса A и B. Побег. Неподчинение.</p>
        <p><strong>Разрешено:</strong> Участие в тестах. Ограниченное передвижение с охраной.</p>
      </div>
      <div class="clearance-card level-e">
        <h4>КЛАСС E</h4>
        <p><strong>Временное обозначение</strong></p>
        <ul>
          <li>Полевые агенты</li>
          <li>Персонал, пострадавший от аномалий</li>
        </ul>
        <p><strong>Запрещено:</strong> Возвращение к обязанностям до полного обследования.</p>
        <p><strong>Разрешено:</strong> Карантин и наблюдение.</p>
      </div>
    </div>

    <hr class="divider">

    <!-- МОГ -->
    <h2 id="mtf">🛡️ Раздел IV. Мобильные Оперативные Группы (МОГ)</h2>
    <p>МОГ — элитные подразделения Фонда, специализирующиеся на решении конкретных угроз.</p>

    <h3>Основные МОГ</h3>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Отряд</th><th>Позывной</th><th>Специализация</th></tr>
        <tr><td><strong>Ню-7</strong></td><td>«Удар молота»</td><td>Подавление крупномасштабных нарушений содержания.</td></tr>
        <tr><td><strong>Эта-10</strong></td><td>«Не вижу зла»</td><td>Меметические, информационные и когнитивные угрозы.</td></tr>
        <tr><td><strong>Эта-11</strong></td><td>«Дикие твари»</td><td>Звуковые и музыкальные аномалии.</td></tr>
        <tr><td><strong>Бета-7</strong></td><td>«Шляпные болванчики»</td><td>Био-угрозы, инфекции, аномальные пандемии.</td></tr>
        <tr><td><strong>Эпсилон-11</strong></td><td>«Девятихвостая лиса»</td><td>Внутренняя безопасность, поимка беглых SCP.</td></tr>
        <tr><td><strong>Дзета-9</strong></td><td>«Кротокрысы»</td><td>Пространственно-временные аномалии.</td></tr>
        <tr><td><strong>Лямбда-5</strong></td><td>«Белые кролики»</td><td>Экстрамерные, временные и пространственные угрозы.</td></tr>
        <tr><td><strong>Мю-13</strong></td><td>«Охотники за привидениями»</td><td>Нематериальные и эктоплазматические сущности.</td></tr>
      </table>
    </div>

    <h3>Дополнительные МОГ</h3>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Отряд</th><th>Позывной</th><th>Специализация</th></tr>
        <tr><td><strong>Альфа-1</strong></td><td>«Багряная десница»</td><td>Личная охрана Совета О5.</td></tr>
        <tr><td><strong>Альфа-9</strong></td><td>«Последняя надежда»</td><td>Сдерживание SCP, ликвидация неавторизованных групп.</td></tr>
        <tr><td><strong>Альфа-40</strong></td><td>«Мятежники»</td><td>Ликвидация неавторизованных группировок.</td></tr>
        <tr><td><strong>Гамма-5</strong></td><td>«Ложный след»</td><td>Дезинформация, сокрытие аномальных событий.</td></tr>
        <tr><td><strong>Гамма-13</strong></td><td>«Законники Азимова»</td><td>Работа с ИИ-аномалиями.</td></tr>
        <tr><td><strong>Лямбда-12</strong></td><td>«Санстанция»</td><td>Паразитные организмы и биологические системы.</td></tr>
        <tr><td><strong>Мю-3</strong></td><td>«Богатые Аукционеры»</td><td>Ликвидация неавторизованных групп.</td></tr>
        <tr><td><strong>Мю-4</strong></td><td>«Отладчики»</td><td>Устранение неполадок в системах комплекса.</td></tr>
        <tr><td><strong>Омега-1</strong></td><td>«Левая рука закона»</td><td>Внутренние разбирательства, охота на предателей.</td></tr>
        <tr><td><strong>Сигма-66</strong></td><td>«Шестнадцать тонн»</td><td>Тяжёлое вооружение.</td></tr>
        <tr><td><strong>Тау-5</strong></td><td>«Самсара»</td><td>Религиозные и культовые аномалии.</td></tr>
        <tr><td><strong>Эпсилон-9</strong></td><td>«Пожиратели огня»</td><td>Термальные угрозы, пожары, пирокинез.</td></tr>
      </table>
    </div>

    <h3>Тактические группы (ТГ)</h3>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Группа</th><th>Позывной</th><th>Специализация</th></tr>
        <tr><td><strong>ОБР «Курс»</strong></td><td>Тактическая группа</td><td>Сдерживание SCP, разведка, разбирательства.</td></tr>
        <tr><td><strong>ТГ «Птицы»</strong></td><td>Тактическая группа</td><td>Сдерживание SCP-106, сопровождение.</td></tr>
        <tr><td><strong>ТГ «Резонанс»</strong></td><td>Тактическая группа</td><td>Ликвидация угроз, сдерживание SCP.</td></tr>
        <tr><td><strong>ТГ «Пожарники»</strong></td><td>Инженерная ТГ</td><td>Устранение неполадок, пожаров.</td></tr>
        <tr><td><strong>Санитарная ТГ</strong></td><td>Медицинская группа</td><td>Медицинская помощь пострадавшим.</td></tr>
      </table>
    </div>

    <hr class="divider">

    <!-- ПРОТОКОЛЫ -->
    <h2 id="protocols">📋 Раздел V. Протоколы и изоляционные коды</h2>

    <div class="two-col-grid">
      <div>
        <h3>Протоколы P-L (блокировка)</h3>
        <table class="data-table">
          <tr><th>Протокол</th><th>Описание</th></tr>
          <tr><td><strong>P-L-1</strong></td><td>Блокировка гермо-ворот A и B.</td></tr>
          <tr><td><strong>P-L-2</strong></td><td>Блокировка всех КПП.</td></tr>
          <tr><td><strong>P-L-3</strong></td><td>Блокировка всех дверей.</td></tr>
        </table>
      </div>

      <div>
        <h3>Протоколы P-S (SCP)</h3>
        <table class="data-table">
          <tr><th>Протокол</th><th>Описание</th></tr>
          <tr><td><strong>P-S-1</strong></td><td>Отслеживание SCP-объектов.</td></tr>
          <tr><td><strong>P-S-2</strong></td><td>Отслеживание статуса SCP-объектов.</td></tr>
          <tr><td><strong>P-S-3</strong></td><td>Активация тесла-ворот.</td></tr>
          <tr><td><strong>P-S-4</strong></td><td>Сканирование комплекса.</td></tr>
          <tr><td><strong>P-S-5</strong></td><td>Полный блэкаут комплекса.</td></tr>
        </table>
      </div>

      <div>
        <h3>Протоколы P-B (био-безопасность)</h3>
        <table class="data-table">
          <tr><th>Протокол</th><th>Описание</th></tr>
          <tr><td><strong>P-B-1</strong></td><td>Запечатывание заражённых комнат.</td></tr>
          <tr><td><strong>P-B-2</strong></td><td>Запечатывание камер содержания SCP.</td></tr>
          <tr><td><strong>P-B-3</strong></td><td>Деконтаминация ЛЗС.</td></tr>
          <tr><td><strong>P-B-4</strong></td><td>Деконтаминация ТЗС.</td></tr>
          <tr><td><strong>P-B-5</strong></td><td>Подрыв комплекса.</td></tr>
          <tr><td><strong>P-B-6</strong></td><td>Подрыв комплекса и внешнего периметра.</td></tr>
        </table>
      </div>

      <div>
        <h3>Протоколы P-I (вторжение)</h3>
        <table class="data-table">
          <tr><th>Протокол</th><th>Описание</th></tr>
          <tr><td><strong>P-I-1</strong></td><td>Уничтожение техники у комплекса.</td></tr>
          <tr><td><strong>P-I-2</strong></td><td>Блокировка мест взлома и оповещение.</td></tr>
          <tr><td><strong>P-I-3</strong></td><td>Уничтожение всего персонала в зоне.</td></tr>
        </table>
      </div>

      <div>
        <h3>Протоколы P-E (пожаротушение)</h3>
        <table class="data-table">
          <tr><th>Протокол</th><th>Описание</th></tr>
          <tr><td><strong>P-E-1</strong></td><td>Тушение в одной комнате; нет угрозы жизни.</td></tr>
          <tr><td><strong>P-E-2</strong></td><td>Тушение в одной комнате; есть угроза жизни.</td></tr>
          <tr><td><strong>P-E-3</strong></td><td>Тушение в одной комнате; угроза взрыва.</td></tr>
          <tr><td><strong>P-E-4</strong></td><td>Тушение в нескольких комнатах; нет угрозы.</td></tr>
          <tr><td><strong>P-E-5</strong></td><td>Тушение в нескольких комнатах; есть угроза.</td></tr>
          <tr><td><strong>P-E-6</strong></td><td>Тушение в целой зоне; большая угроза жизни.</td></tr>
          <tr><td><strong>P-E-7</strong></td><td>Тушение в КС SCP класса «Безопасный».</td></tr>
          <tr><td><strong>P-E-8</strong></td><td>Тушение в КС SCP класса «Евклид».</td></tr>
          <tr><td><strong>P-E-9</strong></td><td>Тушение в КС SCP класса «Кетер».</td></tr>
        </table>
      </div>

      <div>
        <h3>Изоляционные коды (КИР)</h3>
        <table class="data-table">
          <tr><th>Код</th><th>Значение</th></tr>
          <tr><td><strong>Чёрный</strong></td><td>Полная изоляция комплекса.</td></tr>
          <tr><td><strong>Серый</strong></td><td>Внутренняя угроза.</td></tr>
          <tr><td><strong>Белый</strong></td><td>Внешнее вторжение.</td></tr>
          <tr><td><strong>Суперсиний</strong></td><td>Побег разумного SCP (высокий интеллект).</td></tr>
          <tr><td><strong>Синий</strong></td><td>Побег разумного SCP.</td></tr>
          <tr><td><strong>Красный</strong></td><td>Агрессивная сущность.</td></tr>
          <tr><td><strong>Зелёный</strong></td><td>Био-угроза.</td></tr>
          <tr><td><strong>Пурпурный</strong></td><td>Экстрамерная угроза.</td></tr>
          <tr><td><strong>Жёлтый</strong></td><td>Меметическая угроза.</td></tr>
          <tr><td><strong>Чистый</strong></td><td>Неизвестная угроза.</td></tr>
          <tr><td><strong>Суперчистый</strong></td><td>Неописуемая угроза.</td></tr>
          <tr><td><strong>Хладное серебро</strong></td><td>Фатальный сбой Фонда.</td></tr>
          <tr><td><strong>Розовый</strong></td><td>Дополнительный код.</td></tr>
        </table>
      </div>
    </div>

    <hr class="divider">

    <!-- ПРИВИЛЕГИИ -->
    <h2 id="privileges">⭐ Раздел VI. Правила привилегий и администрации</h2>
    <p>Администрация сервера — это не просто люди с командами, а <strong>лицо проекта</strong>. Каждый админ обязан соблюдать регламент и не злоупотреблять полномочиями.</p>

    <div class="alert alert-danger">
      <strong>⛔ ВАЖНО:</strong> Нарушение правил привилегий = понижение, ЧСА или полное снятие с должности.
    </div>

    <h3>Основные правила для администрации</h3>
    <div class="two-col-grid">
      <div class="priv-card">
        <h4>✅ Что ОБЯЗАН делать админ</h4>
        <ul>
          <li>Быть активным (заходить минимум 3–4 раза в неделю).</li>
          <li>Знать правила сервера наизусть.</li>
          <li>Реагировать на жалобы игроков.</li>
          <li>Использовать команды только по назначению.</li>
          <li>Быть вежливым и сдержанным.</li>
          <li>Помогать новичкам.</li>
          <li>Соблюдать иерархию и субординацию.</li>
          <li>Фиксировать выданные наказания.</li>
        </ul>
      </div>

      <div class="priv-card" style="border-color:#ff0000;">
        <h4 style="color:#ff6666;">❌ Что ЗАПРЕЩЕНО админу</h4>
        <ul>
          <li>Оскорблять игроков или коллег.</li>
          <li>Злоупотреблять полномочиями.</li>
          <li>Игнорировать игроков.</li>
          <li>Читерить или использовать сторонний софт.</li>
          <li>Использовать админ-команды в личных целях.</li>
          <li>Сливать информацию из админ-чата.</li>
          <li>Кормить читеров или закрывать на них глаза.</li>
          <li>Создавать конфликты на глазах у игроков.</li>
          <li>Долго отсутствовать без предупреждения (7+ дней).</li>
        </ul>
      </div>

      <div class="priv-card" style="border-color:#ffaa00;">
        <h4 style="color:#ffaa00;">⚠️ Наказания за враньё</h4>
        <ul>
          <li><strong>1-е враньё:</strong> строгий выговор.</li>
          <li><strong>2-е враньё:</strong> временный ЧСА (3–7 дней).</li>
          <li><strong>3-е враньё:</strong> понижение или пожизненный ЧСА.</li>
        </ul>
        <p style="margin-top:10px; color:#999;">Враньё подрывает доверие внутри команды.</p>
      </div>

      <div class="priv-card" style="border-color:#ff0000;">
        <h4 style="color:#ff6666;">🚫 Конфиденциальность переписок</h4>
        <ul>
          <li>Запрещено публиковать скриншоты админ-чата.</li>
          <li>Запрещено пересылать личные сообщения третьим лицам.</li>
          <li>Запрещено рассказывать игрокам о внутренних обсуждениях.</li>
          <li><strong>Даже для обжалования</strong> нельзя показывать переписки.</li>
          <li><strong>Наказание:</strong> ПОЖИЗНЕННЫЙ ЧСА без права восстановления.</li>
        </ul>
      </div>

      <div class="priv-card" style="border-color:#9013fe;">
        <h4 style="color:#c07aff;">🛡️ Администрирование на других серверах</h4>
        <ul>
          <li>Запрещено быть админом на других серверах SCP:SL.</li>
          <li>Это конфликт интересов.</li>
          <li><strong>Наказание:</strong> пожизненный ЧСА без права восстановления.</li>
          <li>После ЧСА — запрет на админство на других серверах.</li>
        </ul>
      </div>

      <div class="priv-card" style="border-color:#00ff88;">
        <h4>👑 Иерархия должностей</h4>
        <ul>
          <li><strong>Высший состав:</strong> Владелец, Со-владелец, Гл. Админ, Зам., HR, Dev.</li>
          <li><strong>Кураторы:</strong> Ст. куратор, кураторы админов/модеров/помощников/стажёров, дисциплины.</li>
          <li><strong>Ивент-отдел:</strong> Гл. ивентолог, ивентолог.</li>
          <li><strong>Администраторы:</strong> Ст. админ, админ, мл. админ.</li>
          <li><strong>Модераторы:</strong> Ст. модер, модер, мл. модер.</li>
          <li><strong>Помощники и стажёры:</strong> Ст. помощник, помощник, мл. помощник, стажёры.</li>
          <li><strong>Контент-мейкеры:</strong> Гл. КМ, ст. КМ, КМ, видео-оператор, стример, летсплейщик.</li>
        </ul>
      </div>

      <div class="priv-card" style="border-color:#f5a623;">
        <h4 style="color:#f5a623;">⚖️ Виды взысканий</h4>
        <ul>
          <li><strong>Выговор устный</strong> — мелкие нарушения.</li>
          <li><strong>Выговор письменный</strong> — грубые или повторные нарушения.</li>
          <li><strong>Временный ЧСА</strong> — систематические нарушения (3–30 дней).</li>
          <li><strong>Понижение</strong> — неисполнение обязанностей.</li>
          <li><strong>Пожизненный ЧСА</strong> — за читерство, слив инфы, оскорбления, враньё (3+ раз), админство на других серверах.</li>
        </ul>
      </div>

      <div class="priv-card" style="border-color:#00ccff;">
        <h4 style="color:#00ccff;">📋 Права администрации</h4>
        <ul>
          <li>Право на ошибку, если админ готов её признать.</li>
          <li>Право на защиту своей позиции при обсуждении.</li>
          <li>Право обратиться к старшему админу или владельцу.</li>
          <li>Право на апелляцию наказания (через владельца, лично).</li>
        </ul>
      </div>
    </div>

    <div class="alert alert-info">
      <strong>💡 Помни:</strong> Администратор — это <strong>пример для игроков</strong>. 
      Ты не просто человек с командами, ты — <strong>лицо проекта</strong>. Будь на высоте.
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
          <tr><td><strong>Капрал СБ</strong></td><td>Форма СБ, дубинка, пистолет, бронежилет, рация</td></tr>
          <tr><td><strong>Мл. НС / Инженер</strong></td><td>Халат, очки, планшет, инструменты, фонарь</td></tr>
          <tr><td><strong>Сержант / Лейтенант СБ</strong></td><td>Форма СБ, ПП, бронежилет, рация, наручники</td></tr>
          <tr><td><strong>Ст. НС / НС</strong></td><td>Халат, очки, планшет, рация, пропуск 3 УД</td></tr>
          <tr><td><strong>Директор / ГСБ / ГНС</strong></td><td>Официальная форма, пистолет, рация, пропуск 4 УД</td></tr>
          <tr><td><strong>Совет О5 / КпЭ</strong></td><td>Официальная форма, пистолет, полный допуск</td></tr>
          <tr><td><strong>Капитан МОГ</strong></td><td>Тактическая форма, штурмовая винтовка, рация, пропуск 4 УД</td></tr>
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
            <li>Аксессуары, нарушающие RP (короны, шляпы).</li>
          </ul>
        </div>
      </div>

      <div>
        <h3>❌ Что ЗАПРЕЩЕНО делать</h3>
        <div class="alert alert-danger">
          <ul>
            <li>Покидать комплекс без приказа.</li>
            <li>Использовать оружие без RP-причины.</li>
            <li>Открывать двери без допуска.</li>
            <li>Передавать ключ-карты другим.</li>
            <li>Вступать в контакт с SCP без протокола.</li>
            <li>Игнорировать коды угроз.</li>
            <li>Мешать другим отделам.</li>
            <li>Нарушать субординацию.</li>
          </ul>
        </div>
      </div>
    </div>

    <hr class="divider">

    <!-- ОБЩИЕ -->
    <h2 id="general">📜 Раздел VIII. Общие правила</h2>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
        <h3>8.1. Принципы сервера</h3>
        <p>Сервер <strong>MV.Project</strong> — это <span class="highlight">Medium RP</span> проект.</p>
        <ul>
          <li>Уважение — основа сервера.</li>
          <li>Запрещена дискриминация.</li>
          <li>Запрещены угрозы в реальной жизни.</li>
          <li>Запрещена пропаганда терроризма и насилия.</li>
          <li>Запрещены атаки на сервер.</li>
        </ul>
      </div>

      <div class="section" style="margin:0;">
        <h3>8.2. Возраст и аккаунты</h3>
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
    <h2 id="rp">🎭 Раздел IX. RP-правила</h2>
    <div class="section">
      <h3>9.1. Что такое RP?</h3>
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
    <h2 id="classes">👥 Раздел X. Правила игровых классов</h2>

    <div class="two-col-grid">
      <details>
        <summary>🟠 Класс D</summary>
        <ul>
          <li>Обязаны слушаться охрану и учёных.</li>
          <li>Запрещено устраивать бунт без RP-причины.</li>
          <li>Побег разрешён, но без Banhop.</li>
          <li>Запрещено мешать тестам.</li>
          <li>При КОДЕ КРАСНОМ+ разрешено всё для выживания.</li>
        </ul>
      </details>

      <details>
        <summary>🔵 Учёные</summary>
        <ul>
          <li>Обязаны проводить тесты SCP.</li>
          <li>Запрещено покидать комплекс без причины.</li>
          <li>Обязаны сотрудничать с МОГ.</li>
          <li>Запрещено давать Класс D предметы без разрешения.</li>
        </ul>
      </details>

      <details>
        <summary>🟢 Охрана Фонда</summary>
        <ul>
          <li>Обязаны следить за порядком.</li>
          <li>Запрещено убивать Класс D без причины.</li>
          <li>Обязаны сопровождать учёных.</li>
          <li>При КОДЕ 3+ — защищать комплекс.</li>
        </ul>
      </details>

      <details>
        <summary>🔴 МОГ (NTF)</summary>
        <ul>
          <li>Действуют по протоколу.</li>
          <li>Запрещено убивать учёных и охрану.</li>
          <li>Обязаны защищать комплекс от ПХ.</li>
          <li>При КОДЕ 4 — вернуть SCP в камеры.</li>
        </ul>
      </details>

      <details>
        <summary>⚫ ПХ (Chaos Insurgency)</summary>
        <ul>
          <li>Цель — освобождение SCP и захват комплекса.</li>
          <li>Запрещён RDM без RP-причины.</li>
          <li>Запрещено убивать своих.</li>
          <li>Обязаны подчиняться командиру отряда.</li>
        </ul>
      </details>

      <details>
        <summary>🟣 SCP-объекты</summary>
        <ul>
          <li>Обязаны отыгрывать свою роль.</li>
          <li>Запрещено фармить убийства без причины.</li>
          <li>SCP-049 обязан лечить.</li>
          <li>Запрещено кемперить.</li>
        </ul>
      </details>
    </div>

    <hr class="divider">

    <!-- SCP -->
    <h2 id="scp">🧬 Раздел XI. Правила SCP-объектов</h2>

    <div class="two-col-grid">
      <div>
        <h3>Основные SCP</h3>
        <table class="data-table">
          <tr><th>SCP</th><th>Правило</th><th>Наказание</th></tr>
          <tr><td><strong>173</strong></td><td>Двигается только при отсутствии зрительного контакта. Запрещён телепорт при 3+ наблюдателях.</td><td>Бан 7-30 дней</td></tr>
          <tr><td><strong>049</strong></td><td>Обязан лечить. Поднимает зомби только по RP-причине.</td><td>Бан 3-7 дней</td></tr>
          <tr><td><strong>106</strong></td><td>Запрещено намеренно отправлять игроков в карманное измерение без RP-причины.</td><td>Бан 3-7 дней</td></tr>
          <tr><td><strong>096</strong></td><td>Запрещено намеренно смотреть на 096, чтобы вызвать агрессию.</td><td>Бан 1-3 дня</td></tr>
          <tr><td><strong>939</strong></td><td>Обязан использовать звук для охоты.</td><td>Предупреждение / Бан 1 день</td></tr>
          <tr><td><strong>3114</strong></td><td>Обязан маскироваться под человека. Запрещено быстрое раскрытие.</td><td>Бан 1-3 дня</td></tr>
          <tr><td><strong>079</strong></td><td>Обязан сотрудничать с SCP.</td><td>Предупреждение / Бан 1 день</td></tr>
        </table>
      </div>

      <div>
        <h3>SCP-953 — Полиморфная рептилия</h3>
        <p><strong>SCP-953</strong> — опасный SCP, способный принимать облик человека. Класс: <span class="highlight">Кетер</span>.</p>
        <table class="data-table">
          <tr><th>Правило</th><th>Наказание</th></tr>
          <tr><td>Запрещено использование облика для нарушения RP.</td><td>Бан 7 дней</td></tr>
          <tr><td>Запрещено заманивание игроков в ловушки под видом союзника.</td><td>Бан 14 дней</td></tr>
          <tr><td>Запрещено использование невидимости для постоянных атак без RP-причины.</td><td>Бан 7 дней</td></tr>
          <tr><td>Обязан отыгрывать роль SCP-953 согласно лору.</td><td>Предупреждение / Бан 3 дня</td></tr>
          <tr><td>Запрещено убивать без RP-причины даже в облике.</td><td>Бан 3 дня</td></tr>
        </table>
        <div class="alert alert-warning">
          <strong>⚠️ Важно:</strong> SCP-953 должен использовать облик для RP, а не для RDM.
        </div>
      </div>
    </div>

    <hr class="divider">

    <!-- SCP-914 -->
    <h2 id="scp914">⚙️ Раздел XII. Правила SCP-914</h2>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
        <h3>Правила использования</h3>
        <ul>
          <li>Запрещено использование 914 в личных целях без RP-причины.</li>
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
          <tr><td><strong>Coarse</strong></td><td>Может ухудшить предмет</td><td>Да</td></tr>
          <tr><td><strong>1:1</strong></td><td>Обмен предмета</td><td>Да</td></tr>
          <tr><td><strong>Fine</strong></td><td>Улучшение предмета</td><td>Да</td></tr>
          <tr><td><strong>Very Fine</strong></td><td>SCP-049-2</td><td>Только по RP</td></tr>
        </table>
      </div>
    </div>

    <hr class="divider">

    <!-- ИНТЕРКОМ -->
    <h2 id="intercom">📢 Раздел XIII. Правила интеркома и чата</h2>

    <div class="alert alert-info">
      <strong>📢 Формат сообщения в интеркоме:</strong>
      <p>«[Имя/Позывной], [Уровень допуска], [Класс персонала], [Что требуется]».</p>
      <ul>
        <li><strong>Пример 1:</strong> «Говорит СБ-Капрал Иванов, 2 уровень допуска, класс C. Требуется подкрепление в Лёгкой зоне содержания».</li>
        <li><strong>Пример 2:</strong> «Говорит НС Петров, 3 уровень допуска, класс B. Внимание: побег SCP-173, КОД СИНИЙ».</li>
        <li><strong>Пример 3:</strong> «Говорит Капитан МОГ, 4 уровень допуска, класс B. Внимание: объявляю КОД КРАСНЫЙ».</li>
      </ul>
    </div>

    <div class="two-col-grid">
      <div>
        <h3>Запрещено в интеркоме</h3>
        <div class="alert alert-danger">
          <ul>
            <li>Спам и троллинг.</li>
            <li>Музыка без RP-причины.</li>
            <li>Крики, оскорбления, нецензурные звуки.</li>
            <li>Личные разговоры, не относящиеся к RP.</li>
            <li>Перебивание говорящего.</li>
            <li>Ложные коды угроз.</li>
          </ul>
        </div>
      </div>

      <div>
        <h3>Наказания за интерком</h3>
        <table class="data-table">
          <tr><th>Нарушение</th><th>1-е</th><th>2-е</th><th>3-е</th></tr>
          <tr><td>Спам</td><td>Мут 1 ч</td><td>Мут 6 ч</td><td>Бан 1 день</td></tr>
          <tr><td>Музыка</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
          <tr><td>Ложный код</td><td>Бан 7 дней</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
          <tr><td>Оскорбления</td><td>Мут 6 ч</td><td>Бан 1 день</td><td>Бан 7 дней</td></tr>
        </table>
      </div>
    </div>

    <h3>Правила чата</h3>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
        <h4>Текстовый чат</h4>
        <ul>
          <li>Запрещён спам (более 3 сообщений подряд).</li>
          <li>Запрещён флуд.</li>
          <li>Запрещены оскорбления.</li>
          <li>Запрещён Caps Lock без причины.</li>
          <li>Запрещена реклама других серверов.</li>
          <li>Запрещено обсуждение политики и религии.</li>
        </ul>
      </div>

      <div class="section" style="margin:0;">
        <h4>Голосовой чат</h4>
        <ul>
          <li>Запрещены громкие, неприятные звуки.</li>
          <li>Запрещён Soundpad без разрешения.</li>
          <li>Запрещён спам в голосовом чате.</li>
          <li>Запрещено перебивать других.</li>
          <li>Рация — только для RP-общения.</li>
        </ul>
      </div>
    </div>

    <hr class="divider">

    <!-- БАНЫ -->
    <h2 id="bans">⏱️ Раздел XIV. Сроки наказаний</h2>
    <div class="table-wrap">
      <table class="data-table">
        <tr><th>Нарушение</th><th>1-е</th><th>2-е</th><th>3-е</th></tr>
        <tr><td>Спам в чате</td><td>Мут 30 мин</td><td>Мут 2 ч</td><td>Мут 12 ч</td></tr>
        <tr><td>Оскорбления</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
        <tr><td>Громкий микрофон</td><td>Мут 1 ч</td><td>Мут 6 ч</td><td>Мут 24 ч</td></tr>
        <tr><td>Soundpad без разрешения</td><td>Мут 2 ч</td><td>Мут 12 ч</td><td>Бан 1 день</td></tr>
        <tr><td>No RDM (1-2)</td><td>Бан 1 день</td><td>Бан 3 дня</td><td>Бан 7 дней</td></tr>
        <tr><td>No RDM (3+)</td><td>Бан 7 дней</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
        <tr><td>Teamkill (случайный)</td><td>Предупреждение</td><td>Бан 1 день</td><td>Бан 3 дня</td></tr>
        <tr><td>Teamkill (намеренный)</td><td>Бан 3 дня</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
        <tr><td>Meta / Powergaming</td><td>Бан 3 дня</td><td>Бан 7 дней</td><td>Бан 14 дней</td></tr>
        <tr><td>FailRP</td><td>Предупреждение</td><td>Бан 1 день</td><td>Бан 3 дня</td></tr>
        <tr><td>Banhop</td><td>Бан 1 день</td><td>Бан 3 дня</td><td>Бан 7 дней</td></tr>
        <tr><td>Телепорт к 173 (3+)</td><td>Бан 7 дней</td><td>Бан 14 дней</td><td>Бан 30 дней</td></tr>
        <tr><td>Использование 914 без RP</td><td>Бан 3 дня</td><td>Бан 7 дней</td><td>Бан 14 дней</td></tr>
        <tr><td>Использование багов</td><td>Бан 30 дней</td><td>Бан 90 дней</td><td>Перманентный бан</td></tr>
        <tr><td>Читы / стороннее ПО</td><td colspan="3">Перманентный бан (без апелляции)</td></tr>
        <tr><td>Реклама серверов</td><td colspan="3">Перманентный бан</td></tr>
        <tr><td>Угрозы / травля</td><td colspan="3">Перманентный бан</td></tr>
        <tr><td>Обход бана</td><td colspan="3">Перманентный бан + IP-бан</td></tr>
        <tr><td>Подкуп администрации</td><td colspan="3">Перманентный бан</td></tr>
        <tr><td>Ложное объявление кода</td><td colspan="3">Бан 7 дней</td></tr>
        <tr><td>Неуважение к админам</td><td>Мут 1 ч</td><td>Мут 12 ч</td><td>Бан 3 дня</td></tr>
      </table>
    </div>

    <div class="alert alert-warning">
      <strong>⚠️ Примечание:</strong> Администрация оставляет за собой право изменять срок наказания. Рецидивы = удвоение срока.
    </div>

    <hr class="divider">

    <!-- АПЕЛЛЯЦИЯ -->
    <h2 id="appeal">📩 Раздел XV. Процедура апелляции</h2>
    <div class="two-col-grid">
      <div class="section" style="margin:0;">
        <h3>Как подать апелляцию</h3>
        <ol>
          <li>Зайди на наш Discord-сервер.</li>
          <li>Перейди в канал <strong>#апелляции</strong>.</li>
          <li>Создай тикет по шаблону.</li>
          <li>Укажи свой SteamID, причину бана и объяснение.</li>
        </ol>

        <h3>Сроки рассмотрения</h3>
        <ul>
          <li>Обычная апелляция — до 24 часов.</li>
          <li>Сложная апелляция — до 72 часов.</li>
          <li>Апелляция на перманентный бан — до 7 дней.</li>
        </ul>
      </div>

      <div>
        <h3>Правила апелляции</h3>
        <div class="alert alert-danger">
          <ul>
            <li>Запрещено оскорблять администрацию при апелляции.</li>
            <li>Запрещено дублировать апелляции.</li>
            <li>Запрещено подавать апелляцию с другого аккаунта.</li>
            <li>Решение по апелляции окончательное.</li>
            <li>Апелляция без доказательств рассматривается в последнюю очередь.</li>
          </ul>
        </div>

        <h3>Шаблон апелляции</h3>
        <div class="section" style="margin:0; padding:15px;">
          <p><strong>SteamID:</strong> [ваш ID]</p>
          <p><strong>Причина бана:</strong> [причина]</p>
          <p><strong>Кто забанил:</strong> [ник админа]</p>
          <p><strong>Объяснение:</strong> [почему бан несправедлив]</p>
          <p><strong>Доказательства:</strong> [ссылка]</p>
        </div>
      </div>
    </div>

    <hr class="divider">

    <div class="alert alert-info">
      <strong>💡 Помни:</strong> Соблюдение правил — залог комфортной игры для всех. 
      Если сомневаешься, спроси у администрации в Discord. Приятной игры на MV.Project!
    </div>

    <div class="center">
      <a href="https://discord.gg/ZCGAhTH6ep" class="discord">💬 ВСТУПИТЬ В DISCORD</a>
      <a href="https://t.me/mvprojectru" class="telegram">📢 TELEGRAM-КАНАЛ</a>
    </div>

    <div class="footer">
      <p>© 2026 MV.PROJECT | SCP FOUNDATION | MEDIUM ROLEPLAY</p>
      <p>Документ №SCP-RP-01 «ЗАСЛОН» | Версия 2.1 | Обновлено: сентябрь 2026</p>
      <p style="margin-top: 15px; color: #333;">CLASSIFIED — LEVEL 5 CLEARANCE REQUIRED</p>
    </div>

  </main>

  <script>
    document.querySelectorAll('.sidebar-nav a').forEach(link => {
      link.addEventListener('click', () => {
        if (window.innerWidth <= 900) {
          document.querySelector('.sidebar').classList.remove('open');
        }
      });
    });

    window.addEventListener('scroll', () => {
      const sections = document.querySelectorAll('h2[id]');
      const links = document.querySelectorAll('.sidebar-nav a');
      let current = '';
      sections.forEach(sec => {
        const top = sec.offsetTop - 100;
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
