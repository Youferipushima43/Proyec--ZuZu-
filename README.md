<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Feliz Cumpleaños Mi Niña - Carta de Amor</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Great+Vibes&family=Merriweather:wght@400;700&family=Montserrat:wght@400;700&display=swap');
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      background: linear-gradient(135deg, #ffdde1, #ff9a9e);
      font-family: 'Montserrat', sans-serif;
      min-height: 100vh;
      color: #6e2a3a;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px 20px 40px;
      overflow-x: hidden;
    }
    #header-container {
      position: fixed;
      top: 0; left: 0; right: 0;
      min-height: 80px;
      padding: 10px 20px;
      background: linear-gradient(135deg, #bb2a41, #9b2034);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 10;
      box-shadow: 0 3px 10px rgba(0,0,0,0.3);
    }
    #main-title {
      font-family: 'Playfair Display', serif;
      font-size: 3.8rem;
      color: #fff;
      text-align: center;
      text-shadow: 2px 2px 6px #5c1020;
    }
    #content-container {
      margin-top: 100px;
      max-width: 480px;
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    #heart-container {
      position: relative;
      width: 180px;
      height: 180px;
      cursor: pointer;
    }
    #heart {
      width: 180px;
      height: 180px;
      background: radial-gradient(circle at 50% 40%, #ff5268, #b81e37);
      clip-path: polygon(50% 90%, 82% 65%, 92% 40%, 75% 20%, 50% 27%, 25% 20%, 8% 40%, 18% 65%);
      filter: drop-shadow(0 0 6px #f65178);
      transition: transform 0.7s ease, opacity 0.7s ease;
      z-index: 2;
      position: relative;
    }
    #heart.clicked {
      transform: scale(0.4) translateY(-220px);
      opacity: 0;
    }
    #falling-hearts {
      position: absolute;
      top: 0; left: 50%;
      width: 240px;
      height: 320px;
      pointer-events: none;
      overflow: visible;
      z-index: 1;
    }
    .falling-heart {
      position: absolute;
      width: 28px;
      height: 28px;
      background: radial-gradient(circle at 50% 50%, #ff6382, #b91944);
      clip-path: polygon(50% 90%, 82% 65%, 92% 40%, 75% 20%, 50% 27%, 25% 20%, 8% 40%, 18% 65%);
      animation: fall-and-sway ease-in-out 6s 1;
      filter: drop-shadow(0 0 3px #ff4b6a);
      opacity: 0;
    }
    @keyframes fall-and-sway {
      0% { transform: translateY(0) translateX(0) scale(1); opacity: 1; }
      100% { transform: translateY(280px) translateX(var(--sway)) scale(0.5); opacity: 0; }
    }
    #buttons {
      margin-top: 15px;
      display: flex;
      gap: 10px;
      justify-content: center;
      width: 100%;
      max-width: 480px;
      position: sticky;
      top: 90px;
      z-index: 15;
      flex-wrap: wrap;
    }
    button {
      font-family: 'Montserrat', sans-serif;
      font-weight: 700;
      font-size: 1.1rem;
      padding: 12px 24px;
      border-radius: 30px;
      border: none;
      cursor: pointer;
      background: #bb2a41;
      color: white;
      box-shadow: 0 5px 15px rgba(187, 42, 65, 0.6);
      transition: background-color 0.3s ease;
    }
    button:hover:not(:disabled) {
      background: #9b2034;
    }
    button:disabled {
      background: #d7a5ab;
      cursor: not-allowed;
    }
    #letter-container {
      width: 100%;
      max-width: 480px;
      min-height: 420px;
      margin-top: 20px;
      background: #fff8f9;
      border-radius: 20px;
      box-shadow: inset 0 0 15px #f2c4ca, 0 12px 30px rgba(219, 36, 60, 0.35);
      padding: 35px 40px 30px;
      font-family: 'Merriweather', serif;
      font-size: 1.24rem;
      line-height: 1.75;
      text-align: justify;
      opacity: 0;
      transform: scale(0.75) translateY(30px);
      transition: opacity 0.8s ease, transform 0.8s ease;
      max-height: 70vh;
      overflow-y: auto;
    }
    #letter-container.visible {
      opacity: 1;
      transform: scale(1) translateY(0);
    }
    #letter-title {
      font-family: 'Great Vibes', cursive;
      font-size: 3.2rem;
      margin-bottom: 18px;
      color: #bb2a41;
      text-align: center;
    }
    #letter-signoff {
      margin-top: 30px;
      font-family: 'Montserrat', sans-serif;
      font-weight: 700;
      font-size: 1.16rem;
      color: #bb2a41;
      text-align: right;
    }
    /* Estilo para el iframe del reproductor pequeño */
    #audio-archive-player iframe {
      width: 240px !important;
      height: 55px !important;
      max-width: 95vw;
      min-width: 140px;
      border-radius: 14px;
      background: #18181c;
      display: inline-block;
    }
  </style>
