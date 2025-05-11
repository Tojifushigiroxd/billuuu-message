<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Black Cat Prank</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: black;
      color: white;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      overflow: hidden;
    }
    .container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
    }
    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 20px;
      background-color: #222;
      color: white;
      border: 2px solid white;
      cursor: pointer;
    }
    .emoji {
      position: absolute;
      font-size: 30px;
      animation: float 3s ease-in-out infinite;
    }
    @keyframes float {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-300px) scale(0.5); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="container" id="question-container">
    <h1>ek question puchu??😺</h1>
    <button onclick="nextQuestion('ha')">ha</button>
    <button onclick="nextQuestion('noi')">noi</button>
  </div>  <script>
    function spawnEmoji(char) {
      for (let i = 0; i < 15; i++) {
        const emoji = document.createElement('div');
        emoji.className = 'emoji';
        emoji.innerText = char;
        emoji.style.left = Math.random() * window.innerWidth + 'px';
        emoji.style.top = Math.random() * window.innerHeight + 'px';
        document.body.appendChild(emoji);

        setTimeout(() => emoji.remove(), 3000);
      }
    }

    function nextQuestion(choice) {
      spawnEmoji('😾');
      let container = document.getElementById('question-container');
      let questionText = '';
      if (choice === 'ha') {
        questionText = 'tu mujhe bakchod bana rhi h na😙';
      } else {
        questionText = 'tab bhi puchunga... tu mujhe bakchod bana rhi h na😙';
      }
      container.innerHTML = `
        <h1>${questionText}</h1>
        <button onclick="finalAnswer('haa')">haa</button>
        <button onclick="finalAnswer('bilkul')">bilkul nahi</button>
      `;
    }

    function finalAnswer(finalChoice) {
      spawnEmoji('🖕');
      if (finalChoice === 'haa') {
        alertWithTitle("billu is saying that", "Fuck u I don't care");
      } else {
        alertWithTitle("billu is saying that", "still fuck u I don't care now");
      }
    }

    function alertWithTitle(title, msg) {
      const customPopup = document.createElement('div');
      customPopup.style.position = 'fixed';
      customPopup.style.top = '30%';
      customPopup.style.left = '50%';
      customPopup.style.transform = 'translate(-50%, -50%)';
      customPopup.style.background = '#111';
      customPopup.style.color = 'white';
      customPopup.style.padding = '20px';
      customPopup.style.border = '2px solid white';
      customPopup.style.zIndex = '9999';
      customPopup.innerHTML = `<h2>${title}</h2><p>${msg}</p>`;
      document.body.appendChild(customPopup);

      setTimeout(() => customPopup.remove(), 3000);
    }
  </script></body>
</html>
