<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mahappen WebView</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      padding: 20px;
    }

    header {
      width: 100%;
      max-width: 900px;
      text-align: center;
      margin-bottom: 20px;
    }

    header h1 {
      font-size: 2rem;
      margin-bottom: 10px;
      color: #00ffff;
    }

    .search-bar {
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba(255,255,255,0.1);
      border-radius: 12px;
      padding: 10px 15px;
      width: 100%;
      max-width: 600px;
      margin: auto;
      backdrop-filter: blur(8px);
    }

    .search-bar input {
      flex: 1;
      border: none;
      outline: none;
      background: transparent;
      color: #fff;
      font-size: 1rem;
      padding: 8px;
    }

    .search-bar button {
      background: #00ffff;
      border: none;
      padding: 8px 15px;
      border-radius: 8px;
      color: #000;
      font-weight: 600;
      cursor: pointer;
      transition: 0.3s;
    }

    .search-bar button:hover {
      background: #00d4d4;
    }

    .files-section {
      margin-top: 30px;
      width: 100%;
      max-width: 900px;
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 15px;
    }

    .file-card {
      background: rgba(255, 255, 255, 0.08);
      padding: 15px;
      border-radius: 12px;
      text-align: center;
      backdrop-filter: blur(6px);
      transition: transform 0.2s ease;
    }

    .file-card:hover {
      transform: translateY(-5px);
    }

    .file-card h3 {
      margin-bottom: 10px;
      color: #00ffff;
      font-size: 1rem;
    }

    .file-card p {
      font-size: 0.85rem;
      color: #ccc;
    }

    footer {
      margin-top: 30px;
      font-size: 0.8rem;
      color: #aaa;
    }
  </style>
</head>
<body>
  <header>
    <h1>🌐 Mahappen WebView</h1>
    <div class="search-bar">
      <input type="text" placeholder="Search files or websites..." id="searchInput" />
      <button onclick="search()">Search</button>
    </div>
  </header>

  <section class="files-section" id="files">
    <div class="file-card">
      <h3>Document 1</h3>
      <p>Project details and notes.</p>
    </div>
    <div class="file-card">
      <h3>Image Gallery</h3>
      <p>Beautiful images stored here.</p>
    </div>
    <div class="file-card">
      <h3>Music Folder</h3>
      <p>Your favorite soundtracks.</p>
    </div>
    <div class="file-card">
      <h3>Downloads</h3>
      <p>All recent files and data.</p>
    </div>
  </section>

  <footer>© 2025 Mahappen | WebView Interface</footer>

  <script>
    function search() {
      const query = document.getElementById('searchInput').value.trim();
      if (query) {
        alert('Searching for: ' + query);
      } else {
        alert('Please enter something to search.');
      }
    }
  </script>
</body>
</html>
