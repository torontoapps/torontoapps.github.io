
<html>
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
            <td>
              <div class="word">ruminate</div>
            </td>
            <td>
              <span class="pos">verb</span>
            </td>
            <td>
              To think carefully for a long time about something.
            </td>
            <td>
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/ruminate" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>

          <tr>
            <td>
              <div class="word">collaborate</div>
            </td>
            <td>
              <span class="pos">verb</span>
            </td>
            <td>
              To work with someone else for a special purpose (to create or achieve something together).
            </td>
            <td>
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/collaborate" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>

          <tr>
            <td>
              <div class="word">peninsula</div>
            </td>
            <td>
              <span class="pos">noun</span>
            </td>
            <td>
              A piece of land that sticks out from a larger area of land and is surrounded by water on most sides.
            </td>
            <td>
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/peninsula" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>

          <tr>
            <td>
              <div class="word">prairies</div>
            </td>
            <td>
              <span class="pos">noun (plural)</span>
            </td>
            <td>
              Wide areas of flat land without trees (especially in Canada and the northern U.S.).
            </td>
            <td>
              <a class="audio-link" href="https://dictionary.cambridge.org/pronunciation/english/prairie" target="_blank" rel="noopener noreferrer">
                🔊 Listen
              </a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="footer">
      Tip: Students can open the audio link in a new tab, press play, then practice spelling the word out loud.
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
</html> -->












