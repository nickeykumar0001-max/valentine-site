<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Be My Valentine 💖</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<audio id="music" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<div class="container">
  <h1>Happy Valentine Day 💘</h1>
  <p class="text">Will you be my Valentine? 🌹</p>

  <div class="buttons">
    <button id="yes">Yes 💖</button>
    <button id="no">No 💔</button>
  </div>
</div>

<div class="hearts"></div>

<script src="script.js"></script>
</body>
</html># valentine-site
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Segoe UI', sans-serif;
  overflow: hidden;
}

.container {
  background: white;
  padding: 30px 40px;
  border-radius: 20px;
  text-align: center;
  box-shadow: 0 0 25px rgba(255,0,0,0.4);
  animation: pop 1s ease;
}

h1 {
  color: #ff3366;
}

.text {
  font-size: 18px;
  margin: 15px 0;
}

.buttons button {
  padding: 10px 25px;
  margin: 10px;
  font-size: 16px;
  border: none;
  border-radius: 20px;
  cursor: pointer;
}

#yes {
  background: #ff3366;
  color: white;
}

#no {
  background: #ccc;
}

@keyframes pop {
  0% {transform: scale(0);}
  100% {transform: scale(1);}
}

/* Floating hearts */
.heart {
  position: absolute;
  color: red;
  font-size: 20px;
  animation: float 5s linear infinite;
}

@keyframes float {
  0% {transform: translateY(0); opacity: 1;}
  100% {transform: translateY(-600px); opacity: 0;}
}
const noBtn = document.getElementById("no");
const yesBtn = document.getElementById("yes");
const music = document.getElementById("music");

// No button bhagega 😄
noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * (window.innerWidth - 100);
  const y = Math.random() * (window.innerHeight - 50);
  noBtn.style.position = "absolute";
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";
});

// Yes click = Love 💖
yesBtn.addEventListener("click", () => {
  document.querySelector(".text").innerHTML = "I Love You ❤️ Forever 💍";
  music.play();
  createHearts();
});

function createHearts() {
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * window.innerWidth + "px";
    heart.style.bottom = "0px";
    document.body.appendChild(heart);

    setTimeout(() => {
      heart.remove();
    }, 5000);
  }, 300);
}
