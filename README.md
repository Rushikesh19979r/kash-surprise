

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For My Dearest Kash ❤️</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    min-height: 100dvh;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ffe0ec, #ffb6cf, #f9c5e0);
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    text-align: center;
    padding: 15px;
}

/* Main proposal card */
.card {
    width: 100%;
    max-width: 480px;
    padding: 40px 25px;
    background: rgba(255,255,255,0.9);
    border-radius: 28px;
    box-shadow: 0 15px 45px rgba(180,50,100,0.2);
    position: relative;
    z-index: 2;
    backdrop-filter: blur(10px);
}

.heart {
    font-size: 65px;
    animation: heartbeat 1.3s infinite;
}

h1 {
    color: #d6336c;
    font-size: 32px;
    margin: 18px 0;
}

.message {
    color: #87405c;
    font-size: 17px;
    line-height: 1.8;
    margin-bottom: 25px;
}

.question {
    color: #d6336c;
    font-size: 27px;
    margin: 20px 0 25px;
}

.buttons {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;
    min-height: 60px;
}

button {
    border: none;
    padding: 15px 25px;
    border-radius: 35px;
    font-size: 17px;
    font-weight: bold;
    cursor: pointer;
    white-space: nowrap;
    -webkit-tap-highlight-color: transparent;
    touch-action: manipulation;
}

#yesBtn {
    background: linear-gradient(135deg, #ff4f91, #e91e63);
    color: white;
    box-shadow: 0 6px 18px #e91e6350;
    transition: transform 0.3s;
}

#yesBtn:hover {
    transform: scale(1.08);
}

#noBtn {
    background: #f1e5eb;
    color: #9b5470;
    transition: left 0.18s ease, top 0.18s ease;
}

#noBtn:disabled {
    opacity: 1;
    cursor: default;
}

.footer {
    margin-top: 30px;
    color: #c44d7c;
    font-size: 14px;
}

/* Success message */
#success {
    display: none;
    margin-top: 25px;
    animation: appear 1s ease;
}

#success h2 {
    color: #d6336c;
    font-size: 29px;
    margin-bottom: 15px;
}

#success p {
    color: #87405c;
    line-height: 1.8;
    font-size: 17px;
}

/* Floating hearts and flowers */
.floating {
    position: fixed;
    bottom: -60px;
    pointer-events: none;
    z-index: 10;
    animation: floatUp linear forwards;
    user-select: none;
}

@keyframes heartbeat {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.2); }
}

@keyframes floatUp {
    0% {
        transform: translateY(0) rotate(0deg);
        opacity: 0;
    }
    15% { opacity: 1; }
    100% {
        transform: translateY(-115vh) rotate(360deg);
        opacity: 0;
    }
}

