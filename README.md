<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy Birthday Manjushaa 🎂</title>
<style>
  body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    text-align: center;
    overflow: hidden;
    min-height: 100vh;
    animation: rainbowBG 20s linear infinite;
    background: linear-gradient(135deg, #7b2ff7, #f107a3, #ffdd00, #00ffdd, #ff00ff);
    background-size: 500% 500%;
  }

  @keyframes rainbowBG {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  h1, h2 {
    margin: 20px;
  }

  .welcome {
    font-size: 2rem;
    margin-top: 50px;
    animation: glow 2s infinite alternate;
    color: #fff;
  }

  @keyframes glow {
    0% { text-shadow: 0 0 10px #fff, 0 0 20px #f0f, 0 0 30px #7b2ff7; }
    100% { text-shadow: 0 0 20px #ff0, 0 0 30px #f107a3, 0 0 40px #fff; }
  }

  .gift-icon {
    font-size: 4rem;
    margin-top: 50px;
    cursor: pointer;
    animation: bounce 1s infinite;
  }

  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-20px); }
  }

  .special-day, .final-message {
    display: none;
    margin-top: 30px;
    font-size: 1.5rem;
    animation: fadeIn 1s forwards;
  }

  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  .birthday-image {
    display: none;
    margin-top: 30px;
    width: 200px;
    height: 200px;
    border-radius: 50%;
    border: 5px solid #fff;
    animation: pop 1s forwards;
  }

  @keyframes pop {
    0% { transform: scale(0); }
    100% { transform: scale(1); }
  }

  .balloons, .confetti, .fireworks {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    overflow: hidden;
  }

  .balloon {
    width: 40px;
    height: 60px;
    border-radius: 50% 50% 50% 50%;
    position: absolute;
    bottom: -60px;
    animation: rise linear infinite;
  }

  @keyframes rise {
    0% { bottom: -60px; transform: translateX(0) rotate(0deg); }
    100% { bottom: 120%; transform: translateX(50px) rotate(360deg); }
  }

  .confetti-piece {
    position: absolute;
    width: 8px;
    height: 8px;
    border-radius: 2px;
    opacity: 0.9;
    animation: confetti-fall linear forwards;
  }

  @keyframes confetti-fall {
    0% { transform: translateY(0) rotate(0deg); opacity: 1; }
    100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
  }

  .firework {
    position: absolute;
    width: 5px;
    height: 5px;
    border-radius: 50%;
    animation: explode 1s ease-out forwards;
  }

  @keyframes explode {
    0% { transform: scale(0); opacity: 1; }
    100% { transform: scale(10); opacity: 0; }
  }

  .sparkle-text {
    display: inline-block;
    font-size: 2rem;
    font-weight: bold;
    background: linear-gradient(45deg, red, yellow, green, blue, pink);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: sparkle 2s linear infinite;
  }

  @keyframes sparkle {
    0% { background-position: 0% 50%; }
    100% { background-position: 100% 50%; }
  }

</style>
</head>
<body>

<h1 class="welcome">Welcome Manjushaa 😊</h1>
<div class="gift-icon" onclick="startSurprise()">🎁</div>

<h2 class="special-day">Today is a Special Day 🎉</h2>

<img src="manjushaa.jpg" alt="Manjushaa" class="birthday-image">

<h2 class="final-message sparkle-text">Happy Birthday Manjushaa (cutiepie) ❤️<br>Have a nice day with birthday blasts and joy 🎊</h2>

<audio id="birthday-music" src="song.mp3"></audio>

<div class="balloons" id="balloon-container"></div>
<div class="confetti" id="confetti-container"></div>
<div class="fireworks" id="fireworks-container"></div>

<script>
function startSurprise() {
  document.querySelector('.special-day').style.display = 'block';

  setTimeout(() => {
    document.querySelector('.birthday-image').style.display = 'block';
    document.querySelector('.final-message').style.display = 'block';

    document.getElementById('birthday-music').play();

    // Continuous balloons
    setInterval(() => {
      let balloon = document.createElement('div');
      balloon.className = 'balloon';
      balloon.style.backgroundColor = `hsl(${Math.random()*360}, 70%, 60%)`;
      balloon.style.left = `${Math.random()*90}%`;
      balloon.style.animationDuration = `${3 + Math.random()*3}s`;
      document.getElementById('balloon-container').appendChild(balloon);
      setTimeout(() => balloon.remove(), 7000);
    }, 500);

    // Continuous confetti
    setInterval(() => {
      let confetti = document.createElement('div');
      confetti.className = 'confetti-piece';
      confetti.style.backgroundColor = `hsl(${Math.random()*360}, 80%, 60%)`;
      confetti.style.left = `${Math.random()*100}%`;
      confetti.style.animationDuration = `${2 + Math.random()*3}s`;
      document.getElementById('confetti-container').appendChild(confetti);
      setTimeout(() => confetti.remove(), 5000);
    }, 200);

    // Continuous fireworks
    setInterval(() => {
      createFirework();
    }, 400);

  }, 1500);
}

// Function to create a firework at random position
function createFirework() {
  let firework = document.createElement('div');
  firework.className = 'firework';
  firework.style.top = `${Math.random()*80}%`;
  firework.style.left = `${Math.random()*90}%`;
  firework.style.backgroundColor = `hsl(${Math.random()*360}, 100%, 50%)`;
  document.getElementById('fireworks-container').appendChild(firework);
  setTimeout(() => firework.remove(), 1000);
}

// Extra fireworks when user taps anywhere
document.body.addEventListener('click', (e) => {
  if(document.querySelector('.final-message').style.display === 'block') {
    for(let i=0; i<5; i++){
      let firework = document.createElement('div');
      firework.className = 'firework';
      firework.style.top = `${e.clientY + (Math.random()*40-20)}px`;
      firework.style.left = `${e.clientX + (Math.random()*40-20)}px`;
      firework.style.backgroundColor = `hsl(${Math.random()*360}, 100%, 50%)`;
      document.getElementById('fireworks-container').appendChild(firework);
      setTimeout(() => firework.remove(), 1000);
    }
  }
});
</script>

</body>
</html>
