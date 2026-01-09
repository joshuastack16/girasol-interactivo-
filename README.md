<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Girasol para Ti 🌻</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: linear-gradient(#87ceeb, #fff);
      font-family: 'Arial', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    .girasol {
      position: relative;
      width: 200px;
      height: 200px;
      cursor: pointer;
      transition: transform 1s;
    }

    .centro {
      width: 80px;
      height: 80px;
      background: #5a381e;
      border-radius: 50%;
      position: absolute;
      top: 60px;
      left: 60px;
      z-index: 2;
    }

    .petalo {
      width: 30px;
      height: 90px;
      background: #ffd700;
      border-radius: 50%;
      position: absolute;
      top: 10px;
      left: 85px;
      transform-origin: bottom center;
    }

    .tallo {
      width: 15px;
      height: 180px;
      background: green;
      margin-top: -5px;
      border-radius: 10px;
    }

    .mensaje {
      margin-top: 20px;
      font-size: 20px;
      color: #333;
      padding: 10px;
      max-width: 90%;
      transition: opacity 0.5s;
    }

    .firma {
      margin-top: 10px;
      font-size: 16px;
      color: #555;
      font-style: italic;
    }
  </style>
</head>

<body>

  <div class="girasol" id="girasol">
    <div class="centro"></div>

    <!-- Pétalos -->
    <script>
      for (let i = 0; i < 12; i++) {
        document.write(
          `<div class="petalo" style="transform: rotate(${i * 30}deg);"></div>`
        );
      }
    </script>
  </div>

  <div class="tallo"></div>

  <div class="mensaje" id="mensaje">
    🌻 Toca el girasol
  </div>

  <div class="firma">
    Con cariño de mi para ti 
    Karol 💛
  </div>

  <script>
    const girasol = document.getElementById("girasol");
    const mensaje = document.getElementById("mensaje");

    const mensajesRomanticos = [
      "Eres la razón por la que mi corazón sonríe 💛",
      "Así como el girasol sigue al sol, yo te sigo a ti 🌻",
      "Tu sonrisa ilumina mis días ☀️",
      "Cada pétalo guarda un pensamiento para ti 💫",
      "Si el amor tuviera forma, sería como este girasol 💕",
      "Eres mi lugar favorito en el mundo 🌎",
      "Mi corazón florece cada vez que pienso en ti 🌼"
    ];

    let indice = 0;
    let girando = false;

    girasol.addEventListener("click", () => {
      girando = !girando;

      girasol.style.transform = girando
        ? "rotate(360deg)"
        : "rotate(0deg)";

      mensaje.style.opacity = 0;

      setTimeout(() => {
        mensaje.innerText = mensajesRomanticos[indice];
        mensaje.style.opacity = 1;
        indice = (indice + 1) % mensajesRomanticos.length;
      }, 300);
    });
  </script>

</body>
</html>
