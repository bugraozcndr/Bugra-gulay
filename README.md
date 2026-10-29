# Bugra-gulay
Bugra gulay
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sana Özel ❤️</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: radial-gradient(circle at center, #2b0814 0%, #0d0106 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      overflow: hidden;
      color: #fff;
      position: relative;
    }
    .card {
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.15);
      padding: 30px 20px;
      border-radius: 24px;
      text-align: center;
      max-width: 420px;
      width: 90%;
      box-shadow: 0 20px 50px rgba(227, 38, 54, 0.25);
      z-index: 10;
      animation: fadeIn 2s ease-in-out;
    }
    .photo-container {
      width: 190px;
      height: 190px;
      margin: 0 auto 20px;
      border-radius: 50%;
      padding: 5px;
      background: linear-gradient(45deg, #ff4d6d, #ff758f, #ffb3c1);
      box-shadow: 0 0 25px rgba(255, 77, 109, 0.6);
      animation: pulse 3s infinite ease-in-out;
    }
    .photo-container img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 50%;
    }
    .text-box {
      font-size: 1.25rem;
      line-height: 1.6;
      font-weight: 500;
      min-height: 90px;
      color: #fff0f3;
      text-shadow: 0 2px 10px rgba(0,0,0,0.5);
    }
    .heart-particle {
      position: absolute;
      color: #ff4d6d;
      font-size: 20px;
      user-select: none;
      pointer-events: none;
      animation: flyUp linear infinite;
    }
    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.04); }
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes flyUp {
      0% {
        transform: translateY(105vh) scale(0.5);
        opacity: 0;
      }
      20% { opacity: 0.8; }
      80% { opacity: 0.8; }
      100% {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <div class="photo-container">
      <!-- Birlikte çekildiğiniz fotoğrafın dosya adı -->
      <img src="biz.jpg" alt="Biz">
    </div>
    <div class="text-box" id="typing-text"></div>
  </div>

  <script>
    // Yazılacak metin
    const text = "Egemenlik kayıtsız şartsız milletindir ama bu kalp tamamen senindir ❤️";
    let index = 0;
    const speed = 70;

    function typeWriter() {
      if (index < text.length) {
        document.getElementById("typing-text").innerHTML += text.charAt(index);
        index++;
        setTimeout(typeWriter, speed);
      }
    }

    // Uçuşan kalp tanecikleri üretimi
    function createHearts() {
      const heartChars = ['❤️', '💖', '💕', '✨', '💓'];
      for (let i = 0; i < 25; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart-particle';
        heart.innerText = heartChars[Math.floor(Math.random() * heartChars.length)];
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
        heart.style.animationDelay = (Math.random() * 5) + 's';
        heart.style.fontSize = (Math.random() * 16 + 14) + 'px';
        document.body.appendChild(heart);
      }
    }

    window.onload = () => {
      createHearts();
      setTimeout(typeWriter, 800);
    };
  </script>
</body>
</html>
