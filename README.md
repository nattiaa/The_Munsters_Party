<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halloween Party Invite</title>
    <style>
        body {
            margin: 0;
            overflow-x: hidden; /* Prevent horizontal scrolling */
            background-image: url('morado.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: 2;
            margin: 0;
            height: 100vh;
            color: white;
            font-family: american typewriter, serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh; /* Allow for vertical scrolling */
            text-align: center;
            padding: 20px;
        }
        header {
            position: relative;
            padding: 20px 0;
            z-index: 1;
        }
        .bat {
            position: absolute;
            width: 90px;
            height: 90px;
            background-image: url('ba.png'); /* Replace with your bat image */
            background-size: cover;
            animation: fly 10s linear infinite;
        }
        @keyframes fly {
            0% { transform: translateY(100vh) translateX(-100vw); }
            50% { transform: translateY(-100vh) translateX(100vw); }
            100% { transform: translateY(100vh) translateX(-100vw); }
        }
        .content {
            position: relative;
            z-index: 1;
            padding: 10px; /* Added padding for spacing */
        }
        h1 {
            font-size: 2.5em;
            margin: 10px 0;
            font-family: american typewriter, serif;
            color:rgb(160, 255, 45)
        }
        h2 {
            font-size: 1.5em;
            margin: 10px 0;
        }
        p {
            font-size: 1.1em;
            margin: 10px 0;
            max-width: 600px;
        }
        img {
            width: 80%; /* Responsive image */
            max-width: 400px;
            margin: 20px 0;
        }
        .buttons {
            position: relative; /* Changed to relative */
            margin: 20px 0;
            z-index: 1;
            width: calc(100% - 40px);
        }
        .button {
            background-color: rgb(0, 249, 0);
            color: black;
            border: none;
            padding: 15px 25px;
            margin: 10px;
            font-size: 25px !important;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s;
            display: inline-block;
            width: calc(100% - 40px);
            max-width: 300px;
            font-family: american typewriter, serif
        }
        .button:hover {
            background-color: rgb(0, 0, 0);
            color: white
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 2.5em;
            }
            h2 {
                font-size: 1.5em;
            }
            h3 {
                font-size: 2em;
            }
            }
            .button {
                font-size: 14px;
                padding: 12px 20px;
            }
        
    </style>
</head>
<body>

<header>
    <h2>Estás invitado a nuestra fiesta de disfraces en:</h2>
    <img src="munsters.png" alt="The Munsters">
    <h1>Family House!!</h1>
</header>

<div class="content">
    <h1>SIN DISFRAZ NO HAY ENTRADA!</h1>
    <h2>Únete a nosotros para una noche de Halloween llena de diversión! </h2>
    <p>*habrá un premio al mejor (o mas divertido) disfraz. Por favor usar disfraces aptos para todas las edades.</p>
    <H2><u>Hora: 7:00p.m </u></H2>
    <p>No olvides ser puntual y venir listo para pasarla bien!</p>
    <img src="house.png" alt="Bat Image"> <!-- Replace with your image -->
</div>

<div class="buttons">
    <a href="https://wa.link/m6rw7f" class="button">Confirmar asistencia</a>
    <a href="https://maps.app.goo.gl/Na24VW78258pcXUq7" class="button">Ver ubicación</a>
</div>

<script>
    function createBats(numBats) {
        for (let i = 0; i < numBats; i++) {
            const bat = document.createElement('div');
            bat.className = 'bat';
            bat.style.left = Math.random() * 100 + 'vw';
            bat.style.top = Math.random() * 100 + 'vh';

            const duration = Math.random() * 3 + 3; // Between 3 and 6 seconds
            bat.style.animationDuration = duration + 's';

            const endX = Math.random() * 200 - 100; // Between -100 and 100vw
            const endY = Math.random() * 200 - 100; // Between -100 and 100vh

            const animationName = `fly-${i}`; // Unique animation name for each bat
            bat.style.animationName = animationName;
            document.body.appendChild(bat);

            const styleSheet = document.styleSheets[0];
            styleSheet.insertRule(`
                @keyframes ${animationName} {
                    0% { transform: translate(0, 0); }
                    100% { transform: translate(${endX}vw, ${endY}vh); }
                }
            `, styleSheet.cssRules.length);

            
        }
    }

    // Create 50 bats flying at once when the page loads
    window.onload = () => {
        createBats(50);
    };
</script>

</body>
</html>
