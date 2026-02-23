# Deepak-kiran
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>9 Years of Love</title>

<style>
body{
  margin:0;
  font-family: Arial, sans-serif;
  text-align:center;
  background: linear-gradient(to bottom right, #ffc0cb, #ffe6f2);
  overflow-x:hidden;
}

h1{
  margin-top:20px;
}

.section{
  margin:60px 20px;
}

button{
  padding:12px 22px;
  margin:10px;
  border:none;
  border-radius:25px;
  background:#ff69b4;
  color:white;
  font-size:16px;
  cursor:pointer;
  transition:0.3s;
  position:relative;
}

button:hover{
  transform:scale(1.1);
}

img{
  width:320px;
  border-radius:20px;
  box-shadow:0 0 20px pink;
}

.fade{
  position:absolute;
  left:50%;
  transform:translateX(-50%);
  opacity:0;
  transition:opacity 2s;
}

.confetti{
  position:fixed;
  width:10px;
  height:10px;
  top:-10px;
  animation: fall 3s linear forwards;
}

@keyframes fall{
  to{
    transform: translateY(100vh) rotate(360deg);
  }
}

.heart{
  position:fixed;
  font-size:20px;
  animation: float 5s linear infinite;
}

@keyframes float{
  from{ transform: translateY(100vh); }
  to{ transform: translateY(-10vh); }
}
</style>
</head>

<body>

<audio autoplay loop>
  <source src="perfect.mp3" type="audio/mpeg">
</audio>

<h1>Happy 9th Anniversary Deepak Mama & Kiran Mami ❤️</h1>

<div class="section">
  <h2>Family</h2>
  <p>Built with love, laughter and forever memories.</p>
</div>

<div class="section" style="position:relative; height:360px;">
  <img id="slideshow" src="photo1.jpg" class="fade" style="opacity:1;">
</div>

<div class="section">
  <h2>Spin Love Wheel</h2>
  <button onclick="spinLove()">Spin</button>
</div>

<div class="section">
  <h2>In your next birth, would you choose another wife?</h2>
  <button id="yesBtn" onmouseover="moveYes()">Yes</button>
  <button onclick="correctAnswer('Awww that’s so cute. Of course your love is bonded for infinity births… and honestly you won’t find someone as pretty, kind, soft and pure hearted like Mami 😚')">No</button>
</div>

<div class="section">
  <h2>Who controls the TV?</h2>
  <button onclick="wrongAnswer()">Deepak Mama</button>
  <button onclick="wrongAnswer()">Kiran Mami</button>
  <button onclick="correctAnswer('House hierarchy confirmed. Kids rule 🤭')">Kids</button>
</div>

<div class="section">
  <h2>Shopping Superpower Test</h2>
  <button onclick="wrongAnswer()">2 seconds</button>
  <button onclick="wrongAnswer()">5 seconds</button>
  <button onclick="correctAnswer('Legendary instincts detected 👑')">Already bought it online yesterday</button>
</div>

<div class="section">
  <h2>Family CEO?</h2>
  <button onclick="wrongAnswer()">Deepak Mama</button>
  <button onclick="wrongAnswer()">Kids</button>
  <button onclick="correctAnswer('CEO confirmed 👑')">Kiran Mami</button>
</div>

<div class="section">
  <h3>Made with love by Peehu ❤️</h3>
</div>

<script>

let images = [
"photo1.jpg",
"photo2.jpg",
"photo3.jpg",
"photo4.jpg",
"photo5.jpg",
"photo6.jpg",
"photo7.jpg",
"photo8.jpg",
"photo9.jpg"
];

let index = 0;
let slideshow = document.getElementById("slideshow");

setInterval(function(){
  index = (index + 1) % images.length;
  slideshow.style.opacity = 0;
  setTimeout(function(){
    slideshow.src = images[index];
    slideshow.style.opacity = 1;
  },1000);
},4000);

function moveYes(){
  let btn = document.getElementById("yesBtn");
  btn.style.position = "absolute";
  btn.style.left = Math.random()*300 + "px";
  btn.style.top = Math.random()*200 + "px";
}

function wrongAnswer(){
  alert("Hmm… not quite. Try again.");
}

function correctAnswer(message){
  alert(message);
  confetti();
}

function spinLove(){
  alert("100% Perfect Match Always ❤️");
  confetti();
}

function confetti(){
  for(let i=0;i<60;i++){
    let c = document.createElement("div");
    c.className = "confetti";
    c.style.left = Math.random()*100 + "vw";
    c.style.backgroundColor = "hsl("+Math.random()*360+",100%,50%)";
    document.body.appendChild(c);
    setTimeout(function(){ c.remove(); },3000);
  }
}

setInterval(function(){
  let h = document.createElement("div");
  h.className = "heart";
  h.innerHTML = "❤️";
  h.style.left = Math.random()*100 + "vw";
  document.body.appendChild(h);
  setTimeout(function(){ h.remove(); },5000);
},1200);

</script>

</body>
</html>