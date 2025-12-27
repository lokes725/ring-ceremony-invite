<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Ring Ceremony Invitation</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box}
body{
  background:radial-gradient(circle at top,#2b1055,#000);
  color:#fff;
  font-family:'Poppins',sans-serif;
  overflow:hidden;
}
section{
  min-height:100vh;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  text-align:center;
}

/* LOGO */
.logo{
  font-family:'Great Vibes',cursive;
  font-size:64px;
  color:gold;
  text-shadow:0 0 35px orange;
}

/* BUTTONS */
.btn{
  margin-top:20px;
  padding:12px 34px;
  border:none;
  border-radius:40px;
  background:linear-gradient(45deg,gold,orange);
  font-size:18px;
  cursor:pointer;
}
.btn:hover{transform:scale(1.1)}

.nav-btns{margin-top:30px;display:flex;gap:20px}

/* INPUT */
.input-name input{
  padding:10px 18px;
  font-size:20px;
  border-radius:10px;
  border:none;
  margin-top:20px;
}

/* LETTER DROP */
.letter span{
  display:inline-block;
  opacity:0;
  transform:translateY(-140px);
  animation:drop 0.8s forwards;
}
@keyframes drop{
  to{opacity:1;transform:translateY(0)}
}

/* COUPLE */
.couple{display:flex;gap:50px;margin:40px 0}
.avatar{
  width:150px;height:150px;border-radius:50%;
  background:linear-gradient(135deg,#ff5fa2,#8e2de2);
  display:flex;align-items:center;justify-content:center;
  font-size:65px;
  animation:float 3s infinite;
}
@keyframes float{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-20px)}
}

/* NAMES */
.names{
  font-family:'Great Vibes',cursive;
  font-size:56px;
}

/* DETAILS */
.details{font-size:22px;margin:8px}

