# San-Valent-n
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>¿Quieres ser mi San Valentín?</title>

<style>
    body {
        margin: 0;
        padding: 0;
        background: linear-gradient(135deg, #ff4e50, #fc913a);
        font-family: Arial, sans-serif;
        text-align: center;
        color: white;
        overflow: hidden;
    }

    h1 {
        margin-top: 100px;
        font-size: 3em;
        animation: aparecer 2s ease-in-out;
    }

    @keyframes aparecer {
        from { opacity: 0; transform: scale(0.5); }
        to { opacity: 1; transform: scale(1); }
    }

    button {
        padding: 15px 30px;
        font-size: 1.2em;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        margin: 20px;
        transition: 0.3s;
    }

    .si {
        background-color: #fff;
        color: #ff4e50;
    }

    .no {
        background-color: #333;
        color: white;
        position: absolute;
    }

    .corazon {
        position: absolute;
        color: red;
        font-size: 20px;
        animation: flotar 5s linear infinite;
    }

    @keyframes flotar {
        0% { transform: translateY(100vh); opacity: 1; }
        100% { transform: translateY(-10vh); opacity: 0; }
    }
</style>
</head>

<body>

<h1>¿Quieres ser mi San Valentín? 💖</h1>

<button class="si" onclick="aceptar()">Sí ❤️</button>
<button class="no" onmouseover="moverBoton(this)">No 😢</button>

<script>
function aceptar() {
    document.body.innerHTML = `
        <h1>¡Sabía que dirías que sí! 💕</h1>
        <p>Te quiero muchísimo ❤️</p>
    `;
}

function moverBoton(boton) {
    boton.style.top = Math.random() * window.innerHeight + "px";
    boton.style.left = Math.random() * window.innerWidth + "px";
}

function crearCorazon() {
    const corazon = document.createElement("div");
    corazon.classList.add("corazon");
    corazon.innerHTML = "❤️";
    corazon.style.left = Math.random() * 100 + "vw";
    corazon.style.fontSize = Math.random() * 20 + 10 + "px";
    document.body.appendChild(corazon);

    setTimeout(() => {
        corazon.remove();
    }, 5000);
}

setInterval(crearCorazon, 300);
</script>

</body>
</html>
