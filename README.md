# San-Valent-n<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>¿Quieres ser mi San Valentín?</title>
    <style>
        body {
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        .card {
            background: white;
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            max-width: 350px;
            z-index: 2;
        }

        h1 {
            color: #e63946;
        }

        p {
            font-size: 18px;
            color: #333;
        }

        button {
            margin: 10px;
            padding: 10px 20px;
            border: none;
            border-radius: 10px;
            font-size: 16px;
            cursor: pointer;
            position: relative;
        }

        .yes {
            background-color: #e63946;
            color: white;
        }

        .no {
            background-color: #ccc;
        }

        .heart {
            position: absolute;
            bottom: -20px;
            color: #e63946;
            font-size: 20px;
            animation: floatUp 6s linear infinite;
            opacity: 0.8;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) scale(1);
                opacity: 0.8;
            }
            100% {
                transform: translateY(-120vh) scale(1.5);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="card">
        <h1>💖 Gaby 💖</h1>
        <p>Hay algo que quiero preguntarte</p>
        <p><strong>¿Quieres ser mi San Valentín?</strong></p>

        <button class="yes" onclick="alert('Sabía que dirías que sí, Gaby 💕')">
            Sí 💘
        </button>

        <button class="no" id="noBtn">
            No 🙈
        </button>
    </div>

    <script>
        const noBtn = document.getElementById("noBtn");

        noBtn.addEventListener("mouseover", () => {
            const x = Math.random() * 200 - 100;
            const y = Math.random() * 200 - 100;
            noBtn.style.transform = `translate(${x}px, ${y}px)`;
        });

        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.fontSize = Math.random() * 15 + 15 + "px";
            heart.style.animationDuration = Math.random() * 3 + 4 + "s";
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 7000);
        }

        setInterval(createHeart, 300);
    </script>

</body>
</html>
