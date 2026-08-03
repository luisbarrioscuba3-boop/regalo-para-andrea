# regalo-para-andrea
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Regalo para Andrea ❤️</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    height:100vh;
    overflow:hidden;
    display:flex;
    justify-content:center;
    align-items:center;
    background:radial-gradient(circle,#3b126e,#050014);
    font-family:'Segoe UI',sans-serif;
    color:white;
}

/* Estrellas */
.stars{
    position:absolute;
    width:100%;
    height:100%;
}

.star{
    position:absolute;
    background:white;
    width:3px;
    height:3px;
    border-radius:50%;
    animation:brillo 2s infinite alternate;
}

@keyframes brillo{
    from{opacity:.2;}
    to{opacity:1;}
}

/* Carta */
.carta{
    position:relative;
    z-index:5;
    width:90%;
    max-width:500px;
    text-align:center;
}

.sobre{
    width:260px;
    height:170px;
    background:#ff4f9a;
    margin:auto;
    border-radius:15px;
    cursor:pointer;
    display:flex;
    justify-content:center;
    align-items:center;
    box-shadow:0 0 30px #ff4f9a;
    transition:1s;
}

.sobre span{
    font-size:70px;
}

.mensaje{
    display:none;
    background:rgba(255,255,255,.12);
    padding:30px;
    border-radius:20px;
    backdrop-filter:blur(10px);
    box-shadow:0 0 30px #ff8bdc;
}

.mensaje h1{
    color:#ff9de8;
    font-size:2.5em;
}

.mensaje p{
    margin-top:20px;
    line-height:1.7;
    font-size:1.1em;
}

button{
    margin-top:25px;
    padding:14px 30px;
    border:0;
    border-radius:30px;
    background:#ff4f9a;
    color:white;
    font-size:18px;
    cursor:pointer;
}

/* Corazones */
.corazon{
    position:absolute;
    color:#ff6bb5;
    animation:subir 6s linear infinite;
}

@keyframes subir{
    from{
        transform:translateY(100vh);
        opacity:1;
    }
    to{
        transform:translateY(-100px);
        opacity:0;
    }
}

/* Fuegos */
.fuego{
    position:absolute;
    color:#ffd700;
    font-size:25px;
    animation:explota 2s linear forwards;
}

@keyframes explota{
    from{
        transform:scale(0);
        opacity:1;
    }
    to{
        transform:translate(var(--x),var(--y)) scale(2);
        opacity:0;
    }
}

</style>
</head>

<body>

<div class="stars" id="stars"></div>

<div class="carta">

<div class="sobre" onclick="abrir()">
<span>💌</span>
</div>

<div class="mensaje" id="mensaje">

<h1>🌌 Andrea ❤️</h1>

<p>
Hoy quiero regalarte un pequeño universo,
porque para mí eres una estrella única. ✨<br><br>

Gracias por llenar mi vida de momentos hermosos.
Aunque existan millones de galaxias,
mi lugar favorito siempre será donde estés tú. 💖<br><br>

Te quiero mucho, Andrea. 🌹
</p>

<button onclick="fiesta()">✨ Celebrar nuestro amor ✨</button>

</div>

</div>


<script>

// Crear estrellas
for(let i=0;i<200;i++){
let estrella=document.createElement("div");
estrella.className="star";
estrella.style.left=Math.random()*100+"%";
estrella.style.top=Math.random()*100+"%";
estrella.style.animationDuration=(1+Math.random()*3)+"s";
document.getElementById("stars").appendChild(estrella);
}


// Abrir carta
function abrir(){
document.querySelector(".sobre").style.display="none";
document.getElementById("mensaje").style.display="block";
}


// Corazones
setInterval(()=>{
let c=document.createElement("div");
c.className="corazon";
c.innerHTML="❤️";
c.style.left=Math.random()*100+"vw";
c.style.fontSize=(15+Math.random()*30)+"px";
document.body.appendChild(c);

setTimeout(()=>c.remove(),6000);

},300);


// Fuegos artificiales
function fiesta(){

for(let i=0;i<40;i++){

let f=document.createElement("div");
f.className="fuego";
f.innerHTML="✨";

f.style.left="50%";
f.style.top="50%";

f.style.setProperty("--x",
(Math.random()*600-300)+"px");

f.style.setProperty("--y",
(Math.random()*600-300)+"px");

document.body.appendChild(f);

setTimeout(()=>f.remove(),2000);

}

}

</script>

</body>
</html>
