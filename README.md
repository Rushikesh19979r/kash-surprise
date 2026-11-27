

<html lang="en">
<head>
    <meta charset="UTF-8">

    <!-- Mobile responsive and zoom enabled -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>A Special Question for Kash ❤️</title>

    <style>
        * {
            box-sizing: border-box;
        }

        html {
            width: 100%;
            min-height: 100%;
            overflow-x: hidden;
        }

        body {
            margin: 0;
            padding: 18px 12px;
            min-height: 100vh;
            min-height: 100dvh;
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow-x: hidden;
            overflow-y: auto;
            font-family: 'Segoe UI', Arial, sans-serif;
            background: linear-gradient(
                135deg,
                #ff758c,
                #ff7eb3,
                #ffc3a0
            );
        }

        .card {
            width: 100%;
            max-width: 390px;
            margin: auto;
            padding: 25px 20px;
            text-align: center;
            background: rgba(255, 255, 255, 0.96);
            border-radius: 22px;
            box-shadow: 0 12px 35px rgba(120, 0, 50, 0.20);
            position: relative;
            z-index: 2;
        }

        .main-heart {
            font-size: 35px;
            margin-bottom: 8px;
            animation: heartbeat 1.5s infinite;
        }

        h1 {
            color: #e91e63;
            font-size: clamp(21px, 6vw, 27px);
            margin: 8px 0 12px;
        }

        p {
            color: #555;
            font-size: 15px;
            line-height: 1.6;
            margin: 10px 0;
        }

        .question {
            color: #d81b60;
            font-size: clamp(18px, 5vw, 22px);
            font-weight: bold;
            margin: 22px 0 15px;
        }

        .buttons-area {
            width: 100%;
            max-width: 290px;
            height: 85px;
            margin: 0 auto;
            position: relative;
        }

        button {
            border: none;
            border-radius: 30px;
            padding: 11px 23px;
            font-size: 15px;
            font-weight: 700;
            cursor: pointer;
            touch-action: manipulation;
            -webkit-tap-highlight-color: transparent;
        }

        #yesBtn {
            color: white;
            background: #e91e63;
            box-shadow: 0 4px 12px rgba(233, 30, 99, 0.3);
            position: relative;
            z-index: 2;
        }

        #yesBtn:active {
            transform: scale(0.96);
        }

        #noBtn {
            color: #e91e63;
            background: #ffe0eb;
            position: absolute;
            left: 175px;
            top: 0;
            white-space: nowrap;
            transition: left 0.22s ease, top 0.22s ease;
            z-index: 3;
        }

        #celebration {
            display: none;
            animation: appear 0.7s ease;
        }

        #celebration h1 {
            font-size: clamp(22px, 6vw, 28px);
        }

        .celebration-text {
            color: #d81b60;
            font-size: 16px;
            line-height: 1.8;
        }

        .floating {
            position: fixed;
            top: -40px;
            pointer-events: none;
            z-index: 10;
            animation: fall linear forwards;
        }

        @keyframes fall {
            to {
                transform: translateY(110vh) rotate(360deg);
                opacity: 0;
            }
        }

        @keyframes heartbeat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.15);
            }
        }

        @keyframes appear {
            from {
                opacity: 0;
                transform: scale(0.85);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @media (max-width: 480px) {
            body {
                padding: 14px 10px;
            }

            .card {
                max-width: 350px;
                padding: 22px 16px;
                border-radius: 19px;
            }

            .main-heart {
                font-size: 30px;
            }

            p {
                font-size: 14px;
            }

            .question {
                margin: 18px 0 12px;
            }

            .buttons-area {
                max-width: 270px;
                height: 78px;
            }

            button {
                padding: 10px 19px;
                font-size: 14px;
            }
        }

        @media (max-height: 550px) {
            body {
                align-items: flex-start;
            }
        }
    </style>
</head>

<body>

    <div class="card">

        <div id="proposal">

            <div class="main-heart">❤️</div>

            <h1>My Dearest Kash!</h1>

            <p>
                Every love story is beautiful, but ours is my favourite.
                You make my ordinary days special and my world more beautiful.
            </p>

            <div class="question">
                Will you marry me? 💍
            </div>

            <div class="buttons-area" id="buttonsArea">
                <button id="yesBtn" onclick="sayYes()">
                    Yes! ❤️
                </button>

                <button id="noBtn" type="button">
                    No 🙈
                </button>
            </div>

        </div>

        <div id="celebration">

            <div class="main-heart">💖</div>

            <h1>She said YES! 🥹</h1>

            <p class="celebration-text">
                I knew you would say YES! 💍
                <br><br>

                You are my favourite person.
                If I could choose again, I would still choose you.
                <br><br>

                Forever starts with you, Kash! 🌹❤️
            </p>

        </div>

    </div>

    <script>
        const noBtn = document.getElementById("noBtn");
        const buttonsArea = document.getElementById("buttonsArea");

        let angryTimer;
        let hoverTimer;

        function moveNoButton() {
            const areaWidth = buttonsArea.clientWidth;
            const areaHeight = buttonsArea.clientHeight;

            const buttonWidth = noBtn.offsetWidth;
            const buttonHeight = noBtn.offsetHeight;

            const maxX = Math.max(0, areaWidth - buttonWidth);
            const maxY = Math.max(0, areaHeight - buttonHeight);

            const x = Math.random() * maxX;
            const y = Math.random() * maxY;

            noBtn.style.left = x + "px";
            noBtn.style.top = y + "px";
        }

        function showAngry() {
            clearTimeout(angryTimer);
            clearTimeout(hoverTimer);

            noBtn.textContent = "😡";

            angryTimer = setTimeout(() => {
                noBtn.textContent = "No 🙈";
                moveNoButton();
            }, 3000);
        }

        // Clicking No displays angry emoji for 3 seconds
        noBtn.addEventListener("click", showAngry);

        // On desktop, move away after the mouse approaches.
        // A short delay allows the user to click the button.
        noBtn.addEventListener("pointerenter", (event) => {
            if (
                event.pointerType === "mouse" &&
                noBtn.textContent !== "😡"
            ) {
                clearTimeout(hoverTimer);

                hoverTimer = setTimeout(() => {
                    if (noBtn.textContent !== "😡") {
                        moveNoButton();
                    }
                }, 600);
            }
        });

        noBtn.addEventListener("pointerdown", () => {
            clearTimeout(hoverTimer);
        });

        noBtn.addEventListener("pointerleave", () => {
            clearTimeout(hoverTimer);
        });

        // Reposition safely when screen size changes
        window.addEventListener("resize", () => {
            moveNoButton();
        });

        // Initial position
        window.addEventListener("load", moveNoButton);

        // Romantic floating emojis
        function createFloatingEmoji() {
            const emojis = [
                "❤️", "💕", "💖", "💗",
                "🌹", "🌸", "🌷", "💐",
                "✨", "🦋"
            ];

            const item = document.createElement("div");

            item.className = "floating";

            item.textContent =
                emojis[Math.floor(Math.random() * emojis.length)];

            item.style.left = Math.random() * 100 + "vw";

            item.style.fontSize =
                (18 + Math.random() * 20) + "px";

            item.style.animationDuration =
                (3 + Math.random() * 3) + "s";

            document.body.appendChild(item);

            setTimeout(() => {
                item.remove();
            }, 6500);
        }

        let celebrationInterval;

        function sayYes() {
            document.getElementById("proposal").style.display = "none";

            document.getElementById("celebration").style.display = "block";

            clearTimeout(angryTimer);
            clearTimeout(hoverTimer);

            noBtn.style.display = "none";

            createFloatingEmoji();

            celebrationInterval = setInterval(
                createFloatingEmoji,
                250
            );

            // Stop creating new emojis after 30 seconds
            setTimeout(() => {
                clearInterval(celebrationInterval);
            }, 30000);
        }
    </script>

</body>
</html>
