# proxy-website
A proxy website for accessing games, YouTube, TikTok, GeForce Now, and Google
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Web Portal</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0b1020;
      color: white;
    }
    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 30px 20px;
    }
    .header {
      text-align: center;
      margin-bottom: 30px;
    }
    .search-bar {
      display: flex;
      gap: 10px;
      margin-bottom: 30px;
    }
    .search-bar input {
      flex: 1;
      padding: 15px;
      border-radius: 12px;
      border: 1px solid #2a3f5f;
      background: #111827;
      color: white;
    }
    .search-bar button {
      padding: 15px 20px;
      border: none;
      border-radius: 12px;
      background: #3b82f6;
      color: white;
      cursor: pointer;
    }
    .portal-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 18px;
    }
    .portal-card {
      background: #111827;
      border: 1px solid #26354d;
      border-radius: 18px;
      padding: 24px 18px;
      text-align: center;
      cursor: pointer;
    }
    .icon {
      font-size: 2.3rem;
      margin-bottom: 12px;
    }
    .quick-links {
      margin-top: 30px;
    }
    .quick-links a {
      display: inline-block;
      margin: 8px 10px 0 0;
      color: #93c5fd;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <div class="container">
    <header class="header">
      <h1>Web Portal</h1>
      <p>Quick access to your favorite sites</p>
    </header>

    <div class="search-bar">
      <input id="urlInput" type="text" placeholder="Enter URL or search term..." />
      <button onclick="go()">Go</button>
    </div>

    <div class="portal-grid">
      <div class="portal-card" onclick="openLink('https://www.google.com')">
        <div class="icon">🔍</div>
        <h3>Google</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://www.youtube.com')">
        <div class="icon">📺</div>
        <h3>YouTube</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://www.tiktok.com')">
        <div class="icon">🎵</div>
        <h3>TikTok</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://play.geforcenow.com')">
        <div class="icon">🎮</div>
        <h3>GeForce NOW</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://store.steampowered.com')">
        <div class="icon">🕹️</div>
        <h3>Steam</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://www.epicgames.com')">
        <div class="icon">⚡</div>
        <h3>Epic Games</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://discord.com')">
        <div class="icon">💬</div>
        <h3>Discord</h3>
      </div>
      <div class="portal-card" onclick="openLink('https://www.twitch.tv')">
        <div class="icon">📹</div>
        <h3>Twitch</h3>
      </div>
    </div>

    <div class="quick-links">
      <h2>Quick Links</h2>
      <a href="https://www.reddit.com" target="_blank">Reddit</a>
      <a href="https://www.github.com" target="_blank">GitHub</a>
      <a href="https://www.netflix.com" target="_blank">Netflix</a>
      <a href="https://www.amazon.com" target="_blank">Amazon</a>
    </div>
  </div>

  <script>
    function openLink(url) {
      window.open(url, '_blank');
    }

    function go() {
      const input = document.getElementById('urlInput').value.trim();
      if (!input) return;
      if (input.includes('://')) {
        openLink(input);
      } else if (input.includes('.')) {
        openLink('https://' + input);
      } else {
        openLink('https://www.google.com/search?q=' + encodeURIComponent(input));
      }
    }
  </script>
</body>
</html>
