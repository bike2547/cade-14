
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Card</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: pink;
      font-family: 'Segoe UI', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
    }

    .card-container {
      position: relative;
      width: 200px;
      height: 120px;
    }

    .envelope {
      width: 100%;
      height: 100%;
      background: #ff4d6d;
      clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%);
      position: relative;
      cursor: pointer;
    }

    .flap {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 60px;
      background: #ff708d;
      clip-path: polygon(0 0, 100% 0, 50% 100%);
      transform-origin: top;
      transition: transform 1s ease;
      z-index: 2;
    }

    .flap.open {
      transform: rotateX(180deg);
    }

    .message {
      margin-top: 30px;
      font-size: 1.5em;
      color: darkred;
      display: none;
      animation: fadeIn 1s forwards;
      text-align: center;
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(10px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .show {
      display: block;
    }

    .hint {
      margin-top: 10px;
      font-size: 0.9em;
      color: #800000;
      opacity: 0.7;
    }
  </style>
</head>
<body>

  <div class="card-container" onclick="openCard()">
    <div class="envelope"></div>
    <div class="flap" id="flap"></div>
  </div>

  <div class="message" id="Message">💖 For you 💖<br>เป็นแฟนกับพี่นะคับหนู</div>
  <div class="hint">(จดหมายรัก 💌)</div>

  <audio id="bgMusic" src="c:\Users\sorayut\Downloads\- COCKTAIL _Official MV_.mp3" preload="auto"></audio>

  <script>
    function openCard() {
      document.getElementById("flap").classList.add("open");
      document.getElementById("Message").classList.add("show");
      document.getElementById("bgMusic").play();
    }
  </script>

</body>
</html>
