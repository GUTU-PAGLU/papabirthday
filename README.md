<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday, Pita Ji!</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%);
            color: #fff;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            transition: all 0.5s ease;
        }

        .container {
            position: relative;
            z-index: 10;
            transition: opacity 0.5s ease;
        }

        .container.hidden {
            opacity: 0;
            pointer-events: none;
        }

        h1 {
            font-size: 4rem;
            margin-bottom: 2rem;
            animation: bounceIn 2s ease-out;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        @keyframes bounceIn {
            0% { transform: scale(0.3); opacity: 0; }
            50% { transform: scale(1.05); }
            70% { transform: scale(0.9); }
            100% { transform: scale(1); opacity: 1; }
        }

        button {
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            border: none;
            padding: 1rem 2rem;
            font-size: 1.5rem;
            color: white;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
            animation: pulse 2s infinite;
        }

        button:hover {
            transform: scale(1.1);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .letter-page {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%);
            z-index: 20;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            animation: fadeIn 1s ease-out;
        }

        .letter-page.show {
            display: flex;
        }

        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        .letter {
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            padding: 2rem;
            border-radius: 20px;
            max-width: 600px;
            font-size: 1.2rem;
            line-height: 1.6;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif; /* SF Pro-like font */
        }

        .back-btn {
            margin-top: 2rem;
            background: linear-gradient(45deg, #4ecdc4, #ff6b6b);
            border: none;
            padding: 0.5rem 1rem;
            font-size: 1rem;
            color: white;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .back-btn:hover {
            transform: scale(1.1);
        }

        /* Confetti animation */
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background: #ff6b6b;
            animation: fall 3s linear infinite;
        }

        .confetti:nth-child(2n) { background: #4ecdc4; animation-delay: 0.5s; }
        .confetti:nth-child(3n) { background: #ffe66d; animation-delay: 1s; }
        .confetti:nth-child(4n) { background: #a8e6cf; animation-delay: 1.5s; }

        @keyframes fall {
            0% { transform: translateY(-100vh) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }

        /* Pop animations for extras */
        .pop {
            animation: pop 0.5s ease-out;
        }

        @keyframes pop {
            0% { transform: scale(0); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }

        /* Floating hearts */
        .heart {
            position: absolute;
            font-size: 2rem;
            color: #ff6b6b;
            animation: float 4s ease-in-out infinite;
        }

        .heart:nth-child(odd) { animation-delay: 1s; }
        .heart:nth-child(even) { animation-delay: 2s; }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
        }
    </style>
</head>
<body>
    <div class="container" id="mainContainer">
        <h1 class="pop">HAPPY BIRTHDAY!</h1>
        <button id="openBtn" class="pop">OPEN</button>
    </div>

    <div class="letter-page" id="letterPage">
        <div class="letter">
            <p id="letterText"></p>
        </div>
        <button class="back-btn" id="backBtn">Back</button>
    </div>

    <!-- Confetti elements -->
    <div class="confetti" style="left: 10%;"></div>
    <div class="confetti" style="left: 20%;"></div>
    <div class="confetti" style="left: 30%;"></div>
    <div class="confetti" style="left: 40%;"></div>
    <div class="confetti" style="left: 50%;"></div>
    <div class="confetti" style="left: 60%;"></div>
    <div class="confetti" style="left: 70%;"></div>
    <div class="confetti" style="left: 80%;"></div>
    <div class="confetti" style="left: 90%;"></div>

    <!-- Floating hearts -->
    <div class="heart" style="left: 15%; top: 20%;">❤️</div>
    <div class="heart" style="left: 75%; top: 30%;">💖</div>
    <div class="heart" style="left: 45%; top: 50%;">😍</div>
    <div class="heart" style="left: 85%; top: 70%;">🎉</div>

    <script>
        const fullText = "HAPPY BIRTHDAY PITA JI AAPKO JANAM DIN KI HAARDIK SHUBH KAAMNAYE OO HELLO I MADE THIS WITH VERY HARDWORK AND ALL OKAY NAAA SOO APRECEAITE MY GIFT AND SAY THANK TO ME BUT NOT WITH MOUTH THANK ME BY GIVING ME 12 MODULES BOOK FOR MY CLAT PREP OKAY JOKES APAART THANK YOU FOR EVERYTHING yOU DID FOR MY AND I AM LUCKY THAT I HAVE PARENT LIKE YOU I LOVE YOU HEHEHEHE SOMETHING I NEED TO TELL YOU JUST BE UNDERSTANDING DONT BE ANGRY STRICT SIGMA BOY OKAY TRY TO UNDERSTAND YOUR KIDS OKAYYY HAPPY BIRTHDAY THANKS TO RAAJMANI SHE AND DADA DID REALLY GOOD WORK THANK YOU EHHEHEHE.";
        const letterText = document.getElementById('letterText');
        let index = 0;

        function typeWriter() {
            if (index < fullText.length) {
                letterText.innerHTML += fullText.charAt(index);
                index++;
                setTimeout(typeWriter, 50); // Adjust speed here (50ms per character; lower = faster)
            }
        }

        document.getElementById('openBtn').addEventListener('click', function() {
            document.getElementById('mainContainer').classList.add('hidden');
            document.getElementById('letterPage').classList.add('show');
            if (index === 0) { // Only start typing if not already started
                typeWriter();
            }
            // Add more confetti on click
            for (let i = 0; i < 10; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + '%';
                confetti.style.animationDelay = Math.random() * 2 + 's';
                document.body.appendChild(confetti);
                setTimeout(() => confetti.remove(), 3000);
            }
        });

        document.getElementById('backBtn').addEventListener('click', function() {
            document.getElementById('letterPage').classList.remove('show');
            document.getElementById('mainContainer').classList.remove('hidden');
            // Reset typing for next open
            index = 0;
            letterText.innerHTML = '';
        });
    </script>
</body>
</html>
