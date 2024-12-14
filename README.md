<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Propuesta indecente</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom, #ff9a9e, #fad0c4);
            overflow: hidden;
        }

        #contenedor {
            text-align: center;
            z-index: 2;
        }

        h1 {
            font-size: 2.5rem;
            color: #fff;
            margin-bottom: 20px;
        }

        button {
            font-size: 1.5rem;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: transform 0.3s, background 0.3s;
        }

        button:hover {
            transform: scale(1.1);
        }

        .boton-si {
            background: #6bcf63;
            color: white;
        }

        .boton-si:hover {
            background: #55a64e;
        }

        .boton-no {
            background: #ff6b6b;
            color: white;
        }

        .boton-no:hover {
            background: #d45c5c;
        }

        .perrito {
            position: absolute;
            width: 100px;
            animation: flotar 3s infinite ease-in-out;
        }

        @keyframes flotar {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        .corazon {
            position: absolute;
            width: 50px;
            opacity: 0;
            animation: subir 4s infinite;
        }

        @keyframes subir {
            0% {
                transform: translateY(0) scale(1);
                opacity: 1;
            }
            100% {
                transform: translateY(-200px) scale(0.5);
                opacity: 0;
            }
        }

        #texto-extra {
            margin-top: 20px;
            font-size: 1.2rem;
            color: white;
            display: none;
        }
    </style>
</head>
<body>
    <div id="contenedor">
        <h1>¿Quieres ser mi novia?</h1>
        <button class="boton-si">Sí</button>
        <button class="boton-no" id="boton-no">No</button>
        <p id="texto-extra"></p>
    </div>

    <img src="https://i.imgur.com/LQ5KnXp.png" alt="perrito" class="perrito" style="top: 20%; left: 15%;">
    <img src="https://i.imgur.com/LQ5KnXp.png" alt="perrito" class="perrito" style="top: 40%; left: 75%;">

    <img src="https://i.imgur.com/vGyb6DQ.png" alt="corazon" class="corazon" style="top: 50%; left: 30%; animation-delay: 0s;">
    <img src="https://i.imgur.com/vGyb6DQ.png" alt="corazon" class="corazon" style="top: 60%; left: 60%; animation-delay: 1s;">

    <script>
        const botonNo = document.getElementById('boton-no');
        const textoExtra = document.getElementById('texto-extra');
        let intentos = 0;

        botonNo.addEventListener('click', () => {
            intentos++;

            if (intentos === 1) {
                textoExtra.style.display = 'block';
                textoExtra.textContent = '¿Estás segura?';
            } else if (intentos === 2) {
                textoExtra.textContent = '¿Estás totalmente segura?';
            } else {
                textoExtra.textContent = '¡Está bien! Pero me quedaré esperando. 🥺';
                botonNo.disabled = true;
            }
        });
    </script>
</body>
</html>
