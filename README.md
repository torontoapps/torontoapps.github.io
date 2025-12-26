<html>
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Spelling Bee Practice – Pronunciation Table</title>
  <style>
    :root { color-scheme: dark; }
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