</head>
<body>
  <div id="header-container">
    <h1 id="main-title">FELIZ CUMPLEAÑOS, MI NIÑA 🎉💖</h1>
  </div>

  <div id="content-container">
    <div id="heart-container">
      <div id="heart"></div>
      <div id="falling-hearts"></div>
    </div>

    <div id="buttons">
      <button id="open-btn">Abrir</button>
      <button id="reset-btn" disabled>Resetear</button>
      <button id="music-anuel-btn">🎵 Anuel</button>
    </div>

    <div id="letter-container">
      <h2 id="letter-title">Querida Mi Niña,</h2>
      <p>
        Hoy es 12 de octubre, y no es un día cualquiera… Hoy es el cumpleaños de la persona que me hace sentir amado, que le dio un nuevo color a mi vida y que, sin importar la distancia, me hace sentir cerca con solo pensar en ella.<br><br>
        Feliz cumpleaños, mi amor. Este es nuestro primer cumpleaños juntos, y aunque la vida quiso que estemos lejos por ahora, quiero que sepas que estoy con vos en cada pensamiento, en cada suspiro, en cada deseo que le pido al día por vos.<br><br>
        Quizás no pueda abrazarte hoy como quisiera, pero sí puedo hacerte sentir lo mucho que te amo, lo agradecido que estoy de tenerte y lo feliz que me hace tu existencia.<br>
        Sé que no estoy ahí físicamente, pero quise estar presente de algún modo. Por eso, con la ayuda de tu hermana (que se volvió mi cómplice), logré mandarte un regalo. Tal vez sea algo sencillo comparado con lo que siento, pero va con todo mi amor.<br><br>
        Cada detalle está pensado para sacarte una sonrisa y recordarte que, aunque estemos a kilómetros, estoy con vos más de lo que imaginás. Gracias por aparecer en mi vida, por todo lo que sos y por compartir tu corazón conmigo. Te merecés un mundo lleno de cosas lindas, y yo quiero ser parte de todo eso que te haga feliz.<br><br>
        Hoy celebro tu vida, y desde donde estoy, te mando mil besos, mil abrazos y el deseo más sincero: que este nuevo año te traiga paz, amor, logros y sonrisas infinitas… y que muy pronto podamos celebrar de la mano, sin distancias.<br><br>
        Te amo, feliz cumpleaños mi reina. Siempre con vos, aunque sea desde lejos.<br><br>
        ¡Feliz cumpleaños!
      </p>
      <div id="letter-signoff">ATT: Maycol.I</div>
    </div>

    <!-- Audio archive.org player, solo audio, pequeño, oculto al inicio -->
    <div id="audio-archive-player" style="display:none; text-align:center; margin-top: 20px;">
      <iframe src="https://archive.org/embed/anuel-aa.-yailin-la-mas-viral-si-tu-me-busca"
        width="240" height="55"
        frameborder="0"
        webkitallowfullscreen="true"
        mozallowfullscreen="true"
        allowfullscreen>
      </iframe>
    </div>
  </div>

  <audio id="background-music" loop>
    <source src="https://cdn.pixabay.com/download/audio/2021/08/04/audio_239642b9f9.mp3?filename=romantic-background-11830.mp3" type="audio/mpeg" />
  </audio>

  <script>
    const heart = document.getElementById('heart');
    const fallingHeartsContainer = document.getElementById('falling-hearts');
    const letter = document.getElementById('letter-container');
    const backgroundMusic = document.getElementById('background-music');
    const headerContainer = document.getElementById('header-container');
    const openBtn = document.getElementById('open-btn');
    const resetBtn = document.getElementById('reset-btn');
    const musicBtn = document.getElementById('music-anuel-btn');

    let animationDone = false;

    function createFallingHearts() {
      const heartsCount = 25;
      const swayValues = ['-50px','-30px','0','30px','50px'];
      for (let i = 0; i < heartsCount; i++) {
        const fh = document.createElement('div');
        fh.classList.add('falling-heart');
        fh.style.left = `calc(50% + ${(Math.random() - 0.5) * 180}px)`;
        fh.style.top = `${-30 * i}px`;
        fh.style.setProperty('--sway', swayValues[i % swayValues.length]);
        fh.style.animationDuration = `${4 + Math.random() * 3}s`;
        fh.style.animationDelay = `${i * 0.2}s`;
        fallingHeartsContainer.appendChild(fh);
        fh.addEventListener('animationend', () => fh.remove());
      }
    }

    function openExperience() {
      if (animationDone) return;
      animationDone = true;
      heart.classList.add('clicked');
      createFallingHearts();
      headerContainer.classList.add('collapsed');
      setTimeout(() => {
        letter.classList.add('visible');
        letter.focus();
      }, 700);
      backgroundMusic.volume = 0.3;
      backgroundMusic.play();
      openBtn.disabled = true;
      resetBtn.disabled = false;
    }

    function resetExperience() {
      if (!animationDone) return;
      animationDone = false;
      heart.classList.remove('clicked');
      letter.classList.remove('visible');
      backgroundMusic.pause();
      backgroundMusic.currentTime = 0;
      document.getElementById('audio-archive-player').style.display = 'none';
      while (fallingHeartsContainer.firstChild) {
        fallingHeartsContainer.removeChild(fallingHeartsContainer.firstChild);
      }
      headerContainer.classList.remove('collapsed');
      openBtn.disabled = false;
      resetBtn.disabled = true;
    }

    openBtn.addEventListener('click', openExperience);
    resetBtn.addEventListener('click', resetExperience);
    document.getElementById('heart-container').addEventListener('click', openExperience);
    musicBtn.addEventListener('click', () => {
      const player = document.getElementById('audio-archive-player');
      player.style.display = 'block';
      // (El usuario debe dar play manualmente)
    });
  </script>
</body>
</html>
