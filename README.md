# valentine
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Для тебя ❤️</title>
<style>
body {
  margin: 0;
  font-family: 'Arial', sans-serif;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  color: white;
  text-align: center;
  overflow: hidden;
}
.slide {
  display: none;
  height: 100vh;
  padding: 40px;
  box-sizing: border-box;
}
.active { display: block; }

button {
  padding: 15px 30px;
  font-size: 20px;
  border: none;
  border-radius: 30px;
  background: white;
  color: #ff4f7a;
  cursor: pointer;
  margin-top: 40px;
}

.item {
  font-size: 26px;
  margin: 25px 0;
  cursor: pointer;
}
.hidden {
  display: none;
  font-size: 18px;
  margin-top: 10px;
}

.heart, .emoji {
  position: absolute;
  animation: float 4s linear infinite;
}
[club66008961|@keyframes] float {
  from { transform: translateY(100vh); opacity: 1; }
  to { transform: translateY(-10vh); opacity: 0; }
}
</style>
</head>

<body>

<!-- Слайд 1 -->
<div class="slide active" id="slide1">
  <h1>Любимка моя, это для тебя ❤️</h1>
  <button onclick="openLove()">Открыть</button>
</div>

<!-- Слайд 2 -->
<div class="slide" id="slide2">
  <div class="item" onclick="toggle(this)">
    Ты у меня красивый 😍
    <div class="hidden">самый сексуальный и романтичный 💋</div>
  </div>

  <div class="item" onclick="toggle(this)">
    Твой юмор 🥴
    <div class="hidden">я всегда смеюсь, даже если это не показываю 😂</div>
  </div>

  <div class="item" onclick="toggle(this)">
    Ты сильный 💪🏻
    <div class="hidden">эмоционально хорош и не отступаешь от своих начинаний 🍀</div>
  </div>

  <div class="item" onclick="toggle(this)">
    Мы ♾️
    <div class="hidden">мы очень любим друг друга и всегда будем вместе ❤️‍🔥</div>
  </div>

  <button onclick="nextSlide()">Дальше 💖</button>
</div>

<!-- Слайд 3 -->
<div class="slide" id="slide3">
  <h1>С Днём Святого Валентина 💘</h1>
  <h2>Я тебя люблю ❤️</h2>
</div>

<script>
function openLove() {
  hearts(30);
  setTimeout(() => {
    document.getElementById("slide1").classList.remove("active");
    document.getElementById("slide2").classList.add("active");
  }, 1200);
}

function toggle(el) {
  el.querySelector(".hidden").classList.toggle("hidden");
}

function nextSlide() {
  document.getElementById("slide2").classList.remove("active");
  document.getElementById("slide3").classList.add("active");
  confetti(50);
}

function hearts(count) {
  for (let i = 0; i < count; i++) {
    let h = document.createElement("div");
    h.className = "heart";
    h.innerText = "❤️";
    h.style.left = Math.random() * 100 + "vw";
    h.style.animationDuration = 2 + Math.random() * 3 + "s";
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 4000);
  }
}

function confetti(count) {
  const emojis = ["❤️","💘","😍","💕","💖"];
  for (let i = 0; i < count; i++) {
    let e = document.createElement("div");
    e.className = "emoji";
    e.innerText = emojis[Math.floor(Math.random()*emojis.length)];
    e.style.left = Math.random() * 100 + "vw";
    e.style.animationDuration = 2 + Math.random() * 3 + "s";
    document.body.appendChild(e);
    setTimeout(() => e.remove(), 4000);
  }
}
</script>

</body>
</html>
