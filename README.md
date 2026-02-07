# always-here
A small, gentle page made to offer comfort and encouragement.
<!DOCTYPE html>
<html>
<head>
  <title>Always Here 🌷</title>

  <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap" rel="stylesheet">

  <style>
    body {
      background: linear-gradient(180deg, #fff1f6, #eef4ff);
      font-family: 'Quicksand', sans-serif;
      text-align: center;
      padding: 70px 30px;
      overflow: hidden;
      color: #666;
    }

    h1 {
      color: #c18fb3;
      font-size: 34px;
      margin-bottom: 25px;
      animation: fadeIn 2s ease;
    }

    p {
      font-size: 20px;
      line-height: 1.7;
      opacity: 0;
      animation: fadeIn 1.8s ease forwards;
    }

    .hint {
      font-size: 14px;
      color: #aaa;
      margin-top: 45px;
      animation: fadeIn 3s ease forwards;
    }

    .float {
      position: absolute;
      animation: drift 9s linear infinite;
      user-select: none;
      opacity: 0.85;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes drift {
      0% {
        transform: translateY(0);
        opacity: 0.9;
      }
      100% {
        transform: translateY(-800px);
        opacity: 0;
      }
    }
  </style>
</head>

<body onclick="nextMessage()">

  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-tenderness.mp3" type="audio/mpeg">
  </audio>

  <h1>Hey Luna 🌷</h1>

  <p id="message">
    I know today might feel a little heavier,  
    so I wanted to leave something gentle here for you.
  </p>

  <div class="hint">(tap anywhere)</div>

  <script>
    const messages = [
      "Your body is doing a lot today.",
      "Feeling tired or uncomfortable is completely valid.",
      "You don’t need to push yourself right now.",
      "Slow moments are allowed.",
      "Small comforts matter more today.",
      "Warm drinks. Deep breaths. Quiet rest.",
      "You’re not weak for needing a pause.",
      "Even on days like this, you’re still you.",
      "This discomfort won’t last forever.",
      "Be kind to yourself today — extra kind.",
      "Sending you calm, comfort, and gentle strength.",
      "— always here"
    ];

    let index = 0;
    const messageEl = document.getElementById("message");

    function nextMessage() {
      if (index < messages.length) {
        messageEl.style.opacity = 0;
        setTimeout(() => {
          messageEl.innerText = messages[index];
          messageEl.style.opacity = 1;
          index++;
          createFloat();
        }, 600);
      }
    }

    function createFloat() {
      const item = document.createElement("div");
      item.className = "float";

      const symbols = ["🌸", "☁️", "🍵", "🤍", "🫶"];
      item.innerText = symbols[Math.floor(Math.random() * symbols.length)];

      item.style.left = Math.random() * window.innerWidth + "px";
      item.style.fontSize = (Math.random() * 22 + 14) + "px";
      item.style.color = Math.random() > 0.5 ? "#e8b6c8" : "#c8d3f0";

      document.body.appendChild(item);

      setTimeout(() => item.remove(), 9000);
    }

    setInterval(createFloat, 1500);
  </script>

</body>
</html>
