<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine 💕</title>

<!-- soft romantic font -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital@0;1&family=Quicksand:wght@400;600&display=swap" rel="stylesheet">

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ffb6c1, #ffe4e1);
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  font-family: 'Quicksand', sans-serif;
}

.page {
  display: none;
  text-align: center;
  background: white;
  padding: 35px;
  border-radius: 30px;
  box-shadow: 0 20px 50px rgba(0,0,0,0.2);
  max-width: 90%;
}

.page.active {
  display: block;
}

h1, h2 {
  font-family: 'Playfair Display', serif;
  color: #ff4d6d;
}

button {
  padding: 12px 30px;
  margin: 15px;
  border: none;
  border-radius: 30px;
  font-size: 16px;
  cursor: pointer;
}

#yes {
  background: #ff4d6d;
  color: white;
}

#no {
  background: #ddd;
  position: relative;
}

.message {
  color: #555;
  line-height: 1.7;
  font-size: 15px;
}

/* floating hearts & flowers */
.float {
  position: absolute;
  animation: floatUp 6s linear infinite;
}

@keyframes floatUp {
  0% {transform: translateY(100vh); opacity: 1;}
  100% {transform: translateY(-10vh); opacity: 0;}
}

/* celebration bubbles */
.bubble {
  position: absolute;
  bottom: 0;
  animation: bubbleUp 3s ease-out forwards;
}

@keyframes bubbleUp {
  0% {transform: translateY(0) scale(0.5); opacity: 1;}
  100% {transform: translateY(-400px) scale(1.2); opacity: 0;}
}
</style>
</head>

<body>

<audio id="music" loop>
  <source src="https://dl.sndup.net/mf8p/Indila%20-%20Love%20Story.mp3" type="audio/mpeg">
</audio>

<!-- PAGE 1 -->
<div class="page active" id="page1">
  <h1>Brenda 💕</h1>
  <h2>Do you wanna be my Valentine? 🌹</h2>
  <button id="yes" onclick="goNext()">Yes 💖</button>
  <button id="no" onmouseover="runAway()">No 🙃</button>
</div>

<!-- PAGE 2 -->
<div class="page" id="page2">
  <h1>Happy Valentine’s 💐</h1>
  <div class="message">
    So… I wanted to do something special my Valentine 😆 💕<br><br>

    Even if we’re miles apart, I want this Valentine’s afternoon to be ours. Just you and me.<br><br>

    Thank you for being in my life, for choosing me every day in your own way, and for letting me love you the way I do. I’m really grateful we have each other 🤍<br><br>

    I’d love for us to spend that time talking about how much we love each other, laughing, being soft, and doing cute little things together.<br><br>

    For the activities maybe something we used to do — we can talk about that more later: sharing a playlist, asking each other sweet questions, talking freely, and just enjoying that soft, happy feeling of being connected.<br><br>

    After all it’s not about doing a lot, it’s about being — and I’d love to be with you in that time 💖
  </div>
</div>

<script>
function runAway() {
  const btn = document.getElementById("no");
  const x = Math.random() * 300 - 150;
  const y = Math.random() * 300 - 150;
  btn.style.transform = `translate(${x}px, ${y}px)`;
}

function goNext() {
  document.getElementById("page1").classList.remove("active");
  document.getElementById("page2").classList.add("active");

  document.getElementById("music").play();
  celebrate();
}

function createFloat() {
  const el = document.createElement("div");
  el.className = "float";
  el.innerHTML = Math.random() > 0.5 ? "💖" : "🌸";
  el.style.left = Math.random() * 100 + "vw";
  el.style.fontSize = (Math.random() * 20 + 15) + "px";
  document.body.appendChild(el);
  setTimeout(() => el.remove(), 6000);
}

setInterval(createFloat, 500);

function celebrate() {
  for (let i = 0; i < 25; i++) {
    const bubble = document.createElement("div");
    bubble.className = "bubble";
    bubble.innerHTML = "✨";
    bubble.style.left = Math.random() * 100 + "vw";
    bubble.style.fontSize = (Math.random() * 20 + 15) + "px";
    document.body.appendChild(bubble);
    setTimeout(() => bubble.remove(), 3000);
  }
}
</script>

</body>
</html># Valentin-
