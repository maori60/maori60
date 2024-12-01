<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Matrix Effect - I am learning</title>
  <style>
    /* Base styling */
    body {
      background-color: black;
      color: #00ff00; /* Green text like in Matrix */
      font-family: 'Courier New', Courier, monospace;
      margin: 0;
      padding: 0;
      height: 100vh;
      overflow: hidden;
    }

    h3 {
      text-align: center;
      font-size: 40px;
      color: #00ff00;
      margin-top: 20px;
    }

    p {
      text-align: center;
      font-size: 20px;
      margin-top: 20px;
    }

    a img {
      width: 40px;
      height: 40px;
      margin: 10px;
      opacity: 0.8;
      animation: fall 5s infinite linear;
    }

    /* Animations */
    @keyframes fall {
      0% { transform: translateY(-100%); opacity: 0.8; }
      100% { transform: translateY(100vh); opacity: 0.2; }
    }

    /* Matrix falling effect */
    .matrix-effect {
      position: absolute;
      top: 0;
      left: 0;
      pointer-events: none;
      z-index: 9999;
      font-family: 'Courier New', Courier, monospace;
    }

    .matrix-effect span {
      position: absolute;
      top: -20px;
      color: #00ff00;
      animation: matrixRain 1s linear infinite;
      opacity: 0.9;
    }

    @keyframes matrixRain {
      0% { top: -20px; }
      100% { top: 100%; }
    }
  </style>
</head>
<body>

  <h3>I am currently learning:</h3>

  <p>
    <a href="https://www.arduino.cc/" target="_blank" rel="noreferrer">
      <img src="https://cdn.worldvectorlogo.com/logos/arduino-1.svg" alt="arduino"/>
    </a>
    <a href="https://www.gnu.org/software/bash/" target="_blank" rel="noreferrer">
      <img src="https://www.vectorlogo.zone/logos/gnu_bash/gnu_bash-icon.svg" alt="bash"/>
    </a>
    <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c"/>
    </a>
    <a href="https://www.w3schools.com/cpp/" target="_blank" rel="noreferrer">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" alt="cplusplus"/>
    </a>
    <a href="https://git-scm.com/" target="_blank" rel="noreferrer">
      <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git"/>
    </a>
    <a href="https://www.python.org" target="_blank" rel="noreferrer">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python"/>
    </a>
    <a href="https://www.mysql.com/" target="_blank" rel="noreferrer">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql"/>
    </a>
    <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb"/>
    </a>
    <a href="https://www.linux.org/" target="_blank" rel="noreferrer">
      <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux"/>
    </a>
  </p>

  <!-- Matrix effect container -->
  <div class="matrix-effect" id="matrix-effect"></div>

  <script>
    // JavaScript to create matrix effect of falling characters
    const matrixEffect = document.getElementById('matrix-effect');
    const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789@#$%^&*()*&^%'.split('');

    setInterval(() => {
      const span = document.createElement('span');
      const char = characters[Math.floor(Math.random() * characters.length)];
      const leftPosition = Math.random() * window.innerWidth;

      span.style.left = `${leftPosition}px`;
      span.innerHTML = char;

      matrixEffect.appendChild(span);

      setTimeout(() => {
        matrixEffect.removeChild(span);
      }, 5000); // Remove character after animation
    }, 100); // Create a new character every 100ms
  </script>

</body>
</html>
