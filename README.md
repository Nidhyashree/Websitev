<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #81af9e, #b2c09d);
      overflow: hidden;
      font-family: "Gill Sans", cursive;
    }

    .container {
      text-align: center;
      background: #88b28a; /* Vintage paper color */
      padding: 40px;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0);
      z-index: 1;
      position: relative;
      border:  solid #88b28a; 
      max-width: 500px;
      width: 100%;
    }

    .container::before {
      content: '';
      position: absolute;
      top: -10px;
      right: -10px;
      width: 50px;
      height: 50px;
      background: #af4c4c; 
      clip-path: polygon(100% 0, 0 0, 100% 100%);
    }

    .container::after {
      content: '💌'; /* Stamp emoji */
      position: absolute;
      top: -20px;
      right: -20px;
      font-size: 40px;
      transform: rotate(15deg);
    }

    h1 {
      color: #d32f2f;
      font-family: "Gill Sans", cursive;
      margin-bottom: 20px;
    }

    button {
      padding: 10px 20px;
      margin: 10px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 20px;
      transition: background-color 0.3s ease;
    }

    #yesButton {
      background-color: #4caf50;
      color: white;
    }

    #noButton {
      background-color: #f44336;
      color: white;
    }

    #yesButton2 {
      background-color: #4caf50;
      color: white;
    }

    #moodituButton {
      background-color: #f44336;
      color: white;
    }

    #finalYesButton {
      background-color: #4caf50;
      color: white;
    }

    button:hover {
      opacity: 0.8;
    }

    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: 0;
    }

    .hearts span {
      position: absolute;
      display: block;
      width: 20px;
      height: 20px;
      background: #ff4757;
      clip-path: path("M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z");
      animation: animate 10s linear infinite;
      bottom: -150px;
    }

    .hearts span:nth-child(1) {
      left: 25%;
      animation-delay: 0s;
    }

    .hearts span:nth-child(2) {
      left: 10%;
      animation-delay: 2s;
    }

    .hearts span:nth-child(3) {
      left: 70%;
      animation-delay: 2s;
    }

    .hearts span:nth-child(4) {
      left: 40%;
      animation-delay: 2s;
    }

    .hearts span:nth-child(5) {
      left: 85%;
      animation-delay: 4s;
    }

    @keyframes animate {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-1000px) rotate(720deg);
        opacity: 0;
      }
    }

    .sparkle {
      position: absolute;
      font-size: 24px;
      animation: sparkle 1s linear infinite;
    }

    @keyframes sparkle {
      0% {
        transform: scale(1);
        opacity: 1;
      }
      50% {
        transform: scale(1.2);
        opacity: 0.5;
      }
      100% {
        transform: scale(1);
        opacity: 1;
      }
    }

    .kissy {
      position: absolute;
      font-size: 50px;
      color: red;
      animation: moveKissy 5s ease-in-out infinite;
    }

    @keyframes moveKissy {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-1000px) rotate(720deg);
        opacity: 0;
      }
    }

    .big-message {
      font-size: 30px;
      font-weight: bold;
      color: #B8001F;
    }
  </style>
</head>
<body>
  <div class="hearts">
    <span></span>
    <span></span>
    <span></span>
    <span></span>
    <span></span>
  </div>

  <div class="container">
    <h1 id="valentineQuestion">Will You Be My Valentine?</h1>
    <button id="yesButton">Yessss</button>
    <button id="noButton">Noooo</button>
    <p id="response" style="color: #d32f2f;"></p>
  </div>

  <script>
    const yesButton = document.getElementById('yesButton');
    const noButton = document.getElementById('noButton');
    const response = document.getElementById('response');
    const valentineQuestion = document.getElementById('valentineQuestion');

    yesButton.addEventListener('click', () => {
      response.textContent = "I love you baby! ❤️";
      addSparkleEffect();
    });

    noButton.addEventListener('click', () => {
      yesButton.style.display = "none";
      noButton.style.display = "none";
      response.innerHTML = `
        <button id="yesButton2">Yes</button>
        <button id="moodituButton">Mooditu po di</button>
      `;

      const yesButton2 = document.getElementById('yesButton2');
      const moodituButton = document.getElementById('moodituButton');

      yesButton2.addEventListener('click', () => {
        response.textContent = "I love you baby! ❤️";
        addSparkleEffect();
      });

      moodituButton.addEventListener('click', () => {
        response.innerHTML = `
          Unnaku vera option eh illa.<br>
          <button id="finalYesButton">Yesss</button>
        `;

        const finalYesButton = document.getElementById('finalYesButton');
        finalYesButton.addEventListener('click', () => {
          valentineQuestion.style.display = "none"; // Hide the initial question
          response.innerHTML = "<span class='big-message'>I love you baby boy 🫂❤️</span>";
          addSparkleEffect();
          addKissyEmojis();
        });
      });
    });

    function addSparkleEffect() {
      const sparkle = document.createElement('div');
      sparkle.classList.add('sparkle');
      sparkle.innerHTML = "💋";
      document.body.appendChild(sparkle);

      const x = Math.random() * window.innerWidth;
      const y = Math.random() * window.innerHeight;
      sparkle.style.left = `${x}px`;
      sparkle.style.top = `${y}px`;

      setTimeout(() => {
        sparkle.remove();
      }, 1000);
    }

    function addKissyEmojis() {
      const numOfKisses = 5; // Number of kissy emojis to appear
      for (let i = 0; i < numOfKisses; i++) {
        const kissy = document.createElement('div');
        kissy.classList.add('kissy');
        kissy.innerHTML = "💋";
        
        const x = Math.random() * window.innerWidth;
        kissy.style.left = `${x}px`;
        
        // Randomize animation speed and direction
        const delay = Math.random() * 2 + 3;  // Random delay from 10s to 15s
        kissy.style.animationDuration = `${delay}s`;

        document.body.appendChild(kissy);

        setTimeout(() => {
          kissy.remove(); // Remove after animation
        }, delay * 100000);
      }
    }
  </script>
</body>
</html>
