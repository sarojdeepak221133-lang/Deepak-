index.html
manifest.json
sw.js
logo.svg
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#0758c9">

<title>Study Master 📚</title>

<style>
*{box-sizing:border-box;margin:0;padding:0}

body{
  font-family:Arial,sans-serif;
  background:#f4f7fb;
  color:#172033;
  transition:.3s;
}

header{
  background:linear-gradient(135deg,#087cf0,#172d8f);
  color:white;
  padding:20px 16px;
  text-align:center;
  border-radius:0 0 28px 28px;
}

.logo{
  width:105px;
  height:105px;
  margin:auto;
  display:block;
  border-radius:25px;
  background:white;
  padding:5px;
  box-shadow:0 5px 20px #0004;
}

header h1{
  margin-top:10px;
  font-size:27px;
}

header p{
  margin-top:5px;
}

.search{
  width:100%;
  padding:13px;
  margin-top:17px;
  border:0;
  border-radius:12px;
  outline:none;
  font-size:15px;
}

.install{
  margin-top:10px;
  width:100%;
  background:#facc15;
  color:#111827;
  font-weight:bold;
  display:none;
}

main{
  max-width:900px;
  margin:auto;
  padding:18px 16px 100px;
}

section{display:none}
section.active{display:block}

h2{
  margin:10px 0 15px;
}

.grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:13px;
}

.card{
  background:white;
  padding:18px;
  border-radius:17px;
  margin-bottom:13px;
  box-shadow:0 4px 15px #00000012;
}

.card h3{
  margin:8px 0;
}

.icon{
  width:42px;
  height:42px;
}

button{
  border:0;
  background:#2563eb;
  color:white;
  padding:11px 16px;
  border-radius:10px;
  margin:4px;
  cursor:pointer;
  font-weight:bold;
}

.secondary{
  background:#e8eefb;
  color:#17428f;
}

textarea{
  width:100%;
  min-height:180px;
  padding:12px;
  border:1px solid #ddd;
  border-radius:12px;
  resize:vertical;
}

.progress{
  width:100%;
  height:13px;
  background:#ddd;
  border-radius:20px;
  overflow:hidden;
  margin:12px 0;
}

.bar{
  height:100%;
  width:0;
  background:#2563eb;
}

.timer{
  text-align:center;
}

.time{
  font-size:48px;
  font-weight:bold;
  margin:15px;
}

.quiz-option{
  display:block;
  width:100%;
  text-align:left;
  background:#edf3ff;
  color:#17428f;
  margin:7px 0;
}

.bottom{
  position:fixed;
  left:0;
  right:0;
  bottom:0;
  z-index:50;
  background:white;
  display:flex;
  justify-content:space-around;
  padding:7px 2px;
  box-shadow:0 -3px 15px #0002;
}

.nav{
  background:none;
  color:#333;
  font-size:11px;
  padding:5px;
  margin:0;
}

.nav svg{
  display:block;
  margin:auto;
}

.dark{
  background:#101827;
  color:white;
}

.dark .card,
.dark .bottom{
  background:#1b2638;
  color:white;
}

.dark .nav{
  color:white;
}

.dark textarea,
.dark .search{
  background:#263246;
  color:white;
}

.dark .quiz-option{
  background:#263b60;
  color:white;
}

@media(min-width:700px){
  .grid{
    grid-template-columns:repeat(4,1fr);
  }
}
</style>
</head>

<body>

<!-- ================= HEADER ================= -->

<header>

<!-- SVG STUDY MASTER LOGO -->

<svg class="logo" viewBox="0 0 512 512">

<defs>
<linearGradient id="logoColor" x1="0" y1="0" x2="1" y2="1">
<stop stop-color="#087cf0"/>
<stop offset="1" stop-color="#172d8f"/>
</linearGradient>
</defs>

<rect width="512" height="512"
rx="100"
fill="url(#logoColor)"/>

<!-- Graduation Cap -->

<polygon
points="256,70 430,145 256,220 82,145"
fill="#172d8f"/>

<path
d="M160 180V250
Q256 285 352 250V180"
fill="#172d8f"/>

<line x1="420" y1="140"
x2="420" y2="225"
stroke="#facc15"
stroke-width="13"/>

<circle cx="420" cy="235"
r="17"
fill="#facc15"/>

<!-- Book -->

<path
d="M80 260
Q170 220 256 275
Q342 220 432 260
V405
Q340 365 256 420
Q172 365 80 405Z"
fill="white"/>

<line x1="256" y1="275"
x2="256" y2="418"
stroke="#087cf0"
stroke-width="10"/>

<!-- Growth -->

<path
d="M230 370
Q220 315 250 285"
fill="none"
stroke="#087cf0"
stroke-width="18"
stroke-linecap="round"/>

<path
d="M250 340
Q320 325 350 270"
fill="none"
stroke="#16a34a"
stroke-width="18"
stroke-linecap="round"/>

<text
x="256"
y="475"
text-anchor="middle"
font-family="Arial"
font-size="38"
font-weight="bold"
fill="white">
Study Master
</text>

</svg>

