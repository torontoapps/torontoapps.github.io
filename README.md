<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Spelling Bee Practice Words</title>
  <style>
    :root {
      --bg: #0b1020;
      --card: #121a33;
      --text: #e9ecf5;
      --muted: #b7bfd6;
      --border: rgba(255,255,255,.14);
      --link: #9fd3ff;
      --linkHover: #cbe8ff;
      --accent: #7aa7ff;
    }

    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      background: radial-gradient(1200px 800px at 20% 0%, rgba(122,167,255,.18), transparent 60%),
                  radial-gradient(900px 700px at 90% 20%, rgba(159,211,255,.12), transparent 55%),
                  var(--bg);
      color: var(--text);
      padding: 28px 16px;
    }

    .wrap { max-width: 980px; margin: 0 auto; }
    .header {
      display: flex;
      gap: 16px;
      align-items: flex-end;
      justify-content: space-between;
      flex-wrap: wrap;
      margin-bottom: 16px;
    }

    h1 { margin: 0; font-size: 22px; letter-spacing: .2px; }
    .sub { margin: 6px 0 0; color: var(--muted); font-size: 13px; line-height: 1.4; }

    .toolbar {
      display: flex;
      gap: 10px;
      align-items: center;
      flex-wrap: wrap;
      margin-top: 6px;
    }

    .search {
      width: min(420px, 100%);
      background: rgba(255,255,255,.06);
      border: 1px solid var(--border);
      color: var(--text);
      border-radius: 12px;
      padding: 10px 12px;
      outline: none;
    }
    .search::placeholder { color: rgba(233,236,245,.55); }

    .pill {
      font-size: 12px;
      color: var(--muted);
      border: 1px solid var(--border);
      border-radius: 999px;
      padding: 6px 10px;
      background: rgba(255,255,255,.04);
    }

    .card {
      background: rgba(18,26,51,.82);
      border: 1px solid var(--border);
      border-radius: 16px;
      overflow: hidden;
      box-shadow: 0 20px 60px rgba(0,0,0,.25);
    }

    table { width: 100%; border-collapse: collapse; }
    thead th {
      text-align: left;
      font-size: 12px;
      color: var(--muted);
      font-weight: 600;
      padding: 12px 14px;
      background: rgba(255,255,255,.04);
      border-bottom: 1px solid var(--border);
      position: sticky;
      top: 0;
      backdrop-filter: blur(6px);
    }
    tbody td {
      padding: 14px;
      border-bottom: 1px solid rgba(255,255,255,.08);
      vertical-align: top;
      line-height: 1.35;
      font-size: 14px;
    }
    tbody tr:hover { background: rgba(255,255,255,.03); }
    tbody tr:last-child td { border-bottom: 0; }

    .word {
      font-weight: 750;
      letter-spacing: .2px;
      font-size: 15px;
    }
    .pos {
      display: inline-block;
      margin-top: 6px;
      font-size: 12px;
      color: var(--muted);
      border: 1px solid rgba(255,255,255,.14);
      padding: 3px 8px;
      border-radius: 999px;
      background: rgba(255,255,255,.04);
    }

    a { color: var(--link); text-decoration: none; }
    a:hover { color: var(--linkHover); text-decoration: underline; }

    .audio-link {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 10px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.04);
      white-space: nowrap;
    }
    .audio-link:focus { outline: 2px solid rgba(122,167,255,.6); outline-offset: 2px; }

    .footer {
      margin-top: 14px;
      color: var(--muted);
      font-size: 12px;
      line-height: 1.4;
    }

    @media (max-width: 720px) {
      thead { display: none; }
      table, tbody, tr, td { display: block; width: 100%; }
      tbody td { border-bottom: 0; padding: 10px 14px; }
      tbody tr { border-bottom: 1px solid rgba(255,255,255,.10); padding: 6px 0; }
      tbody tr:last-child { border-bottom: 0; }
      .label {
        display: block;
        font-size: 11px;
        color: var(--muted);
        margin-bottom: 4px;
      }
    }
  </style>
</head>

<body>
  <div class="wrap">
    <div class="header">
      <div>
        <h1>Spelling Bee Practice Words</h1>
        <div class="sub">
          Read the meaning, identify the part of speech, and click “Listen” to hear the pronunciation.
        </div>
      </div>

      <div class="toolbar">
        <input id="search" class="search" type="search" placeholder="Search words… (e.g., pen)" aria-label="Search words" />
        <span id="count" class="pill">4 words</span>
      </div>
    </div>

    <div class="card">
      <table aria-label="Spelling bee word list">
        <thead>
          <tr>
            <th style="width: 20%;">Word</th>
            <th style="width: 16%;">Part of speech</th>
            <th style="width: 44%;">Meaning</th>
            <th style="width: 20%;">Pronunciation</th>
          </tr>
        </thead>

        <tbody id="rows">
          <tr>
            <td><div class="word">ruminate</div></td>
            <td><span class="pos">verb</span></td>
            <td>To think carefully for a long time about something.</td>
            <td>
              <!-- Audio pronunciation page (includes play button) -->
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/ruminate" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>

          <tr>
            <td><div class="word">collaborate</div></td>
            <td><span class="pos">verb</span></td>
            <td>To work with someone else for a special purpose (to create or achieve something together).</td>
            <td>
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/collaborate" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>

          <tr>
            <td><div class="word">peninsula</div></td>
            <td><span class="pos">noun</span></td>
            <td>A piece of land that sticks out from a larger area of land and is surrounded by water on most sides.</td>
            <td>
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/peninsula" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>

          <tr>
            <td><div class="word">prairies</div></td>
            <td><span class="pos">noun (plural)</span></td>
            <td>Wide areas of flat land without trees (especially in Canada and the northern U.S.).</td>
            <td>
              <!-- Use singular base word for pronunciation -->
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/prairie" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="footer">
      Tip: Open the “Listen” link, play the audio, then practice spelling the word out loud.
    </div>
  </div>

  <script>
    const search = document.getElementById('search');
    const rows = Array.from(document.querySelectorAll('#rows tr'));
    const count = document.getElementById('count');

    function updateCount(visible) {
      count.textContent = `${visible} word${visible === 1 ? '' : 's'}`;
    }

    function filterRows() {
      const q = (search.value || '').trim().toLowerCase();
      let visible = 0;

      for (const row of rows) {
        const text = row.innerText.toLowerCase();
        const show = text.includes(q);
        row.style.display = show ? '' : 'none';
        if (show) visible++;
      }
      updateCount(visible);
    }

    search.addEventListener('input', filterRows);
    updateCount(rows.length);
  </script>
</body>
</html>
