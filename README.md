<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>¿Quieres ser mi novia?</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(45deg, #ffc0cb, #ffe4e1);
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: #ffffff;
      font-family: 'Comic Sans MS', cursive;
      text-shadow: 2px 2px 4px #000000;
      position: relative;
      overflow: hidden;
    }

    h1 {
      font-size: 3em;
      background: linear-gradient(90deg, #ff69b4, #ff1493);
      -webkit-background-clip: text;
      color: transparent;
      margin: 20px;
      text-align: center;
    }

    .botones {
      margin-top: 30px;
      position: relative;
      width: 100%;
      height: 150px;
    }

    button {
      padding: 15px 30px;
      font-size: 1.5em;
      margin: 0 15px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
      position: absolute;
    }

    #si {
      background-color: #00ff99;
      color: #000;
      position: relative;
      z-index: 2;
    }

    #no {
      background-color: #ff0055;
      color: #fff;
      z-index: 2;
    }

    .decoraciones img {
      position: absolute;
      width: 100px;
      pointer-events: none;
    }

    .rosa1 { top: 20px; left: 20px; }
    .rosa2 { top: 20px; right: 20px; }
    .regalo { bottom: 20px; left: 30px; }
    .anillo { bottom: 20px; right: 30px; }
  </style>
</head>
<body>
  <h1 id="pregunta">💖 ¿Quieres ser mi novia? 💕</h1>
  <div class="botones" id="contenedorBotones">
    <button id="si">💍 ¡Sí, quiero! 💘</button>
    <button id="no">❌ No</button>
  </div>

  <!-- Stickers decorativos -->
  <div class="decoraciones">
    <img src="https://png.pngtree.com/png-clipart/20230527/original/pngtree-pink-roses-bouquet-png-image_9171809.png" class="rosa1">
    <img src="https://img.lovepik.com/free-png/20211116/lovepik-a-bunch-of-roses-png-image_400949501_wh1200.png" class="rosa2">
    <img src="https://png.pngtree.com/png-clipart/20231110/original/pngtree-white-gift-box-with-red-bow-png-image_13524750.png" class="regalo">
    <img src="https://images.vexels.com/media/users/3/203481/isolated/preview/c21afaa9f1d32e2c8fd26b352837dda6-ilustracion-de-anillo-de-bodas.png" class="anillo">
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const siBtn = document.getElementById('si');
    const pregunta = document.getElementById('pregunta');
    const botonesContainer = document.getElementById('contenedorBotones');

    let enPantallaConfirmacion = false;

    function moverBoton() {
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;
      const maxX = window.innerWidth - btnWidth;
      const maxY = window.innerHeight - btnHeight;

      const x = Math.max(0, Math.floor(Math.random() * maxX));
      const y = Math.max(0, Math.floor(Math.random() * maxY));

      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    }

    noBtn.addEventListener('mouseover', () => {
      if (!enPantallaConfirmacion) {
        moverBoton();
      }
    });

    noBtn.addEventListener('click', () => {
      if (!enPantallaConfirmacion) {
        // Cambia la pregunta a ¿Estás segura?
        pregunta.textContent = "😥 ¿Estás segura?";
        siBtn.textContent = "🔁 Sí, me arrepiento 💞";
        noBtn.textContent = "❌ No, insisto";
        enPantallaConfirmacion = true;
      } else {
        // Vuelve a la pregunta inicial
        pregunta.textContent = "💖 ¿Quieres ser mi novia? 💕";
        siBtn.textContent = "💍 ¡Sí, quiero! 💘";
        noBtn.textContent = "❌ No";
        enPantallaConfirmacion = false;
      }
    });

    siBtn.addEventListener('click', () => {
      if (!enPantallaConfirmacion) {
        alert("💖 Te amo, sabía que dirías que sí 😍💍");
      } else {
        // Vuelve a la pregunta original
        pregunta.textContent = "💖 ¿Quieres ser mi novia? 💕";
        siBtn.textContent = "💍 ¡Sí, quiero! 💘";
        noBtn.textContent = "❌ No";
        enPantallaConfirmacion = false;
      }
    });
  </script>
</body>
</html>
