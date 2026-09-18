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
  h4 { color: #88ffbb; font-size: 1.1em; margin: 25px 0 12px; letter-spacing: 1px; }

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
  .code-card h4 { font-size: 1.5em; margin-bottom: 15px; letter-spacing: 3px; }
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
  .alert-info { background: rgba(0, 255, 136, 0.05); border-color: #00ff88; color: #88ffbb; }

  /* Кодовые блоки */
  .code-block {
    background: #0a0a0a; border: 1px solid #1f1f1f;
    border-left: 5px solid #00ff88; padding: 18px 22px; margin: 18px 0;
    font-family: 'Consolas', monospace; border-radius: 4px;
  }
  .code-block .code { color: #ffaa00; font-weight: bold; letter-spacing: 2px; font-size: 1.1em; }
  .code-block .desc { color: #999; font-size: 0.92em; margin-top: 8px; }

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
    padding: 18px 50px; border-radius: 10px; text-decoration: none;
    font-weight: bold; margin: 25px 0; transition: 0.3s;
    letter-spacing: 2px; font-size: 1.05em;
  }
  .discord:hover {
    background: #4752c4; transform: scale(1.05);
    box-shadow: 0 0 40px rgba(88, 101, 242, 0.6);
  }

  .center { text-align: center; }

  /* Аккордеон */
  details {
    background: #0d0d0d; border: 1px solid #1a1a1a;
    border-radius: 6px; margin: 12px 0; overflow: hidden;
  }
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

  .divider {
    height: 2px; background: linear-gradient(90deg, transparent, #00ff88, transparent);
    margin: 50px 0; border: none;
  }
</style>
</head>
<body>

  <!-- ВЕРХНЯЯ ПАНЕЛЬ -->
  <div class="top-bar">
    <div class="logo">MV.PROJECT</div>
    <div class="classif">⚠ CLASSIFIED — LEVEL 5 ⚠</div>
  </div>

  <!-- НАВИГАЦИЯ -->
  <div class="top-nav">
    <a href="#codes">🚨 КОДЫ</a>
    <a href="#general">📜 ОБЩИЕ</a>
    <a href="#rp">🎭 RP</a>
    <a href="#classes">👥 КЛАССЫ</a>
    <a href="#scp">🧬 SCP</a>
    <a href="#scp914">⚙️ SCP-914</a>
    <a href="#doors">🚪 ДВЕРИ</a>
    <a href="#weapons">🔫 ОРУЖИЕ</a>
    <a href="#chat">💬 ЧАТ</a>
    <a href="#admin">👑 АДМИНЫ</a>
    <a href="#bans">⏱️ БАНЫ</a>
    <a href="#appeal">📩 АПЕЛЛЯЦИЯ</a>
  </div>

  <div class="container">

    <!-- ШАПКА -->
    <div class="header">
      <div class="classification">⚠ CLASSIFIED — LEVEL 5 CLEARANCE ⚠</div>
      <h1>MV.PROJECT</h1>
      <p class="subtitle">SCP FOUNDATION | MEDIUM ROLEPLAY</p>
      <p class="codename">Уставной документ №SCP-RP-01 «ЗАСЛОН» | Зона 19</p>
    </div>

    <div class="alert alert-danger">
      <strong>⛔ ВНИМАНИЕ:</strong> Данный устав обязателен к прочтению каждому игроку. 
      Заходя на сервер <strong>MV.Project</strong>, вы автоматически соглашаетесь с правилами. 
      <span class="critical">Незнание правил не освобождает от ответственности.</span>
    </div>

    <!-- РАЗДЕЛ КОДЫ -->
    <h2 id="codes">🚨 Раздел I. Цветовые коды угроз</h2>
    <p>Персонал комплекса обязан знать и правильно реагировать на цветовые коды. Коды объявляются администрацией или автоматически при определённых событиях.</p>

    <div class="code-grid">
      <div class="code-card code-green">
        <h4>🟢 КОД ЗЕЛЁНЫЙ</h4>
        <p><strong>Статус:</strong> Полная безопасность</p>
        <p>Комплекс работает в штатном режиме. Все SCP в камерах содержания. Угроз нет.</p>
        <ul>
          <li>Персонал работает по обычному расписанию</li>
          <li>Класс D сопровождается охраной</li>
          <li>Тесты SCP разрешены</li>
          <li>Охрана на постах</li>
        </ul>
      </div>

      <div class="code-card code-blue">
        <h4>🔵 КОД СИНИЙ</h4>
        <p><strong>Статус:</strong> Незначительное нарушение</p>
        <p>Обнаружено незначительное нарушение. Требуется персонал для решения ситуации.</p>
        <ul>
          <li>Мелкое нарушение содержания</li>
          <li>Бунт в блоке Класса D</li>
          <li>Побег одного SCP</li>
          <li>Требуется 2-3 охранника</li>
        </ul>
      </div>

      <div class="code-card code-yellow">
        <h4>🟡 КОД ЖЁЛТЫЙ</h4>
        <p><strong>Статус:</strong> Угроза персоналу</p>
        <p>Обнаружена угроза для персонала комплекса. Требуется усиление охраны.</p>
        <ul>
          <li>Активная стрельба на территории</li>
          <li>Прорыв ПХ через КПП</li>
          <li>Множественные побеги SCP (2-3)</li>
          <li>Требуется МОГ</li>
        </ul>
      </div>

      <div class="code-card code-orange">
        <h4>🟠 КОД ОРАНЖЕВЫЙ</h4>
        <p><strong>Статус:</strong> Множественное нарушение</p>
        <p>Массовое нарушение содержания. Требуется немедленное вмешательство МОГ.</p>
        <ul>
          <li>4+ SCP на свободе</li>
          <li>Захват комплекса ПХ</li>
          <li>Полная потеря контроля над зоной</li>
          <li>Эвакуация персонала</li>
        </ul>
      </div>

      <div class="code-card code-red">
        <h4>🔴 КОД КРАСНЫЙ</h4>
        <p><strong>Статус:</strong> КРИТИЧЕСКАЯ УГРОЗА</p>
        <p>Критическая угроза всему комплексу. Полное нарушение содержания. Активация протокола «Омега».</p>
        <ul>
          <li>Все SCP на свободе</li>
          <li>Комплекс захвачен врагом</li>
          <li>Угроза человечеству</li>
          <li>Разрешено применение БГ</li>
          <li>Эвакуация невозможна</li>
        </ul>
      </div>

      <div class="code-card code-black">
        <h4>⚫ КОД ЧЁРНЫЙ</h4>
        <p><strong>Статус:</strong> КОМПЛЕКС ПОТЕРЯН</p>
        <p>Комплекс потерян. Активация ядерной боеголовки. Персонал обязан покинуть зону любой ценой.</p>
        <ul>
          <li>БГ активирована</li>
          <li>Обратный отсчёт 90 секунд</li>
          <li>Эвакуация на поверхность</li>
          <li>Все выжившие — в безопасности</li>
          <li>Комплекс будет уничтожен</li>
        </ul>
      </div>

      <div class="code-card code-purple">
        <h4>🟣 КОД ФИОЛЕТОВЫЙ</h4>
        <p><strong>Статус:</strong> Аномальный объект</p>
        <p>Обнаружен новый, ранее неизвестный аномальный объект. Требуется группа исследования.</p>
        <ul>
          <li>Обнаружен неизвестный SCP</li>
          <li>Требуется отряд учёных</li>
          <li>Классификация объекта</li>
          <li>Оцепление зоны</li>
        </ul>
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

    <!-- ОБЩИЕ ПРАВИЛА -->
    <h2 id="general">📜 Раздел II. Общие правила</h2>
    <div class="section">
      <h3>2.1. Основные принципы сервера</h3>
      <p>Сервер <strong>MV.Project</strong> — это <span class="highlight">Medium RP</span> проект, что означает: вы должны играть роль персонажа, но без фанатизма. Приоритет — интересный геймплей и комфорт для всех игроков.</p>
      <ul>
        <li><strong>2.1.1.</strong> Уважение к другим игрокам — основа сервера.</li>
        <li><strong>2.1.2.</strong> Запрещены любые формы дискриминации (по полу, расе, религии, возрасту).</li>
        <li><strong>2.1.3.</strong> Запрещены угрозы в реальной жизни, доксинг, преследование.</li>
        <li><strong>2.1.4.</strong> Запрещена пропаганда терроризма, насилия, наркотиков.</li>
        <li><strong>2.1.5.</strong> Запрещены любые действия, направленные на разрушение сервера.</li>
      </ul>

      <h3>2.2. Возрастные ограничения</h3>
      <ul>
        <li><strong>2.2.1.</strong> Минимальный возраст для игры — <span class="highlight">14 лет</span>.</li>
        <li><strong>2.2.2.</strong> При подозрении в несоответствии возраста — администрация вправе запросить подтверждение.</li>
        <li><strong>2.2.3.</strong> Обман по поводу возраста = перманентный бан.</li>
        <li><strong>2.2.4.</strong> Дети младше 14 лет — кик с возможностью возврата после достижения возраста.</li>
      </ul>

      <h3>2.3. Аккаунты и SteamID</h3>
      <ul>
        <li><strong>2.3.1.</strong> Запрещено использование нескольких аккаунтов для обхода наказаний.</li>
        <li><strong>2.3.2.</strong> Запрещена передача аккаунта третьим лицам.</li>
        <li><strong>2.3.3.</strong> Запрещено использование VAC-забаненных аккаунтов.</li>
        <li><strong>2.3.4.</strong> Обход бана = перманентный бан + IP-бан.</li>
      </ul>
    </div>

    <hr class="divider">

    <!-- RP ПРАВИЛА -->
    <h2 id="rp">🎭 Раздел III. RP-правила</h2>
    <div class="section">
      <h3>3.1. Что такое RP?</h3>
      <p><strong>RP (Roleplay)</strong> — это отыгрыш роли персонажа. Вы должны вести себя так, как вёл бы себя ваш персонаж в реальной ситуации. На сервере <span class="highlight">MV.Project</span> действует Medium RP — это значит, что вы должны играть роль, но не обязаны отыгрывать каждую мелочь.</p>

      <h3>3.2. Основные запреты</h3>

      <h4>❌ No RDM (Random Deathmatch)</h4>
      <ul>
        <li>Запрещено убивать игроков без RP-причины.</li>
        <li><strong>RP-причина</strong> — это логичное обоснование: самозащита, приказ, RP-конфликт.</li>
        <li>Убийство без причины = бан от 1 до 30 дней.</li>
        <li>Пример RDM: убить Класс D просто потому, что он вам не понравился.</li>
      </ul>

      <h4>❌ No Teamkill</h4>
      <ul>
        <li>Запрещено убивать союзников (своих по фракции).</li>
        <li>Даже случайный TK = предупреждение, повторный — бан.</li>
        <li>Намеренный TK = бан от 3 дней.</li>
      </ul>

      <h4>❌ No Metagaming (Meta)</h4>
      <ul>
        <li>Запрещено использовать информацию, которую ваш персонаж не может знать.</li>
        <li>Пример: вы Класс D, но в Discord увидели, что МОГ идёт в вашу зону — использовать это нельзя.</li>
        <li>Meta = бан от 3 дней.</li>
      </ul>

      <h4>❌ No Powergaming</h4>
      <ul>
        <li>Запрещены действия, невозможные в реальной жизни.</li>
        <li>Пример: в одиночку убить 5 вооружённых МОГ без ранения.</li>
        <li>Powergaming = бан от 3 дней.</li>
      </ul>

      <h4>❌ No Banhop (Баннихоп)</h4>
      <ul>
        <li>Запрещён баннихоп во время побега.</li>
        <li>Баннихоп = прыжки для ускорения передвижения.</li>
        <li>Разрешено: прыгать при ходьбе без цели ускориться.</li>
        <li>Запрещено: прыгать при побеге от МОГ, чтобы быстрее бежать.</li>
        <li>Баннихоп = бан от 1 дня.</li>
      </ul>

      <h4>❌ No FailRP</h4>
      <ul>
        <li>Запрещено нарушать логику персонажа.</li>
        <li>Пример: учёный стреляет из винтовки как профессиональный военный.</li>
        <li>FailRP = предупреждение или бан от 1 дня.</li>
      </ul>

      <h3>3.3. Терминология</h3>
      <table class="data-table">
        <tr><th>Термин</th><th>Значение</th></tr>
        <tr><td><strong>RDM</strong></td><td>Random Deathmatch — убийство без причины</td></tr>
        <tr><td><strong>Teamkill</strong></td><td>Убийство союзника</td></tr>
        <tr><td><strong>Meta</strong></td><td>Использование внеигровой информации</td></tr>
        <tr><td><strong>Powergaming</strong></td><td>Действия, невозможные в реальности</td></tr>
        <tr><td><strong>Banhop</strong></td><td>Прыжки для ускорения при побеге</td></tr>
        <tr><td><strong>FailRP</strong></td><td>Нарушение логики персонажа</td></tr>
        <tr><td><strong>RP-причина</strong></td><td>Логичное обоснование действия</td></tr>
      </table>
    </div>

    <hr class="divider">

    <!-- КЛАССЫ -->
    <h2 id="classes">👥 Раздел IV. Правила классов</h2>

    <details>
      <summary>🟠 Класс D — Персонал класса D</summary>
      <ul>
        <li><strong>Роль:</strong> Заключённые, используемые для тестирования SCP.</li>
        <li>Обязаны слушаться охрану и учёных.</li>
        <li>Запрещено устраивать бунт без RP-причины.</li>
        <li>Побег разрешён, но без Banhop.</li>
        <li>Запрещено намеренно мешать тестам.</li>
        <li>При побеге через 914 — соблюдайте правила SCP-914.</li>
        <li>Запрещено вступать в сговор с SCP без RP-причины.</li>
        <li>Запрещено выдавать себя за другого игрока.</li>
        <li>При КОДЕ КРАСНОМ+ разрешено всё для выживания.</li>
      </ul>
    </details>

    <details>
      <summary>🔵 Учёные</summary>
      <ul>
        <li><strong>Роль:</strong> Научный персонал, проводящий исследования SCP.</li>
        <li>Обязаны проводить тесты SCP (по заданию).</li>
        <li>Запрещено покидать комплекс без причины.</li>
        <li>Обязаны сотрудничать с МОГ.</li>
        <li>Запрещено намеренно убивать SCP без причины.</li>
        <li>При опасности — обязаны эвакуироваться.</li>
        <li>Запрещено давать Класс D предметы без разрешения.</li>
        <li>Запрещено вступать в контакт с ПХ без необходимости.</li>
        <li>Обязаны докладывать о нарушениях.</li>
      </ul>
    </details>

    <details>
      <summary>🟢 Охрана Фонда (Facility Guard)</summary>
      <ul>
        <li><strong>Роль:</strong> Охрана комплекса, следящая за порядком.</li>
        <li>Обязаны следить за порядком в зонах.</li>
        <li>Запрещено убивать Класс D без причины.</li>
        <li>Обязаны сопровождать учёных.</li>
        <li>Запрещено покидать пост без приказа.</li>
        <li>При КОДЕ 3+ — обязаны защищать комплекс.</li>
        <li>Запрещено сотрудничать с ПХ.</li>
        <li>Обязаны подчиняться МОГ при их прибытии.</li>
        <li>Запрещено выдавать карты Класс D.</li>
      </ul>
    </details>

    <details>
      <summary>🔴 МОГ — Мобильная Оперативная Группа (NTF)</summary>
      <ul>
        <li><strong>Роль:</strong> Элитное подразделение Фонда для решения критических ситуаций.</li>
        <li>Действуют по протоколу.</li>
        <li>Запрещено убивать учёных и охрану.</li>
        <li>Обязаны защищать комплекс от ПХ.</li>
        <li>Запрещено самовольно покидать комплекс.</li>
        <li>При КОДЕ 4 — обязаны вернуть SCP в камеры.</li>
        <li>Запрещено использовать гранаты в закрытых помещениях с персоналом.</li>
        <li>Обязаны докладывать о ситуации командованию.</li>
        <li>Запрещено оставлять раненых союзников.</li>
      </ul>
    </details>

    <details>
      <summary>⚫ ПХ — Повстанцы Хаоса (Chaos Insurgency)</summary>
      <ul>
        <li><strong>Роль:</strong> Вражеская организация, цель — освобождение SCP.</li>
        <li>Цель — освобождение SCP и захват комплекса.</li>
        <li>Запрещён RDM без RP-причины.</li>
        <li>Запрещено убивать своих (Teamkill).</li>
        <li>Действуют по RP-сценарию.</li>
        <li>Запрещено использовать баги при захвате.</li>
        <li>Обязаны подчиняться командиру отряда.</li>
        <li>Запрещено убивать Класс D, если они не сопротивляются.</li>
        <li>При отступлении — обязаны прикрывать союзников.</li>
      </ul>
    </details>

    <details>
      <summary>🟣 SCP-объекты</summary>
      <ul>
        <li><strong>Роль:</strong> Аномальные сущности, содержащиеся Фондом.</li>
        <li>Обязаны отыгрывать свою роль.</li>
        <li>Запрещено фармить убийства без причины.</li>
        <li>SCP-049 обязан лечить, а не убивать всех подряд.</li>
        <li>SCP-173 обязан двигаться только при отсутствии наблюдения.</li>
        <li>SCP-079 обязан сотрудничать с другими SCP.</li>
        <li>Запрещено намеренно мешать другим SCP.</li>
        <li>Запрещено кемперить (стоять на одном месте и убивать всех).</li>
        <li>При КОДЕ ЧЁРНОМ — обязаны покинуть комплекс или погибнуть.</li>
      </ul>
    </details>

    <hr class="divider">

    <!-- SCP -->
    <h2 id="scp">🧬 Раздел V. Правила SCP-объектов</h2>
    <div class="section">
      <table class="data-table">
        <tr><th>SCP</th><th>Правило</th><th>Наказание</th></tr>
        <tr><td><strong>SCP-173</strong></td><td>Двигается только при отсутствии зрительного контакта. Запрещён телепорт к 173 при 3+ наблюдателях.</td><td>Бан 7-30 дней</td></tr>
        <tr><td><strong>SCP-049</strong></td><td>Обязан лечить, а не убивать всех подряд. Поднимает зомби только по RP-причине.</td><td>Бан 3-7 дней</td></tr>
        <tr><td><strong>SCP-106</strong></td><td>Запрещено намеренно отправлять игроков в карманное измерение без RP-причины.</td><td>Бан 3-7 дней</td></tr>
        <tr><td><strong>SCP-096</strong></td><td>Запрещено намеренно смотреть на 096, чтобы вызвать агрессию.</td><td>Бан 1-3 дня</td></tr>
        <tr><td><strong>SCP-939</strong></td><td>Обязан использовать звук для охоты. Запрещено игнорирование правил.</td><td>Предупреждение / Бан 1 день</td></tr>
        <tr><td><strong>SCP-3114</strong></td><td>Обязан маскироваться под человека. Запрещено быстрое раскрытие.</td><td>Бан 1-3 дня</td></tr>
        <tr><td><strong>SCP-079</strong></td><td>Обязан сотрудничать с SCP. Запрещено игнорирование просьб.</td><td>Предупреждение / Бан 1 день</td></tr>
      </table>

      <div class="alert alert-warning">
        <strong>⚠️ Важно:</strong> SCP-объекты не имеют права нарушать правила сервера. 
        Если вы SCP и нарушаете правила (например, кемперите у выхода) — вы будете наказаны как обычный игрок.
      </div>
    </div>

    <hr class="divider">

    <!-- SCP-914 -->
    <h2 id="scp914">⚙️ Раздел VI. Правила SCP-914</h2>
    <div class="section">
      <h3>6.1. Общие правила</h3>
      <ul>
        <li><strong>6.1.1.</strong> Запрещено использование 914 в личных целях без RP-причины.</li>
        <li><strong>6.1.2.</strong> Запрещено превращение в SCP-049-2 без RP-причины.</li>
        <li><strong>6.1.3.</strong> Запрещено использование 914 для обхода правил.</li>
        <li><strong>6.1.4.</strong> При использовании 914 обязательно соблюдать очередь.</li>
        <li><strong>6.1.5.</strong> Запрещено намеренное закидывание людей в 914 на режимы, ведущие к смерти.</li>
      </ul>

      <h3>6.2. Режимы 914</h3>
      <table class="data-table">
        <tr><th>Режим</th><th>Эффект</th><th>Разрешено?</th></tr>
        <tr><td><strong>Rough</strong></td><td>Грубая обработка, часто ломает предметы</td><td>Да</td></tr>
        <tr><td><strong>Coarse</strong></td><td>Обработка, может ухудшить предмет</td><td>Да</td></tr>
        <tr><td><strong>1:1</strong></td><td>Обмен предмета на аналогичный</td><td>Да</td></tr>
        <tr><td><strong>Fine</strong></td><td>Улучшение предмета</td><td>Да</td></tr>
        <tr><td><strong>Very Fine</strong></td><td>Максимальное улучшение, превращение в SCP-049-2</td><td>Только по RP</td></tr>
      </table>

      <div class="alert alert-danger">
        <strong>⛔ Нарушение правил SCP-914 = бан от 3 до 30 дней в зависимости от тяжести.</strong>
      </div>
    </div>

    <hr class="divider">

    <!-- ДВЕРИ -->
    <h2 id="doors">🚪 Раздел VII. Правила кодовых дверей</h2>
    <div class="section">
      <ul>
        <li><strong>7.1.</strong> Запрещено открывать двери персоналу без соответствующего допуска.</li>
        <li><strong>7.2.</strong> Запрещено взламывать двери без RP-причины.</li>
        <li><strong>7.3.</strong> При использовании кодовой карты — обязательно её наличие в инвентаре.</li>
        <li><strong>7.4.</strong> Запрещено передавать карты персоналу без допуска.</li>
        <li><strong>7.5.</strong> Запрещено использовать административные карты в RP.</li>
        <li><strong>7.6.</strong> Запрещено «держать» дверь открытой для врагов.</li>
        <li><strong>7.7.</strong> Запрещено использовать баги дверей.</li>
        <li><strong>7.8.</strong> При КОДЕ 3+ двери блокируются автоматически.</li>
      </ul>

      <h3>Уровни допуска</h3>
      <table class="data-table">
        <tr><th>Карта</th><th>Доступ</th><th>Кому</th></tr>
        <tr><td><strong>Janitor (Уборщик)</strong></td><td>Подсобные помещения</td><td>Класс D</td></tr>
        <tr><td><strong>Zone-1</strong></td><td>Лёгкая зона</td><td>Учёные, охрана</td></tr>
        <tr><td><strong>Zone-2</strong></td><td>Тяжёлая зона</td><td>Старшие учёные, МОГ</td></tr>
        <tr><td><strong>Zone-3</strong></td><td>Зона ЕС</td><td>Командование</td></tr>
        <tr><td><strong>O5</strong></td><td>Все зоны</td><td>Совет О5</td></tr>
      </table>
    </div>

    <hr class="divider">

    <!-- ОРУЖИЕ -->
    <h2 id="weapons">🔫 Раздел VIII. Правила использования оружия</h2>
    <div class="section">
      <h3>8.1. Общие правила</h3>
      <ul>
        <li><strong>8.1.1.</strong> Запрещено стрелять в мирных без RP-причины.</li>
        <li><strong>8.1.2.</strong> Запрещено использовать гранаты в закрытых помещениях с союзниками.</li>
        <li><strong>8.1.3.</strong> Запрещено стрелять в SCP без RP-причины (если вы не МОГ).</li>
        <li><strong>8.1.4.</strong> Запрещено использовать оружие для RDM.</li>
        <li><strong>8.1.5.</strong> Запрещено стрелять в воздух без причины.</li>
      </ul>

      <h3>8.2. Правила для МОГ</h3>
      <ul>
        <li>МОГ имеет право открывать огонь по Класс D при сопротивлении.</li>
        <li>МОГ обязан предупредить перед стрельбой (если есть возможность).</li>
        <li>Запрещено стрелять в учёных и охрану.</li>
        <li>Запрещено использовать тяжёлое оружие в зонах с персоналом.</li>
      </ul>

      <h3>8.3. Правила для охраны</h3>
      <ul>
        <li>Охрана имеет право применять оружие только при угрозе жизни.</li>
        <li>Запрещено стрелять в Класс D без предупреждения.</li>
        <li>Разрешено использовать дубинку для усмирения.</li>
      </ul>

      <h3>8.4. Правила для ПХ</h3>
      <ul>
        <li>ПХ имеет право стрелять в МОГ и охрану.</li>
        <li>Запрещено стрелять в Класс D без RP-причины.</li>
        <li>Запрещено использовать гранаты в зонах с заложниками.</li>
      </ul>
    </div>

    <hr class="divider">

    <!-- ЧАТ -->
    <h2 id="chat">💬 Раздел IX. Правила чата и голосового общения</h2>
    <div class="section">
      <h3>9.1. Текстовый чат</h3>
      <ul>
        <li><strong>9.1.1.</strong> Запрещён спам (более 3 сообщений подряд).</li>
        <li><strong>9.1.2.</strong> Запрещён флуд (бессмысленные сообщения).</li>
        <li><strong>9.1.3.</strong> Запрещены оскорбления в адрес игроков и администрации.</li>
        <li><strong>9.1.4.</strong> Запрещено использование Caps Lock без причины.</li>
        <li><strong>9.1.5.</strong> Запрещена реклама других серверов.</li>
        <li><strong>9.1.6.</strong> Запрещено обсуждение политики и религии.</li>
        <li><strong>9.1.7.</strong> Запрещено использование нецензурной лексики без RP-контекста.</li>
      </ul>

      <h3>9.2. Голосовой чат</h3>
      <ul>
        <li><strong>9.2.1.</strong> Запрещены громкие, неприятные звуки в микрофон.</li>
        <li><strong>9.2.2.</strong> Запрещено использование Soundpad без разрешения.</li>
        <li><strong>9.2.3.</strong> Запрещён спам в голосовом чате.</li>
        <li><strong>9.2.4.</strong> Запрещено перебивать других игроков.</li>
        <li><strong>9.2.5.</strong> Запрещено использовать микрофон для оскорблений.</li>
        <li><strong>9.2.6.</strong> При отсутствии микрофона — используйте текстовый чат.</li>
      </ul>

      <h3>9.3. Рация и интерком</h3>
      <ul>
        <li><strong>9.3.1.</strong> Рация используется только для RP-общения.</li>
        <li><strong>9.3.2.</strong> Запрещено использовать рацию для спама.</li>
        <li><strong>9.3.3.</strong> Интерком используется только для объявлений.</li>
        <li><strong>9.3.4.</strong> Запрещено использовать интерком для оскорблений.</li>
        <li><strong>9.3.5.</strong> Запрещено включать музыку через интерком без RP-причины.</li>
      </ul>
    </div>

    <hr class="divider">

    <!-- АДМИНЫ -->
    <h2 id="admin">👑 Раздел X. Правила для администрации</h2>
    <div class="section">
      <h3>10.1. Общие правила</h3>
      <ul>
        <li><strong>10.1.1.</strong> Администрация обязана соблюдать все правила сервера.</li>
        <li><strong>10.1.2.</strong> Администрация не имеет права использовать свои полномочия в личных целях.</li>
        <li><strong>10.1.3.</strong> Администрация обязана быть вежливой с игроками.</li>
        <li><strong>10.1.4.</strong> Администрация обязана объяснять причину наказания.</li>
        <li><strong>10.1.5.</strong> Администрация не имеет права наказывать без доказательств.</li>
      </ul>

      <h3>10.2. Запрещено администрации</h3>
      <ul>
        <li>Использовать админ-команды в RP-целях (летать, телепортироваться).</li>
        <li>Наказывать игроков за личную неприязнь.</li>
        <li>Использовать Godmode в бою.</li>
        <li>Выдавать предметы игрокам без RP-причины.</li>
        <li>Разглашать внутреннюю информацию сервера.</li>
        <li>Обсуждать других админов с игроками.</li>
        <li>Использовать нецензурную лексику в админ-чате.</li>
      </ul>

      <h3>10.3. Наказания для администрации</h3>
      <ul>
        <li><strong>Выговор</strong> — за мелкие нарушения.</li>
        <li><strong>Понижение</strong> — за систематические нарушения.</li>
        <li><strong>Снятие</strong> — за грубые нарушения.</li>
        <li><strong>ЧСА</strong> — за предательство интересов сервера.</li>
      </ul>
    </div>

    <hr class="divider">

    <!-- БАНЫ -->
    <h2 id="bans">⏱️ Раздел XI. Сроки наказаний</h2>
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
      <tr><td>Ложный вызов админа</td><td>Предупреждение</td><td>Мут 2 ч</td><td>Бан 1 день</td></tr>
      <tr><td>Ложное объявление кода</td><td colspan="3">Бан 7 дней</td></tr>
      <tr><td>Неуважение к админам</td><td>Мут 1 ч</td><td>Мут 12 ч</td><td>Бан 3 дня</td></tr>
    </table>

    <div class="alert alert-warning">
      <strong>⚠️ Примечание:</strong> Администрация оставляет за собой право изменять срок наказания 
      в зависимости от ситуации. Рецидивы = удвоение срока. При тяжких нарушениях 
      наказание может быть выдано сразу без предупреждения.
    </div>

    <hr class="divider">

    <!-- АПЕЛЛЯЦИЯ -->
    <h2 id="appeal">📩 Раздел XII. Процедура апелляции</h2>
    <div class="section">
      <h3>12.1. Как подать апелляцию</h3>
      <ol>
        <li>Зайди на наш Discord-сервер.</li>
        <li>Перейди в канал <strong>#апелляции</strong>.</li>
        <li>Создай тикет по шаблону.</li>
        <li>Укажи свой SteamID, причину бана и объяснение.</li>
        <li>Приложи доказательства (если есть).</li>
      </ol>

      <h3>12.2. Срок рассмотрения</h3>
      <ul>
        <li>Обычная апелляция — до 24 часов.</li>
        <li>Сложная апелляция — до 72 часов.</li>
        <li>Апелляция на перманентный бан — до 7 дней.</li>
      </ul>

      <h3>12.3. Правила апелляции</h3>
      <ul>
        <li>Запрещено оскорблять администрацию при апелляции.</li>
        <li>Запрещено дублировать апелляции.</li>
        <li>Запрещено подавать апелляцию с другого аккаунта.</li>
        <li>Решение по апелляции окончательное.</li>
        <li>Апелляция без доказательств рассматривается в последнюю очередь.</li>
      </ul>

      <div class="alert alert-danger">
        <strong>⛔ Оскорбление администрации при апелляции = автоматический отказ 
        и увеличение срока наказания.</strong>
      </div>

      <h3>12.4. Шаблон апелляции</h3>
      <div class="code-block">
        <div class="code">SteamID: [ваш SteamID]</div>
        <div class="desc">Причина бана: [причина]</div>
        <div class="desc">Кто забанил: [ник админа]</div>
        <div class="desc">Объяснение: [почему вы считаете бан несправедливым]</div>
        <div class="desc">Доказательства: [ссылка на скриншот/видео]</div>
      </div>
    </div>

    <hr class="divider">

    <div class="alert alert-info">
      <strong>💡 Помни:</strong> Соблюдение правил — залог комфортной игры для всех. 
      Если сомневаешься, спроси у администрации в Discord. Приятной игры на MV.Project!
    </div>

    <div class="center">
      <a href="https://discord.gg/ZCGAhTH6ep" class="discord">💬 ВСТУПИТЬ В DISCORD</a>
    </div>

  </div>

  <!-- ФУТЕР -->
  <div class="footer">
    <p>© 2026 MV.PROJECT | SCP FOUNDATION | MEDIUM ROLEPLAY</p>
    <p>Документ №SCP-RP-01 «ЗАСЛОН» | Версия 2.0 | Обновлено: сентябрь 2026</p>
    <p style="margin-top: 15px; color: #333;">CLASSIFIED — LEVEL 5 CLEARANCE REQUIRED</p>
  </div>

</body>
</html>
