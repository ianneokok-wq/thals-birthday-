

<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>For You — ♡</title>
<style>
  
  /*
* Prefixed by https://autoprefixer.github.io
* PostCSS: v8.4.14,
* Autoprefixer: v10.4.7
* Browsers: last 4 version
*/

:root {
  --bg:#0f1022;
  --accent:#ff6b9a;
  --accent-2:#ffd166;
  --glass:rgba(255,255,255,0.06);
}
*{-webkit-box-sizing:border-box;box-sizing:border-box;}
html,body{
  height:100%;margin:0;font-family:'Inter',sans-serif;
}
body{
  background: radial-gradient(1200px 600px at 10% 20%, rgba(241, 0, 76, 0.5), transparent),
              radial-gradient(1000px 500px at 90% 80%, rgba(255,209,102,0.03), transparent),
              var(--bg);
  color:#eee;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:32px;
  overflow:hidden;
}

.card{
  width:100%;max-width:960px;
  background: linear-gradient(180deg, rgba(138, 4, 131, 0.5), rgba(255,255,255,0.01));
  border-radius:18px;padding:28px;
  box-shadow:0 10px 40px rgba(2,6,23,0.6);
  position:relative;overflow:hidden;border:1px solid rgba(255,255,255,0.03)
}
.split{display:grid;grid-template-columns:1fr 420px;gap:22px;align-items:center}
@media (max-width:880px){.split{grid-template-columns:1fr}.side{order:-1}}
h1{font-size:2.1rem;margin:0 0 8px 0;letter-spacing:0.4px}
.subtitle{color:rgba(255, 0, 179, 1);margin-bottom:18px}
.photo{
  background:linear-gradient(135deg,rgba(202,0,185,0.03),rgba(255,255,255,0.01));
  border-radius:14px;padding:12px;
  display:flex;flex-direction:column;align-items:center;gap:12px
}
.photo img{
  width:100%;max-width:320px;border-radius:10px;
  box-shadow:0 8px 30px rgba(2,6,23,0.6);
  transition:opacity 1s ease-in-out
}

/* ⭐ SCROLLABLE MAIN MESSAGE */
.message{
  margin-top:18px;padding:16px;
  background:var(--glass);
  border-radius:12px;color:#fff;
  line-height:1.5;font-size:1rem;

  max-height:220px;        /* scrollbox height */
  overflow-y:auto;         /* enable scroll */
}

/* Scrollbar design */
.message::-webkit-scrollbar { width: 6px; }
.message::-webkit-scrollbar-thumb {
  background: rgba(255,107,154,0.5);
  border-radius:10px;
}

.controls{display:flex;gap:12px;margin-top:8px}
button{
  background:linear-gradient(90deg,var(--accent),var(--accent-2));
  border:none;color:#111;padding:10px 14px;border-radius:12px;
  font-weight:700;cursor:pointer;
  box-shadow:0 6px 18px rgba(255,107,154,0.12);
  transition:transform .2s;
}
button:hover{transform:scale(1.1)}
footer{margin-top:14px;color:rgba(255,255,255,0.45);font-size:0.86rem}

/* ===== ENVELOPE ===== */
.envelope-container {
  position: fixed;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%) scale(0);
  width: 320px; height: 220px;
  perspective: 1000px;
  transition: transform 0.6s ease;
  z-index: 999;
}
.envelope-container.show { transform: translate(-50%, -50%) scale(1); }

.envelope {
  width: 100%; height: 100%;
  position: relative;
  transform-style: preserve-3d;
}

.envelope-body {
  position: absolute;
  bottom: 0;
  width: 100%; height: 100%;
  background: linear-gradient(to bottom right,#ff6b9a,#ff2a75);
  border-radius: 8px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.4);
  overflow: hidden;
  z-index: 1;
}