@keyframes appear {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Mobile responsive design */
@media (max-width: 480px) {
    .card {
        padding: 32px 18px;
        border-radius: 24px;
    }

    .heart {
        font-size: 55px;
    }

    h1 {
        font-size: 27px;
    }

    .message {
        font-size: 15px;
    }

    .question {
        font-size: 23px;
    }

    .buttons {
        gap: 10px;
    }

    button {
        padding: 13px 19px;
        font-size: 15px;
    }

    .footer {
        font-size: 12px;
    }
}
</style>
</head>

<body>

<div class="card">

    <div class="heart">❤️</div>

    <h1>My Dearest Kash!</h1>

    <p class="message">
        Every love story is beautiful,
        but ours is my favourite. 🥰
        <br><br>
        You make my ordinary days special
        and my world more beautiful.
        <br><br>
        So, I have one little question for you...
    </p>

    <h2 class="question">
        Will you marry me? 💍
    </h2>

    <div class="buttons">

        <button id="yesBtn" onclick="sayYes()">
            Yes, I will! ❤️
        </button>

        <button id="noBtn">
            No 🙈
        </button>

    </div>

    <div id="success">

        <h2>Yayyyyy! ❤️🥹</h2>

        <p>
            I knew you would say YES!
            <br><br>
            You are my favourite person.
            <br>
            If I could choose again,
            I would still choose you.
            ❤️
            <br><br>
            Forever starts with you, Kash! 💍🌹
        </p>

    </div>

    <div class="footer">
        Made with endless love, just for you ❤️
    </div>

</div>

<script>

// NO BUTTON SETTINGS

const noBtn = document.getElementById("noBtn");

let angryTimer = null;
let moveTimer = null;
let isAngry = false;

// Find a random position completely inside the screen
function getRandomPosition() {

    const margin = 12;

    const width = noBtn.offsetWidth;
    const height = noBtn.offsetHeight;

    const screenWidth = document.documentElement.clientWidth;
    const screenHeight = document.documentElement.clientHeight;

    const maxX = Math.max(margin, screenWidth - width - margin);
    const maxY = Math.max(margin, screenHeight - height - margin);

    return {
        x: margin + Math.random() * Math.max(0, maxX - margin),
        y: margin + Math.random() * Math.max(0, maxY - margin)
    };
}

// Move No button
function moveNo() {

    if (isAngry || celebrationStarted) return;

    clearTimeout(moveTimer);

    const position = getRandomPosition();

    noBtn.style.position = "fixed";
    noBtn.style.left = position.x + "px";
    noBtn.style.top = position.y + "px";
    noBtn.style.zIndex = "20";
}

// Desktop: run away when mouse approaches
noBtn.addEventListener("pointerenter", function(event) {

    if (event.pointerType === "mouse") {
        moveNo();
    }

});

// Mobile: tapping No shows angry emoji
noBtn.addEventListener("click", function() {

    if (isAngry || celebrationStarted) return;

    angryNo();

});

// Angry emoji for 3 seconds
function angryNo() {

    if (isAngry || celebrationStarted) return;

    isAngry = true;

    clearTimeout(moveTimer);
    clearTimeout(angryTimer);

    noBtn.innerHTML = "😡";
    noBtn.disabled = true;

    angryTimer = setTimeout(function() {

        noBtn.innerHTML = "No 🙈";
        noBtn.disabled = false;
        isAngry = false;

        // Move to another safe position after 3 seconds
        moveNo();

    }, 3000);

}

// Keep No button inside screen when resized
window.addEventListener("resize", function() {

    if (noBtn.style.position === "fixed") {

        const position = getRandomPosition();

        noBtn.style.left = position.x + "px";
        noBtn.style.top = position.y + "px";

    }

});


// YES BUTTON CELEBRATION

let celebrationStarted = false;

function sayYes() {

    if (celebrationStarted) return;

    celebrationStarted = true;

    clearTimeout(angryTimer);
    clearTimeout(moveTimer);

    document.querySelector(".message").style.display = "none";

    document.querySelector(".question").style.display = "none";

    document.querySelector(".buttons").style.display = "none";

    document.getElementById("success").style.display = "block";

    // Floating emoji collection
    const emojis = [
        "❤️",
        "💕",
        "💖",
        "💗",
        "🌹",
        "🌸",
        "🌷",
        "💐",
        "✨",
        "🦋"
    ];

    function createFloatingItem() {

        const item = document.createElement("div");

        item.className = "floating";

        item.innerHTML =
            emojis[Math.floor(Math.random() * emojis.length)];

        item.style.left = Math.random() * 95 + "vw";

        item.style.fontSize =
            (20 + Math.random() * 25) + "px";

        const duration = 3 + Math.random() * 4;

        item.style.animationDuration = duration + "s";

        document.body.appendChild(item);

        setTimeout(function() {
            item.remove();
        }, duration * 1000);

    }

    // Initial celebration shower
    for (let i = 0; i < 60; i++) {

        setTimeout(createFloatingItem, i * 100);

    }

    // Continuous hearts, flowers and sparkles
    setInterval(createFloatingItem, 250);

}

</script>

</body>
</html>