<h1>Study Master 📚</h1>
<p>Learn • Practice • Grow 🚀</p>

<input
id="search"
class="search"
placeholder="🔍 Search..."
oninput="searchData()">

<button id="installBtn"
class="install">
📱 Install Study Master App
</button>

</header>


<!-- ================= MAIN ================= -->

<main>

<!-- HOME -->

<section id="home" class="active">

<h2>🏠 Home</h2>

<div class="grid">

<div class="card">
<div class="icon">📚</div>
<h3>Subjects</h3>
<p>अपने विषय पढ़ें</p>
</div>

<div class="card">
<div class="icon">📝</div>
<h3>Notes</h3>
<p>अपने notes save करें</p>
</div>

<div class="card">
<div class="icon">❓</div>
<h3>Quiz</h3>
<p>Quiz और Score</p>
</div>

<div class="card">
<div class="icon">⏱️</div>
<h3>Study Timer</h3>
<p>Focus से पढ़ें</p>
</div>

</div>

<div class="card">

<h3>📊 आपका Progress</h3>

<div class="progress">
<div id="homeBar" class="bar"></div>
</div>

<p id="homeProgress"></p>

</div>

</section>


<!-- SUBJECTS -->

<section id="subjects">

<h2>📚 Subjects</h2>

<div class="grid">

<div class="card searchable">
<div class="icon">🧪</div>
<h3>Chemistry</h3>
<p>Basic Chemistry</p>
</div>

<div class="card searchable">
<div class="icon">🧬</div>
<h3>Biology</h3>
<p>Cell & Human Body</p>
</div>

<div class="card searchable">
<div class="icon">💊</div>
<h3>Pharmacy</h3>
<p>Pharmacy Notes</p>
</div>

<div class="card searchable">
<div class="icon">📐</div>
<h3>Mathematics</h3>
<p>Formula & Practice</p>
</div>

</div>

</section>


<!-- NOTES -->

<section id="notes">

<h2>📝 Notes</h2>

<div class="card">

<h3>💾 My Notes</h3>

<textarea
id="notesBox"
placeholder="यहाँ अपने notes लिखें...">
</textarea>

<br>

<button onclick="saveNotes()">
💾 Save Notes
</button>

<button class="secondary"
onclick="clearNotes()">
🗑️ Clear
</button>

<p id="saveMessage"></p>

</div>

<div class="card searchable">

<h3>🧬 Cell</h3>

<p>
Cell जीवों की संरचनात्मक और
क्रियात्मक इकाई है।
</p>

</div>

<div class="card searchable">

<h3>🫀 Anatomy</h3>

<p>
Anatomy शरीर की संरचना
का अध्ययन है।
</p>

</div>

</section>


<!-- QUIZ -->

<section id="quiz">

<h2>❓ Quiz + Score</h2>

<div class="card">

<div id="question"></div>

<div id="options"></div>

<h3>
Score:
<span id="score">0</span>
</h3>

<br>

<button onclick="nextQuestion()">
➡️ Next
</button>

<button class="secondary"
onclick="resetQuiz()">
🔄 Reset
</button>

</div>

</section>


<!-- STUDY MATERIAL -->

<section id="material">

<h2>📖 Study Material</h2>

<div class="grid">

<div class="card">
<div class="icon">📄</div>
<h3>PDF Notes</h3>
<p>Important PDFs</p>
</div>

<div class="card">
<div class="icon">🎥</div>
<h3>Video Lectures</h3>
<p>Lecture Videos</p>
</div>

<div class="card">
<div class="icon">📋</div>
<h3>Question Papers</h3>
<p>Practice Papers</p>
</div>

<div class="card">
<div class="icon">📚</div>
<h3>Books</h3>
<p>Study Books</p>
</div>

</div>

</section>


<!-- TIMER -->

<section id="timer">

<h2>⏱️ Study Timer</h2>

<div class="card timer">

<div id="time" class="time">
25:00
</div>

<button onclick="startTimer()">
▶ Start
</button>

<button onclick="pauseTimer()">
⏸ Pause
</button>

<button class="secondary"
onclick="resetTimer()">
🔄 Reset
</button>

</div>

</section>


<!-- PROGRESS -->

<section id="progress">

<h2>📊 Progress</h2>

<div class="card">

<h3>Study Progress</h3>

<div class="progress">

<div id="progressBar"
class="bar">
</div>

</div>

<p id="progressText"></p>

<br>

<button onclick="addProgress()">
➕ Study Done
</button>

</div>

</section>

</main>


<!-- ================= BOTTOM NAV ================= -->

<nav class="bottom">

<button class="nav"
onclick="showPage('home')">

🏠<br>Home

</button>

<button class="nav"
onclick="showPage('subjects')">

📚<br>Subjects

</button>

<button class="nav"
onclick="showPage('notes')">

📝<br>Notes

</button>

<button class="nav"
onclick="showPage('quiz')">

❓<br>Quiz

</button>

<button class="nav"
onclick="showPage('timer')">

⏱️<br>Timer

</button>

<button class="nav"
onclick="darkMode()">

