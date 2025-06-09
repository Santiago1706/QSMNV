
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>¿Quieres ser mi novia?</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-image: url('https://i.pinimg.com/originals/ce/4a/f2/ce4af2dbbd1cb930d3cccbcb0e7c3b67.jpg'); /* fondo con rosas azules */
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
    }

    h1 {
      font-size: 3em;
      background: linear-gradient(90deg, #00f0ff, #ff00f0);
      -webkit-background-clip: text;
      color: transparent;
    }

    .botones {
      margin-top: 30px;
    }

    button {
      padding: 15px 30px;
      font-size: 1.5em;
      margin: 0 15px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    #si {
      background-color: #00ff99;
      color: #000;
    }

    #no {
      background-color: #ff0055;
      color: #fff;
      position: absolute;
    }
  </style>
</head>
<body>
  <h1>¿Quieres ser mi novia?</h1>
  <div class="botones">
    <button id="si">Sí</button>
    <button id="no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById('no');
    const siBtn = document.getElementById('si');

    noBtn.addEventListener('mouseover', () => {
      const x = Math.floor(Math.random() * (window.innerWidth - 100));
      const y = Math.floor(Math.random() * (window.innerHeight - 50));
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    });

    siBtn.addEventListener('click', () => {
      alert("Te amo, sabía que ibas a decir que sí 💖");
    });
  </script>
</body>
</html>
