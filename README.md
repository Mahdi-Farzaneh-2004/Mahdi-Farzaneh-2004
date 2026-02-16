<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mahdi Farzaneh</title>

<style>
/* ---------- RESET ---------- */
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: 'Segoe UI', Tahoma, sans-serif;
}

body{
    background: linear-gradient(135deg,#0f172a,#020617);
    color:white;
    overflow-x:hidden;
}

/* ---------- NAV ---------- */
nav{
    position:fixed;
    width:100%;
    padding:20px 40px;
    background:rgba(0,0,0,0.3);
    backdrop-filter: blur(10px);
    display:flex;
    justify-content:space-between;
    z-index:1000;
}

nav h2{
    color:#38bdf8;
}

nav a{
    color:white;
    text-decoration:none;
    margin-left:20px;
    transition:.3s;
}
nav a:hover{
    color:#38bdf8;
}

/* ---------- HERO ---------- */
.hero{
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
}

.hero h1{
    font-size:60px;
    margin-bottom:10px;
}

.typing{
    font-size:26px;
    color:#38bdf8;
    height:35px;
}

/* ---------- SECTION ---------- */
section{
    padding:100px 15%;
}

.card{
    background:rgba(255,255,255,0.05);
    padding:30px;
    border-radius:12px;
    backdrop-filter: blur(10px);
    margin-top:30px;
    transition:.4s;
}

.card:hover{
    transform:translateY(-10px);
    box-shadow:0 10px 30px rgba(0,0,0,0.5);
}

/* ---------- SKILLS ---------- */
.skills{
    display:flex;
    flex-wrap:wrap;
    gap:15px;
}

.skill{
    background:#38bdf8;
    padding:10px 20px;
    border-radius:50px;
    color:black;
    font-weight:bold;
}

/* ---------- CONTACT ---------- */
.contact a{
    display:block;
    margin-top:10px;
    color:#38bdf8;
    text-decoration:none;
}

/* ---------- SCROLL ANIMATION ---------- */
.hidden{
    opacity:0;
    transform:translateY(40px);
    transition:1s;
}
.show{
    opacity:1;
    transform:translateY(0);
}

/* ---------- FOOTER ---------- */
footer{
    text-align:center;
    padding:40px;
    opacity:.7;
}
</style>
</head>

<body>

<nav>
    <h2>Mahdi</h2>
</nav>

<!-- HERO -->
<div class="hero">
    <h1>Mahdi Farzaneh</h1>
    <div class="typing"></div>
</div>

<!-- ABOUT -->
<section class="hidden">
    <h2>About Me</h2>
    <div class="card">
        <p>
        I am passionate about programming, artificial intelligence, and data analysis.
        I love learning new technologies and building real-world projects.
        My goal is continuous growth and creating smart solutions that make life easier.
        </p>
    </div>
</section>

<!-- SKILLS -->
<section class="hidden">
    <h2>Skills</h2>
    <div class="card skills">
        <div class="skill">Python</div>
        <div class="skill">Artificial Intelligence</div>
        <div class="skill">Data Analysis</div>
        <div class="skill">Power BI</div>
        <div class="skill">HTML</div>
        <div class="skill">CSS</div>
    </div>
</section>

<!-- CONTACT -->
<section class="hidden">
    <h2>Contact</h2>
    <div class="card contact">
        <a href="mailto:farzanehmahdi2004@gmail.com">Email Me</a>
        <a href="https://www.linkedin.com/in/mahdi-farzaneh-8197aa379" target="_blank">LinkedIn Profile</a>
    </div>
</section>

<footer>
Always learning • Always building • Always improving
</footer>

<script>

/* ---------- TYPING EFFECT ---------- */
const text = [
"Computer Science Student",
"Python Developer",
"AI Enthusiast"
];

let i=0;
let j=0;
let current="";
let isDeleting=false;

function type(){
    const el=document.querySelector(".typing");
    current=text[i];

    if(isDeleting){
        el.textContent=current.substring(0,j--);
        if(j<0){
            isDeleting=false;
            i=(i+1)%text.length;
        }
    }else{
        el.textContent=current.substring(0,j++);
        if(j>current.length){
            isDeleting=true;
            setTimeout(type,1200);
            return;
        }
    }
    setTimeout(type,isDeleting?40:80);
}
type();

/* ---------- SCROLL ANIMATION ---------- */
const observer=new IntersectionObserver(entries=>{
    entries.forEach(entry=>{
        if(entry.isIntersecting){
            entry.target.classList.add("show");
        }
    });
});

document.querySelectorAll(".hidden").forEach(el=>observer.observe(el));

</script>

</body>
</html>
