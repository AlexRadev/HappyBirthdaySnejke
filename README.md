# HappyBirthdaySnejke
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday!</title>
    <style>
        /* Add your custom CSS styles here */
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f9f9f9;
            color: #333;
            margin: 0;
            padding: 0;
        }

        h1 {
            color: #ff6b6b;
        }

        .birthday-wishes {
            margin-top: 20px;
            font-size: 20px;
            line-height: 1.5;
        }

        .balloons {
            font-size: 30px;
            animation: floatBalloons 3s infinite;
        }

        @keyframes floatBalloons {
            0% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
            100% {
                transform: translateY(0);
            }
        }

        .btn-container {
            margin-top: 30px;
        }

        .btn-container button {
            padding: 10px 20px;
            font-size: 18px;
            background-color: #ff6b6b;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }

        /* Add more custom styles as needed */
    </style>
</head>
<body>
    <header>
        <h1>Happy Birthday!</h1>
    </header>

    <main>
        <section>
            <div class="birthday-wishes">
                <p>Dear Sneji,</p>
                <p>Wishing you a day filled with joy, laughter, and all the things that make you happy.</p>
                <p>As you turn 24, may this year be full of amazing moments and new adventures!</p>
                <p>I love you more than anything in this world, and I am grateful for every day we share together.</p>
                <p>With love and warmest wishes,</p>
                <p>Alex</p>
            </div>
            <div class="balloons">
                🎈🎈🎈🎈🎈
            </div>
            <div class="btn-container">
                <button onclick="flyBalloons()">Surprise</button>
                <button onclick="openGiftsPage()">Open Presents Page</button>
                <button onclick="showLove()">Show Love</button>
                <button onclick="showMessage1()">Click on Me</button>
                <button onclick="showMessage2()">Click on Me</button>
                <button onclick="showMessage3()">Click on Me</button>
            </div>
        </section>
        <canvas id="confettiCanvas"></canvas>
    </main>

    <footer>
        <p>Happy Birthday! 🎉🎂🎈</p>
    </footer>

    <script>
        function flyBalloons() {
            const balloons = document.querySelector('.balloons');
            balloons.style.animation = 'floatBalloons 3s infinite';
            createConfetti();
        }

        function openGiftsPage() {
            window.open('', '_blank').document.write('<h1>Are you ready for tomorrow to find all presents for you!</h1>');
        }

        function showLove() {
            alert('I love you more than anything! ❤️');
        }

        let clickCount = 0;

        function showMessage1() {
            clickCount++;
            if (clickCount === 1) {
                window.open('', '_blank').document.write('<h1>You have perfect body construction! Can you be my personal coach for abs and legs?</h1>');
            }
        }

        function showMessage2() {
            clickCount++;
            if (clickCount === 2) {
                window.open('', '_blank').document.write('<h1>You are very beautiful! Can you be my plastic surgeon?</h1>');
            }
        }

        function showMessage3() {
            clickCount++;
            if (clickCount === 3) {
                window.open('', '_blank').document.write('<h1>Wow! You are amazing!</h1>');
            }
        }

        function createConfetti() {
            const canvas = document.getElementById('confettiCanvas');
            const ctx = canvas.getContext('2d');

            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;

            const colors = ['#FFC0CB', '#FFD700', '#87CEFA', '#FFA07A', '#20B2AA'];

            function random(min, max) {
                return Math.random() * (max - min) + min;
            }

            function confetti() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);

                for (let i = 0; i < 50; i++) {
                    const x = random(0, canvas.width);
                    const y = random(0, canvas.height);
                    const w = random(5, 10);
                    const h = random(10, 20);
                    const color = colors[Math.floor(random(0, colors.length))];

                    ctx.beginPath();
                    ctx.arc(x, y, random(5, 10), 0, 2 * Math.PI);
                    ctx.fillStyle = color;
                    ctx.fill();

                    ctx.fillRect(x, y, w, h);
                    ctx.fillStyle = color;
                    ctx.fill();
                }

                requestAnimationFrame(confetti);
            }

            confetti();
        }
    </script>
</body>
</html>