🌙<br>Dark

</button>

</nav>


<script>

/* ================= PAGE ================= */

function showPage(page){

document
.querySelectorAll("section")
.forEach(x=>{
x.classList.remove("active");
});

document
.getElementById(page)
.classList.add("active");

window.scrollTo(0,0);

}


/* ================= DARK MODE ================= */

function darkMode(){

document.body.classList.toggle("dark");

localStorage.setItem(
"dark",
document.body.classList.contains("dark")
);

}

if(
localStorage.getItem("dark")==="true"
){

document.body.classList.add("dark");

}


/* ================= NOTES SAVE ================= */

const notesBox=
document.getElementById("notesBox");

notesBox.value=
localStorage.getItem("myNotes") || "";

function saveNotes(){

localStorage.setItem(
"myNotes",
notesBox.value
);

document.getElementById(
"saveMessage"
).innerHTML=
"✅ Notes Saved Successfully!";

}

function clearNotes(){

notesBox.value="";

localStorage.removeItem("myNotes");

document.getElementById(
"saveMessage"
).innerHTML=
"🗑️ Notes Deleted";

}


/* ================= PROGRESS ================= */

let progress=
Number(
localStorage.getItem("studyProgress")
|| 0
);

function updateProgress(){

document.getElementById(
"progressBar"
).style.width=
progress+"%";

document.getElementById(
"homeBar"
).style.width=
progress+"%";

document.getElementById(
"progressText"
).innerText=
progress+"% Complete 🎉";

document.getElementById(
"homeProgress"
).innerText=
progress+"% Complete 🎉";

localStorage.setItem(
"studyProgress",
progress
);

}

function addProgress(){

progress+=10;

if(progress>100){
progress=100;
}

updateProgress();

}

updateProgress();


/* ================= TIMER ================= */

let seconds=1500;

let timer=null;

function updateTimer(){

let minutes=
Math.floor(seconds/60);

let sec=
seconds%60;

document.getElementById(
"time"
).innerText=

String(minutes)
.padStart(2,"0")
+
":"
+
String(sec)
.padStart(2,"0");

}

function startTimer(){

if(timer) return;

timer=setInterval(()=>{

if(seconds>0){

seconds--;

updateTimer();

}

else{

pauseTimer();

alert(
"🎉 Study Time Complete!"
);

}

},1000);

}

function pauseTimer(){

clearInterval(timer);

timer=null;

}

function resetTimer(){

pauseTimer();

seconds=1500;

updateTimer();

}


/* ================= QUIZ ================= */

const quiz=[

{
question:"Cell क्या है?",
options:[
"शरीर की structural unit",
"एक दवा",
"एक हड्डी"
],
answer:0
},

{
question:"Anatomy किसका अध्ययन है?",
options:[
"शरीर की संरचना",
"शरीर के कार्य",
"दवाओं का स्वाद"
],
answer:0
},

{
question:"Study Timer किसके लिए है?",
options:[
"Focus Study",
"गेम",
"Music"
],
answer:0
}

];

let questionNumber=0;

let score=0;


function loadQuiz(){

let q=
quiz[questionNumber];

document.getElementById(
"question"
).innerHTML=
"<h3>"+
(q.question)+
"</h3>";

let html="";

q.options.forEach(
(option,index)=>{

html+=
`
<button
class="quiz-option"
onclick="checkAnswer(${index})">
${option}
</button>
`;

});

document.getElementById(
"options"
).innerHTML=html;

}


function checkAnswer(index){

let q=
quiz[questionNumber];

if(index===q.answer){

score++;

document.getElementById(
"score"
).innerText=
score;

alert("✅ सही उत्तर!");

}else{

alert("❌ गलत उत्तर!");

}

}

function nextQuestion(){

questionNumber++;

if(
questionNumber>=quiz.length
){

questionNumber=0;

}

loadQuiz();

}


function resetQuiz(){

questionNumber=0;

score=0;

document.getElementById(
"score"
).innerText=0;

loadQuiz();

}

loadQuiz();


/* ================= SEARCH ================= */

function searchData(){

let search=
document.getElementById(
"search"
).value
.toLowerCase();

document
.querySelectorAll(".searchable")
.forEach(card=>{

if(
card.innerText
.toLowerCase()
.includes(search)
){

card.style.display="";

}else{

card.style.display="none";

}

});

}


/* ================= PWA INSTALL ================= */

let deferredPrompt;

window.addEventListener(
"beforeinstallprompt",
event=>{

event.preventDefault();

deferredPrompt=event;

document.getElementById(
"installBtn"
).style.display=
"block";

});


document.getElementById(
"installBtn"
).onclick=
async function(){

if(!deferredPrompt){

alert(
"Chrome menu से Add to Home Screen चुनें।"
);

return;

}

deferredPrompt.prompt();

await deferredPrompt.userChoice;

deferredPrompt=null;

};


/* ================= SERVICE WORKER ================= */

/*
  Full PWA install/offline के लिए
  hosting पर manifest.json और sw.js
  भी रखना बेहतर है।
*/

</script>

</body>
</html>
