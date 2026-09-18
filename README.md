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
    background: #050505;
    color: #c0c0c0;
    line-height: 1.9;
    padding: 0;
    background-image: 
      radial-gradient(circle at 20% 30%, rgba(255, 0, 0, 0.05) 0%, transparent 40%),
      radial-gradient(circle at 80% 70%, rgba(0, 255, 136, 0.05) 0%, transparent 40%);
  }

  /* ВЕРХНЯЯ ПАНЕЛЬ НА ВСЮ ШИРИНУ */
  .top-bar {
    position: sticky; top: 0; z-index: 1000;
    background: rgba(8,8,8,0.98);
    border-bottom: 2px solid #00ff88;
    padding: 15px 30px;
    display: flex; align-items: center; justify-content: space-between;
    backdrop-filter: blur(15px);
    box-shadow: 0 5px 30px rgba(0,0,0,0.8);
    flex-wrap: wrap; gap: 15px;
  }
  .top-bar .logo {
    color: #00ff88; font-weight: bold; font-size: 1.3em;
    letter-spacing: 3px;
    background: linear-gradient(90deg, #00ff88, #00cc66);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  }
  .top-bar .classif {
    background: #ff0000; color: #fff; padding: 5px 15px;
    font-size: 0.75em; letter-spacing: 3px; font-weight: bold;
    animation: blink 2s infinite;
  }
  @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0.5; } }

  /* НАВИГАЦИЯ НА ВСЮ ШИРИНУ */
  .top-nav {
    position: sticky; top: 72px; z-index: 999;
    background: rgba(10,10,10,0.98);
    padding: 12px 30px;
    border-bottom: 1px solid #1a1a1a;
    display: flex; flex-wrap: wrap; gap: 8px; justify-content: center;
    font-size: 0.85em;
    backdrop-filter: blur(10px);
  }
  .top-nav a {
    color: #00ff88; text-decoration: none; padding: 6px 14px;
    border-radius: 4px; transition: 0.2s; border: 1px solid transparent;
  }
  .top-nav a:hover {
    background: rgba(0,255,136,0.1); border-color: #00ff88;
  }

  /* КОНТЕНТ НА ВСЮ ШИРИНУ */
  .container {
    width: 100%;
    max-width: 100%;
    padding: 40px 60px;
  }
  @media (max-width: 900px) {
    .container { padding: 25px 20px; }
    .top-bar, .top-nav { padding: 12px 15px; }
    .top-nav { top: 100px; }
  }

  /* Шапка */
  .header { text-align: center; padding-bottom: 40px; border-bottom: 3px solid #00ff88; margin-bottom: 50px; }
  .classification {
    display: inline-block; background: #ff0000; color: #fff;
    padding: 8px 25px; font-weight: bold; letter-spacing: 4px;
    font-size: 0.9em; margin-bottom: 25px;
    animation: blink 2s infinite;
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
  }
  h3 {
    color: #66ffaa; font-size: clamp(1.05em, 2.2vw, 1.35em);
    margin: 35px 0 18px; padding-left: 18px;
    border-left: 4px solid #00cc66; letter-spacing: 1px;
  }

  p { margin: 12px 0; color: #b0b0b0; }
  strong { color: #00ff88; }

  ul, ol { padding-left: 30px; margin: 18px 0; }
  li { padding: 8px 0 8px 10px; color: #b0b0b0; border-bottom: 1px dotted #1a1a1a; }
  li:hover { color: #e0e0e0; }

  /* Таблицы */
  .data-table {
    width: 100%; border-collapse: collapse; margin: 25px 0;
    background: #0f0f0f; border: 1px solid #1f1f1f; font-size: 0.9em;
  }
  .data-table th {
    background: #0a2a1a; color: #00ff88; padding: 15px;
    text-align: left; font-weight: bold; letter-spacing: 1px;
    border-bottom: 2px solid #00ff88; text-transform: uppercase; font-size: 0.85em;
  }
  .data-table td { padding: 12px 15px; border-bottom: 1px solid #1a1a1a; color: #c0c0c0; }
  .data-table tr:hover td { background: #121212; }

  /* Цветные коды */
  .code-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
    gap: 25px; margin: 35px 0;
  }
  .code-card {
    padding: 25px; border-radius: 10px; background: #0f0f0f;
    border: 2px solid; transition: 0.3s; position: relative; overflow: hidden;
  }
  .code-card:hover { transform: translateY(-5px); box-shadow: 0 15px 40px rgba(0,0,0,0.6); }
  .code-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px;
  }
  .code-card h4 { font-size: 1.3em; margin-bottom: 15px; letter-spacing: 2px; }
  .code-card p { font-size: 0.95em; color: #999; margin-bottom: 12px; }
  .code-card ul { margin-top: 10px; font-size: 0.88em; }
  .code-card li { border-bottom: 1px dotted rgba(255,255,255,0.05); }

  .code-red { border-color: #ff0000; background: linear-gradient(135deg, #0f0f0f, rgba(255,0,0,0.08)); }
  .code-red::before { background: #ff0000; }
  .code-red h4 { color: #ff0000; text-shadow: 0 0 15px rgba(255,0,0,0.5); }

  .code-black { border-color: #444; background: linear-gradient(135deg, #0f0f0f, rgba(50,50,50,0.15)); }
  .code-black::before { background: #444; }
  .code-black h4 { color: #888; text-shadow: 0 0 15px rgba(100,100,100,0.5); }

  .code-green { border-color: #00ff88; background: linear-gradient(135deg, #0f0f0f, rgba(0,255,136,0.08)); }
  .code-green::before { background: #00ff88; }
  .code-green h4 { color: #00ff88; text-shadow: 0 0 15px rgba(0,255,136,0.5); }

  .code-blue { border-color: #4a90d9; background: linear-gradient(135deg, #0f0f0f, rgba(74,144,217,0.08)); }
  .code-blue::before { background: #4a90d9; }
  .code-blue h4 { color: #4a90d9; text-shadow: 0 0 15px rgba(74,144,217,0.5); }

  .code-yellow { border-color: #ffcc00; background: linear-gradient(135deg, #0f0f0f, rgba(255,204,0,0.08)); }
  .code-yellow::before { background: #ffcc00; }
  .code-yellow h4 { color: #ffcc00; text-shadow: 0 0 15px rgba(255,204,0,0.5); }

  .code-orange { border-color: #ff8800; background: linear-gradient(135deg, #0f0f0f, rgba(255,136,0,0.08)); }
  .code-orange::before { background: #ff8800; }
  .code-orange h4 { color: #ff8800; text-shadow: 0 0 15px rgba(255,136,0,0.5); }

  .code-purple { border-color: #9013fe; background: linear-gradient(135deg, #0f0f0f, rgba(144,19,254,0.08)); }
  .code-purple::before { background: #9013fe; }
  .code-purple h4 { color: #9013fe; text-shadow: 0 0 15px rgba(144,19,254,0.5); }

  /* Предупреждения */
  .alert {
    padding: 20px 25px; border-radius: 8px; margin: 25px 0;
    border-left: 6px solid; font-size: 0.95em;
  }
  .alert-danger { background: rgba(255, 0, 0, 0.08); border-color: #ff0000; color: #ff8888; }
  .alert-warning { background: rgba(255, 170, 0, 0.08); border-color: #ffaa00; color: #ffcc66; }

  /* Секции */
  .section {
    margin: 40px 0; padding: 30px; background: #0d0d0d;
    border-radius: 10px; border: 1px solid #1a1a1a;
  }

  /* Футер */
  .footer {
    text-align: center; margin-top: 70px; padding: 40px 20px;
    border-top: 2px solid #1a1a1a; color: #555;
    font-size: 0.85em; letter-spacing: 1px;
    background: #080808;
  }
  .discord {
    display: inline-block; background: #5865F2; color: white;
    text-decoration: none; padding: 10px 20px; border-radius: 5px;
    margin-top: 15px; font-weight: bold; transition: 0.3s;
  }
  .discord:hover { background: #4752c4; }
</style>
</head>
<body>

  <div class="top-bar">
    <div class="logo">MV.PROJECT // SCP FOUNDATION</div>
    <div class="classif">ДОСТУП ОГРАНИЧЕН</div>
  </div>

  <div class="top-nav">
    <a href="#levels">Уровни допуска</a>
    <a href="#classes">Классы персонала</a>
    <a href="#protocols">Протоколы тревог</a>
    <a href="#rules">Общие правила</a>
  </div>

  <div class="container">
    
    <div class="header">
      <div class="classification">СЕКРЕТНО // СОВ СЕКРЕТНО</div>
      <h1>ОБЩИЙ УСТАВ ЗОНЫ-02</h1>
      <div class="subtitle">Свод внутренних правил и регламентов безопасности комплекса</div>
      <div class="codename">ДОКУМЕНТ СФОРМИРОВАН АВТОМАТИЧЕСКИ СИСТЕМОЙ САС «СИГМА»</div>
    </div>

    <div class="alert alert-danger">
      <strong>ВНИМАНИЕ:</strong> Несанкционированное чтение данного документа карается введением меметического агента уничтожения «Берримен-Лангфорд» и последующей ликвидацией.
    </div>

    <!-- СЕКЦИЯ 1: УРОВНИ ДОПУСКА -->
    <div class="section" id="levels">
      <h2>1. Иерархия уровней допуска</h2>
      <p>Уровень допуска определяет рамки авторизации сотрудника, его право на перемещение по блокам комплекса и доступ к защищенным информационным базам.</p>
      
      <table class="data-table">
        <thead>
          <tr>
            <th style="width: 15%;">Уровень</th>
            <th style="width: 25%;">Тип допуска</th>
            <th style="width: 35%;">Примеры должностей</th>
            <th style="width: 25%;">Полномочия / Права</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Уровень 0</strong></td>
            <td>Общий (Для посторонних)</td>
            <td>Технический персонал, уборщики, логисты</td>
            <td>Вход только в безопасные зоны Зоны-02. Нет доступа к SCP.</td>
          </tr>
          <tr>
            <td><strong>Уровень 1</strong></td>
            <td>Ограниченный</td>
            <td>Младшие научные сотрудники, охрана (Рядовые)</td>
            <td>Допуск к объектам класса Безопасный. Запрещен вход в ТЗС.</td>
          </tr>
          <tr>
            <td><strong>Уровень 2</strong></td>
            <td>Конфиденциальный</td>
            <td>Научные сотрудники, Служба Безопасности (СБ)</td>
