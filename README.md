<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>A Special Question 💖</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Poppins", sans-serif;
    }

    body {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      background: linear-gradient(135deg, #ff758c, #ff7eb3, #c471ed);
    }

    .card {
      width: 90%;
      max-width: 500px;
      padding: 40px 25px;
      text-align: center;
      background: rgba(255, 255, 255, 0.95);
      border-radius: 30px;
      box-shadow: 0 20px 60px rgba(0, 0, 0, 0.25);
      position: relative;
      z-index: 2;
    }

    .heart {
      font-size: 70px;
      animation: heartbeat 1.2s infinite;
    }

    @keyframes heartbeat {
      0%, 100% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.2);
      }
    }

    h1 {
      color: #ff4f81;
      margin: 15px 0;
      font-size: 32px;
    }

    p {
      color: #555;
      font-size: 18px;
      line-height: 1.6;
      margin-bottom: 25px;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      position: relative;
      min-height: 55px;
    }

    button {
      border: none;
      padding: 14px 28px;
      border-radius: 30px;
      font-size: 17px;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s;
    }

    #yesBtn {
      background: #ff4f81;
      color: white;
      box-shadow: 0 8px 20px rgba(255, 79, 129, 0.4);
    }

    #yesBtn:hover {
      transform: scale(1.1);
      background: #ff2f68;
    }

    #noBtn {
      background: #eee;
      color: #555;
      position: relative;
    }

    .message {
      display: none;
      animation: appear 0.8s ease;
    }

    .message h2 {
      color: #ff4f81;
      margin-bottom: 15px;
    }

    .message p {
      font-size: 19px;
    }

    @keyframes appear {
      from {
        opacity: 0;
        transform: scale(0.5);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    .floating-heart {
      position: absolute;
      bottom: -50px;
      font-size: 25px;
      animation: floatUp 6s linear infinite;
      opacity: 0.7;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 0;
      }
      20% {
        opacity: 0.8;
      }
      100% {
        transform: translateY(-110vh) rotate(360deg);
        opacity: 0;
      }
    }

    .signature {
      margin-top: 15px;
      color: #ff4f81;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <!-- Floating hearts -->
  <div class="floating-heart" style="left:10%; animation-delay:0s;">💗</div>
  <div class="floating-heart" style="left:25%; animation-delay:2s;">💕</div>
  <div class="floating-heart" style="left:45%; animation-delay:4s;">💖</div>
  <div class="floating-heart" style="left:65%; animation-delay:1s;">💘</div>
  <div class="floating-heart" style="left:85%; animation-delay:3s;">❤️</div>

  <div class="card">

    <!-- Question Section -->
    <div id="question">
      <div class="heart">💗</div>

      <h1>Hey, Bestie...</h1>

      <p>
        We've shared so many laughs, secrets, crazy memories
        and unforgettable moments together.
        <br><br>

        But there's something I've been wanting to ask you...
        <br><br>

        <strong>Will you be my forever best friend? 🥹❤️</strong>
      </p>

      <div class="buttons">
        <button id="yesBtn" onclick="sayYes()">
          YES! 💖
        </button>

        <button id="noBtn">
          No 😜
        </button>
      </div>
    </div>

    <!-- Success Message -->
    <div class="message" id="message">
      <div class="heart">🥰</div>

      <h2>YAAAAAY! 💖🎉</h2>

      <p>
        I knew you'd say yes! 😭❤️
        <br><br>
        You're not just my best friend...
        You're one of the most special people in my life.
        <br><br>
        Here's to many more memories, laughs,
        adventures and crazy moments together! 🫶
      </p>

      <div class="signature">
        Forever Besties 💕
      </div>
    </div>

  </div>

  <script>
    const noBtn = document.getElementById("noBtn");

    // Make the NO button run away 😜
    noBtn.addEventListener("mouseover", function () {
      const x = Math.random() * 250 - 125;
      const y = Math.random() * 150 - 75;

      noBtn.style.transform =
        `translate(${x}px, ${y}px)`;
    });

    function sayYes() {
      document.getElementById("question").style.display = "none";
      document.getElementById("message").style.display = "block";

      createHearts();
    }

    // Celebration hearts
    function createHearts() {
      for (let i = 0; i < 40; i++) {
        const heart = document.createElement("div");

        heart.innerHTML = ["❤️", "💖", "💕", "💗", "💘"][Math.floor(Math.random() * 5)];

        heart.style.position = "fixed";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.top = Math.random() * 100 + "vh";
        heart.style.fontSize = (20 + Math.random() * 30) + "px";
        heart.style.zIndex = "10";
        heart.style.pointerEvents = "none";

        document.body.appendChild(heart);

        heart.animate(
          [
            {
              transform: "translateY(0) scale(1)",
              opacity: 1
            },
            {
              transform:
                `translateY(-${100 + Math.random() * 300}px) rotate(360deg) scale(0)`,
              opacity: 0
            }
          ],
          {
            duration: 1500 + Math.random() * 2000,
            easing: "ease-out"
          }
        );

        setTimeout(() => heart.remove(), 3500);
      }
    }






    
  </script>

</body>
</html>