.envelope-flap {
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 50%;
  background: linear-gradient(to bottom right,#ff94b5,#ff6b9a);
  clip-path: polygon(0 0, 100% 0, 50% 100%);
  transform-origin: top;
  z-index: 3;
  transition: transform 1s ease-in-out;
  backface-visibility: hidden;
}

.envelope.open .envelope-flap { transform: rotateX(-180deg); }

/* ⭐ SCROLLABLE POP-UP LETTER */
.letter {
  position: fixed;
  top: 50%; left: 50%;
  transform: translate(-50%, -50%) scale(0.5);
  width: 280px;
  background: #fff;color:#000;
  border-radius: 10px;padding: 20px;
  font-size: 0.95rem;
  box-shadow: 0 0 20px rgba(255, 107, 154, 0.6);
  text-align: left;
  line-height: 1.6;
  opacity: 0;
  z-index: 1000;
  transition: all 0.8s ease;

  max-height: 260px;      /* ⭐ scroll height */
  overflow-y: auto;       /* ⭐ enable scroll */
}

/* scrollbar for pop-up message */
.letter::-webkit-scrollbar { width: 6px; }
.letter::-webkit-scrollbar-thumb {
  background: rgba(255,107,154,0.6);
  border-radius: 10px;
}

.letter.show {
  opacity: 1;
  transform: translate(-50%, -50%) scale(1);
}

/* Floating hearts */
.heart {
  position: fixed;
  bottom: 0;
  width: 16px; height: 16px;
  background: pink;
  transform: rotate(45deg);
  animation: floatUp 4s ease-in infinite;
  z-index: 0;
}
.heart::before, .heart::after {
  content: '';
  position: absolute;
  width: 16px; height: 16px;
  background: pink;
  border-radius: 50%;
}
.heart::before { top: -8px; left: 0; }
.heart::after { left: -8px; top: 0; }

@keyframes floatUp {
  0% {transform:translateY(0) rotate(45deg); opacity:1;}
  100% {transform:translateY(-400px) rotate(45deg); opacity:0;}
}

.example {
    display: grid;
    transition: all .5s;
    user-select: none;
    background: linear-gradient(to bottom, white, black);
}


</style>
</head>
<body>
<audio id="mySong" src="thal2.mp3" autoplay></audio>
<div class="card">
  <div class="split">
    <div class="greeting">
      <h1>Hello, love!!  — <span style="color:var(--accent)">Happy 18th birthday enjoy your day love iloveyou🎈🎂 ❤️</span></h1>
      <div class="subtitle">A little message for you okay?✨</div>
      <div class="message" id="longmsg">Hi lovelove, today isn’t just another day — it’s your day. The day the world became brighter, more beautiful, and more meaningful because you were born. Happy 18th birthday to the most amazing girl in my life, the one who owns my heart completely. Eighteen years ago, someone truly special came into this world someone who would one day become my everything. And now that day has come, and I get to stand beside you as you step into adulthood. I can’t even put into words how proud, grateful, and happy I am to see the person you’ve become. You’re not just growing older, my love you’re growing more beautiful inside and out, wiser, stronger, and even more extraordinary. You have no idea how much you mean to me. You’ve brought light into my darkest days, laughter into my quiet moments, and comfort into my storms. Every time I look at you, I see the reason I smile, the reason I keep going, and the reason I believe in love. You’ve changed my life in so many ways — your kindness, your patience, your love, and your understanding have made me a better person. You’ve always been someone who cares deeply, who loves purely, and who gives her all to the people she loves. You have this rare kind of soul gentle but strong, soft but brave, simple but full of magic. You’re not just beautiful because of how you look, but because of who you are your heart, your thoughts, your dreams, your laughter, your strength, your love. Everything about you amazes me. Now that you’re 18, a new chapter of your life begins one filled with dreams, challenges, adventures, and countless memories waiting to be made. I know that sometimes life can be unpredictable, but please remember that you are capable of anything. You are destined for great things, my love. Don’t ever doubt yourself, because I’ve seen the fire in your heart, the determination in your eyes, and the courage in your soul. I’ll always be here not just as your boyfriend, but as your biggest supporter, your number one fan, your safe place, and your partner in everything. I’ll celebrate every win with you, hold your hand through every challenge, and remind you how incredible you are whenever you forget. You’ll never have to face this world alone, because I’ll be right here cheering you on, loving you endlessly, and believing in you always.

  </div>
      <div class="controls">
        <button id="surpriseBtn">Another message</button>
        <button onclick="playSong()">Play Song</button>
        <button>My Question</button>
        <button id="loveBtn">Love</button>
      </div>
      <footer>Happy birthday!!</footer>
    </div>
    <aside class="side photo">
      <img id="mainPhoto" src="image.png" alt="Couple photo">
      <div class="caption">Look, you're so beautiful ✨</div>
    </aside>
  </div>
</div>

<!-- Envelope -->
<div class="envelope-container" id="envContainer">
  <div class="envelope" id="envelope">
    <div class="envelope-body"></div>
    <div class="envelope-flap"></div>
  </div>
</div>

<!-- Floating letter -->
<div class="letter" id="letterText"></div>

<script>
const photos=["image copy.png","image copy 2.png","image copy 3.png","image copy 4.png",];
let index=0;
const mainPhoto=document.getElementById('mainPhoto');
setInterval(()=>{
  index=(index+1)%photos.length;
  mainPhoto.style.opacity=0;
  setTimeout(()=>{mainPhoto.src=photos[index];mainPhoto.style.opacity=1;},1000);
},4000);

const envContainer=document.getElementById('envContainer');
const envelope=document.getElementById('envelope');
const letter=document.getElementById('letterText');

document.getElementById('surpriseBtn').addEventListener('click',()=>{
  letter.textContent="You’ve given me so many reasons to smile. I still remember the first time I fell for you that moment when everything just felt right, when your voice became my favorite sound, and your name became my favorite word. Since then, every moment with you has been something I’ll always treasure. You’ve made my ordinary days extraordinary. Even your smallest gestures a text, a laugh, a hug, a look mean everything to me. You are my sunshine, my peace, my happiness, my inspiration, and my reason for everything. When I think of my future, I see you there laughing, smiling, still holding my hand the way you do now. I don’t need fancy things; I just need you  because with you, I already have everything I could ever wish for. So on this special day, I want you to know how deeply loved you are. Not just by me, but by everyone whose lives you’ve touched. You deserve to be celebrated, to be adored, and to be reminded of how truly special you are. You are one of a kind no one could ever replace you, and no words could ever fully express how much I love you. As you blow out your candles today, I hope you wish for something beautiful because that’s what you deserve. I hope this year brings you happiness, success, peace, and endless love. And no matter where life takes you, please remember that I’ll always be here, loving you, supporting you, and walking beside you through it all. Thank you for being my greatest blessing. Thank you for loving me even when I’m not perfect. Thank you for making me believe that real love exists. I’ll never stop choosing you not today, not tomorrow, not ever. You are my forever, my heart, my everything. Happy Happy 18th birthday, my love. Here’s to your new chapter, a chapter filled with growth, happiness, and love. I’m so proud of you, and I’ll keep loving you more and more every single day. You’ll always be my greatest story, my favorite person, and the most beautiful part of my life.";

  envContainer.classList.add('show');
  setTimeout(()=> envelope.classList.add('open'), 3000);
  setTimeout(()=>{
    letter.classList.add('show');
    spawnHearts();
  }, 1300);

  // Hide everything after 7 seconds
  setTimeout(()=>{
    letter.classList.remove('show');
    envelope.classList.remove('open');
    envContainer.classList.remove('show');
  }, 20000);
});

function playSong(){document.getElementById("mySong").play();}
document.getElementById('loveBtn').addEventListener('click',()=>{window.location.href='meme.html';})
document.querySelector('button:nth-child(3)').addEventListener('click', function() {
    window.open('https://forms.gle/NK3LMCBYFLVt6vfv5', '_blank');
});

function spawnHearts(){
  for(let i=0;i<15;i++){
    const heart=document.createElement('div');
    heart.className='heart';
    heart.style.left=Math.random()*window.innerWidth+'px';
    heart.style.animationDuration=(3+Math.random()*2)+'s';
    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),4000);
  }
}
</script>
</body>