<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Spelling Bee Practice – Pronunciation Table</title>
  <style>
    :root { color-scheme: light; }
    body { font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; margin: 24px; }
    h1 { margin: 0 0 6px; font-size: 22px; }
    p { margin: 0 0 16px; color: #444; }
    table { width: 100%; border-collapse: collapse; border: 1px solid #ddd; border-radius: 10px; overflow: hidden; }
    thead th { background: #f6f6f6; text-align: left; font-weight: 650; padding: 12px; border-bottom: 1px solid #ddd; }
    tbody td { padding: 12px; border-bottom: 1px solid #eee; vertical-align: top; }
    tbody tr:last-child td { border-bottom: none; }
    .word { font-weight: 750; font-size: 16px; }
    .muted { color: #666; font-size: 13px; }
    .btn {
      display: inline-flex; align-items: center; gap: 8px;
      padding: 8px 10px; border: 1px solid #ccc; border-radius: 10px;
      background: white; cursor: pointer; user-select: none;
      font-weight: 600;
    }
    .btn:hover { background: #fafafa; }
    .btn:active { transform: translateY(1px); }
    .btn[aria-pressed="true"] { border-color: #888; }
    .btn:focus { outline: 3px solid rgba(0,0,0,0.15); outline-offset: 2px; }
    .audio-hidden { width: 1px; height: 1px; position: absolute; left: -9999px; }
    .col-word { width: 18%; }
    .col-meaning { width: 42%; }
    .col-pos { width: 16%; }
    .col-audio { width: 24%; }
    footer { margin-top: 14px; font-size: 12px; color: #666; }
    code { background: #f6f6f6; padding: 2px 6px; border-radius: 6px; }
  </style>
</head>
<body>
  <h1>Spelling Bee Practice</h1>
  <p>Click <b>Play</b> to hear each word.</p>

  <table>
    <thead>
      <tr>
        <th class="col-word">Word</th>
        <th class="col-meaning">Meaning</th>
        <th class="col-pos">Part of speech</th>
        <th class="col-audio">Pronunciation (audio)</th>
      </tr>
    </thead>
    <tbody>

      <!-- ruminate -->
      <tr>
        <td class="word">ruminate</td>
        <td>To think deeply about something; to “chew over” an idea in your mind.</td>
        <td>verb</td>
        <td>
          <button class="btn" type="button" data-audio-id="audio-ruminate" aria-pressed="false">
            ▶ Play
          </button>
          <span class="muted">US pronunciation</span>

          <audio class="audio-hidden" preload="none" id="audio-ruminate" controlsList="nodownload">
            <!-- MP3 first for widest compatibility -->
            <source type="audio/mpeg" src="https://upload.wikimedia.org/wikipedia/commons/transcoded/d/db/En-us-ruminate.ogg/En-us-ruminate.ogg.mp3">
            <source type="audio/ogg"  src="https://upload.wikimedia.org/wikipedia/commons/d/db/En-us-ruminate.ogg">
            Your browser doesn't support HTML5 audio.
          </audio>
        </td>
      </tr>

      <!-- collaborate -->
      <tr>
        <td class="word">collaborate</td>
        <td>To work together with one or more people to create or achieve something.</td>
        <td>verb</td>
        <td>
          <button class="btn" type="button" data-audio-id="audio-collaborate" aria-pressed="false">
            ▶ Play
          </button>
          <span class="muted">US pronunciation</span>

          <audio class="audio-hidden" preload="none" id="audio-collaborate" controlsList="nodownload">
            <source type="audio/mpeg" src="https://upload.wikimedia.org/wikipedia/commons/transcoded/7/70/En-us-collaborate.ogg/En-us-collaborate.ogg.mp3">
            <source type="audio/ogg"  src="https://upload.wikimedia.org/wikipedia/commons/7/70/En-us-collaborate.ogg">
            Your browser doesn't support HTML5 audio.
          </audio>
        </td>
      </tr>

      <!-- peninsula -->
      <tr>
        <td class="word">peninsula</td>
        <td>A piece of land that sticks out into water, surrounded by water on three sides.</td>
        <td>noun</td>
        <td>
          <button class="btn" type="button" data-audio-id="audio-peninsula" aria-pressed="false">
            ▶ Play
          </button>
          <span class="muted">US pronunciation</span>

          <audio class="audio-hidden" preload="none" id="audio-peninsula" controlsList="nodownload">
            <source type="audio/mpeg" src="https://upload.wikimedia.org/wikipedia/commons/transcoded/1/12/En-us-peninsula.ogg/En-us-peninsula.ogg.mp3">
            <source type="audio/ogg"  src="https://upload.wikimedia.org/wikipedia/commons/1/12/En-us-peninsula.ogg">
            Your browser doesn't support HTML5 audio.
          </audio>
        </td>
      </tr>

      <!-- prairies (uses prairie audio) -->
      <tr>
        <td class="word">prairies</td>
        <td>Large, open areas of flat grassland (plural of <i>prairie</i>).</td>
        <td>noun (plural)</td>
        <td>
          <button class="btn" type="button" data-audio-id="audio-prairie" aria-pressed="false">
            ▶ Play
          </button>
          <span class="muted">Uses “prairie” pronunciation</span>

          <audio class="audio-hidden" preload="none" id="audio-prairie" controlsList="nodownload">
            <source type="audio/mpeg" src="https://upload.wikimedia.org/wikipedia/commons/transcoded/8/85/En-us-prairie.ogg/En-us-prairie.ogg.mp3">
            <source type="audio/ogg"  src="https://upload.wikimedia.org/wikipedia/commons/8/85/En-us-prairie.ogg">
            Your browser doesn't support HTML5 audio.
          </audio>
        </td>
      </tr>

    </tbody>
  </table>

  <footer>
    Audio sources: Wikimedia Commons pronunciation recordings (free licenses). Tip: for best results, serve this file over HTTP (e.g. <code>python -m http.server</code>) instead of opening via <code>file://</code>.
  </footer>

  <script>
    // Simple player behavior:
    // - Clicking Play pauses any other playing audio
    // - Button text toggles Play / Pause
    (function () {
      const buttons = Array.from(document.querySelectorAll('button[data-audio-id]'));

      function stopAllExcept(exceptAudio) {
        document.querySelectorAll('audio').forEach(a => {
          if (a !== exceptAudio && !a.paused) {
            a.pause();
            a.currentTime = 0;
          }
        });
        buttons.forEach(b => {
          const id = b.getAttribute('data-audio-id');
          const a = document.getElementById(id);
          if (a !== exceptAudio) {
            b.setAttribute('aria-pressed', 'false');
            b.textContent = '▶ Play';
          }
        });
      }

      buttons.forEach(btn => {
        const audioId = btn.getAttribute('data-audio-id');
        const audioEl = document.getElementById(audioId);

        btn.addEventListener('click', async () => {
          if (!audioEl) return;

          // Ensure others stop before playing this one
          stopAllExcept(audioEl);

          if (audioEl.paused) {
            // Load on-demand (like Cambridge does) so page doesn't fetch audio until needed
            audioEl.load();

            try {
              await audioEl.play();
              btn.setAttribute('aria-pressed', 'true');
              btn.textContent = '⏸ Pause';
            } catch (e) {
              // Autoplay restrictions or other playback issues
              btn.setAttribute('aria-pressed', 'false');
              btn.textContent = '▶ Play';
              console.warn('Audio play blocked or failed:', e);
            }
          } else {
            audioEl.pause();
            audioEl.currentTime = 0;
            btn.setAttribute('aria-pressed', 'false');
            btn.textContent = '▶ Play';
          }
        });

        audioEl.addEventListener('ended', () => {
          btn.setAttribute('aria-pressed', 'false');
          btn.textContent = '▶ Play';
        });
      });
    })();
  </script>
</body>
</html>