/* KRISHNA */
.krishna{
  width:190px;height:190px;border-radius:50%;
  background:radial-gradient(circle,#00c6ff,#0072ff);
  display:flex;align-items:center;justify-content:center;
  font-size:75px;
  box-shadow:0 0 40px #00c6ff;
}
.radhe{
  font-family:'Great Vibes',cursive;
  font-size:44px;
  color:gold;
}

/* CANVAS */
canvas{
  position:fixed;
  inset:0;
  pointer-events:none;
  z-index:5;
}

/* PHOOL JHADI */
.spark{
  position:absolute;
  width:5px;height:5px;border-radius:50%;
  background:radial-gradient(circle,#fff,gold,orange);
  animation:sparkFall .9s linear forwards;
  z-index:15;
}
@keyframes sparkFall{
  to{transform:translateY(180px) scale(0);opacity:0}
}

/* ROCKET */
.rocket{
  position:absolute;
  width:4px;height:22px;
  background:linear-gradient(to top,orange,yellow);
  box-shadow:0 0 15px orange;
  animation:rocketRise 1.4s linear forwards;
  z-index:15;
}
@keyframes rocketRise{
  to{transform:translateY(-450px);opacity:0}
}

/* SKY SHOTS */
.shoot{
  position:absolute;
  width:4px;
  height:30px;
  background:linear-gradient(to top,cyan,yellow,red);
  box-shadow:0 0 20px cyan,0 0 35px yellow;
  animation:shootRise 1.6s linear forwards;
  z-index:20;
}
@keyframes shootRise{
  to{transform:translateY(-550px);opacity:0}
}

/* RAINBOW TEXT */
.rainbow span{
  background:linear-gradient(to right,red,orange,yellow,green,cyan,blue,violet);
  -webkit-background-clip:text;
  color:transparent;
}
</style>
</head>

<body>

<canvas id="fire"></canvas>

<section id="home">
  <div class="logo">💍 Ring Ceremony 💍</div>
  <button class="btn" onclick="nextSection('guestName')">Open Invitation</button>
</section>

<section id="guestName" style="display:none">
  <h2 class="letter">Enter Your Name</h2>
  <div class="input-name">
    <input id="guest" placeholder="Your Name">
    <button class="btn" onclick="submitGuestName()">Continue</button>
  </div>
</section>

<section id="welcome" style="display:none">
  <h1 class="letter" id="welcomeText">Welcome Dear Guest</h1>
  <p class="letter">We are delighted to invite you</p>
  <div class="couple">
    <div class="avatar">🤵</div>
    <div class="avatar">👰</div>
  </div>
  <div class="nav-btns">
    <button class="btn" onclick="prevSection('guestName')">Back</button>
    <button class="btn" onclick="nextSection('names')">Next</button>
  </div>
</section>

<section id="names" style="display:none">
  <h1 class="letter">Engagement Of</h1>
  <div class="names rainbow">
    <span>L</span><span>o</span><span>k</span><span>e</span><span>s</span><span>h</span>
    <span style="color:red">❤</span>
    <span>S</span><span>h</span><span>i</span><span>v</span><span>a</span><span>n</span><span>i</span>
  </div>
  <div class="nav-btns">
    <button class="btn" onclick="prevSection('welcome')">Back</button>
    <button class="btn" onclick="nextSection('details')">Next</button>
  </div>
</section>

<section id="details" style="display:none">
  <h1 class="letter">Venue & Schedule</h1>
  <div class="details letter">
    The Leela, 1 CBD, Maharaja Surajmal Marg, Near Yamuna Sports Complex, Shahdara, Delhi - 110032
  </div>
  <div class="details letter">23 February 2026</div>
  <div class="details letter">12:00 PM Onwards</div>
  <div class="nav-btns">
    <button class="btn" onclick="prevSection('names')">Back</button>
    <button class="btn" onclick="nextSection('blessing')">Next</button>
  </div>
</section>

<section id="blessing" style="display:none">
  <div class="krishna">🦚</div>
  <div class="radhe letter">Radhe Radhe</div>
</section>

<script>
/* 🔥 FIXED LETTER DROP WITH SPACE */
function splitLetters(){
  document.querySelectorAll(".letter").forEach(el=>{
    const text = el.innerText;
    el.innerHTML = "";
    text.split("").forEach((char,i)=>{
      if(char===" "){
        let sp=document.createElement("span");
        sp.innerHTML="&nbsp;";
        sp.style.display="inline-block";
        sp.style.width="14px";
        el.appendChild(sp);
      }else{
        let s=document.createElement("span");
        s.innerText=char;
        s.style.animationDelay=i*0.07+"s";
        el.appendChild(s);
      }
    });
  });
}

/* PHOOL JHADI */
setInterval(()=>{
  for(let i=0;i<25;i++){
    let s=document.createElement("div");
    s.className="spark";
    s.style.left=Math.random()*innerWidth+"px";
    s.style.top=Math.random()*innerHeight/2+"px";
    document.body.appendChild(s);
    setTimeout(()=>s.remove(),900);
  }
},120);

/* ROCKETS */
setInterval(()=>{
  let r=document.createElement("div");
  r.className="rocket";
  r.style.left=Math.random()*innerWidth+"px";
  r.style.bottom="0";
  document.body.appendChild(r);
  setTimeout(()=>r.remove(),1500);
},400);

/* SKY SHOTS */
setInterval(()=>{
  let s=document.createElement("div");
  s.className="shoot";
  s.style.left=Math.random()*innerWidth+"px";
  s.style.bottom="0";
  document.body.appendChild(s);
  setTimeout(()=>s.remove(),1600);
},300);

/* FIREWORK CANVAS */
const canvas=document.getElementById("fire");
const ctx=canvas.getContext("2d");
canvas.width=innerWidth;
canvas.height=innerHeight;
window.onresize=()=>{canvas.width=innerWidth;canvas.height=innerHeight;}
let parts=[];
function boom(){
  let x=Math.random()*canvas.width,y=Math.random()*canvas.height/2;
  for(let i=0;i<200;i++)
    parts.push({x,y,vx:Math.random()*10-5,vy:Math.random()*10-5,a:1,c:`hsl(${Math.random()*360},100%,60%)`});
}
function animate(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  parts.forEach(p=>{
    p.x+=p.vx;p.y+=p.vy;p.a-=0.01;
    ctx.globalAlpha=p.a;
    ctx.fillStyle=p.c;
    ctx.fillRect(p.x,p.y,3,3);
  });
  parts=parts.filter(p=>p.a>0);
  requestAnimationFrame(animate);
}
setInterval(boom,700);
animate();

/* NAV */
function nextSection(id){
  document.querySelectorAll("section").forEach(s=>s.style.display="none");
  document.getElementById(id).style.display="flex";
  splitLetters();
}
function prevSection(id){nextSection(id);}

/* GUEST NAME */
function submitGuestName(){
  const n=document.getElementById("guest").value.trim();
  if(!n) return alert("Enter name");
  let rainbow="";
  const c=["red","orange","yellow","green","cyan","blue","violet"];
  n.split("").forEach((l,i)=>rainbow+=`<span style="color:${c[i%c.length]}">${l}</span>`);
  document.getElementById("welcomeText").innerHTML="Welcome Dear "+rainbow;
  nextSection("welcome");
}
</script>

</body>
</html>
