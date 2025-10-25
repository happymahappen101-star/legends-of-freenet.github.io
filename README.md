<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Hacker Login Portal</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Courier New', monospace;
    }

    body {
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: radial-gradient(circle at center, #000 60%, #020202 100%);
      color: #00ff99;
      overflow: hidden;
    }

    body::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: repeating-linear-gradient(
        0deg,
        rgba(0, 255, 0, 0.05) 0px,
        rgba(0, 255, 0, 0.05) 1px,
        transparent 2px,
        transparent 4px
      );
      animation: matrixRain 20s linear infinite;
      z-index: 0;
    }

    @keyframes matrixRain {
      from { background-position: 0 0; }
      to { background-position: 0 1000px; }
    }

    .login-box {
      position: relative;
      z-index: 1;
      background: rgba(0, 0, 0, 0.85);
      border: 2px solid #00ff99;
      border-radius: 10px;
      padding: 40px;
      width: 350px;
      box-shadow: 0 0 20px #00ff99;
      text-align: center;
    }

    .login-box h2 {
      margin-bottom: 25px;
      font-size: 1.8em;
      color: #00ff99;
      text-shadow: 0 0 10px #00ff99;
      animation: flicker 3s infinite, glowPulse 1.5s infinite alternate;
    }

    @keyframes glowPulse {
      from { text-shadow: 0 0 5px #00ff99; }
      to { text-shadow: 0 0 20px #00ff99; }
    }

    .input-box {
      position: relative;
      margin: 25px 0;
    }

    .input-box input {
      width: 100%;
      padding: 12px;
      border: 1px solid #00ff99;
      border-radius: 5px;
      background: black;
      color: #00ff99;
      font-size: 1em;
      outline: none;
      box-shadow: 0 0 10px #00ff99 inset;
      transition: 0.3s;
    }

    .input-box input::placeholder {
      color: #00ff99;
      opacity: 0.5;
    }

    .input-box input:focus {
      box-shadow: 0 0 20px #00ff99 inset, 0 0 10px #00ff99;
    }

    .btn {
      width: 100%;
      padding: 12px;
      border: 2px solid #00ff99;
      border-radius: 5px;
      background: transparent;
      color: #00ff99;
      font-size: 1.1em;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
      text-transform: uppercase;
    }

    .btn:hover {
      background: #00ff99;
      color: black;
      box-shadow: 0 0 15px #00ff99;
    }

    .signup-link {
      margin-top: 20px;
      font-size: 0.9em;
    }

    .signup-link a {
      color: #00ff99;
      text-decoration: none;
      font-weight: bold;
    }

    .signup-link a:hover {
      text-shadow: 0 0 5px #00ff99;
    }

    @keyframes flicker {
      0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% { opacity: 1; }
      20%, 24%, 55% { opacity: 0.3; }
    }

    /* Music control button */
    .music-btn {
      position: fixed;
      left: 20px;
      bottom: 20px;
      z-index: 3;
      width: 56px;
      height: 56px;
      border-radius: 50%;
      border: 2px solid #00ff99;
      background: rgba(0,0,0,0.75);
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      box-shadow: 0 0 12px #00ff99;
      transition: transform 0.12s ease;
    }
    .music-btn:active { transform: scale(0.96); }
    .music-btn svg { fill: #00ff99; width: 26px; height: 26px; }
    .music-label {
      position: fixed;
      left: 86px;
      bottom: 32px;
      z-index: 3;
      color: #00ff99;
      font-size: 0.9em;
      text-shadow: 0 0 6px #00ff99;
      font-weight: bold;
    }
    audio { display: none; }
  </style>
</head>
<body>

  <div class="login-box" id="loginBox">
    <h2>ACCESS TERMINAL</h2>
    <form id="loginForm">
      <div class="input-box">
        <input type="text" placeholder="Username" id="username" required />
      </div>
      <div class="input-box">
        <input type="password" placeholder="Password" id="password" required />
      </div>
      <button type="submit" class="btn">LOGIN</button>
      <div class="signup-link">
        No access? <a href="#">Request Clearance</a>
      </div>
    </form>
  </div>

  <audio id="bg-music" src="music/cyber-ambient.mp3" loop preload="auto"></audio>
  <div class="music-btn" id="musicBtn" title="Play / Pause music" aria-label="Play music">
    <svg id="musicIcon" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
  </div>
  <div class="music-label" id="musicLabel">Cyber Ambient</div>

  <script>
    // Redirect to index.html when login is submitted
    document.getElementById("loginForm").addEventListener("submit", function(event) {
      event.preventDefault(); // Stop actual form submit
      window.location.href = "index.html"; // Go to your main page
    });

    // Music player controls
    const audio = document.getElementById('bg-music');
    const btn = document.getElementById('musicBtn');
    const icon = document.getElementById('musicIcon');
    const label = document.getElementById('musicLabel');

    function updateIcon(isPlaying) {
      icon.innerHTML = isPlaying
        ? '<path d="M6 19h4V5H6v14zM14 5v14h4V5h-4z"/>'
        : '<path d="M8 5v14l11-7z"/>';
    }

    btn.addEventListener('click', function() {
      if (audio.paused) {
        audio.play();
        updateIcon(true);
      } else {
        audio.pause();
        updateIcon(false);
      }
    });

    // Try autoplay after first user click
    document.addEventListener('click', () => audio.play().catch(() => {}), { once: true });
  </script>

</body>
</html>
