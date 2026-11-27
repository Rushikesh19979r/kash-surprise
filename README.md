
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>A Little Question For Kash ❤️</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ffe0ec, #ffb6cf, #f9c5e0);
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    text-align: center;
}

.card {
    width: 90%;
    max-width: 480px;
    padding: 45px 25px;
    background: rgba(255,255,255,0.85);
    border-radius: 30px;
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
    margin-bottom: 30px;
}

.buttons {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
}

button {
    border: none;
    padding: 15px 27px;
    border-radius: 35px;
    font-size: 17px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.3s;
}

#yesBtn {
    background: linear-gradient(135deg, #ff4f91, #e91e63);
    color: white;
    box-shadow: 0 6px 18px #e91e6350;
}

#yesBtn:hover {
    transform: scale(1.1);
}

#noBtn {
    background: #f1e5eb;
    color: #9b5470;
}

.footer {
    margin-top: 30px;
    color: #c44d7c;
    font-size: 14px;
}

#success {
    display: none;
    margin-top: 25px;
    animation: appear 1s ease;
}

#success h2 {
    color: #d6336c;
    font-size: 28px;
    margin-bottom: 12px;
}

#success p {
    color: #87405c;
    line-height: 1.7;
    font-size: 17px;
}

.floating {
    position: fixed;
    bottom: -50px;
    pointer-events: none;
    z-index: 5;
    animation: floatUp linear forwards;
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
        transform: translateY(-110vh) rotate(360deg);
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

    <h1 style="font-size:27px;">
        Will you marry me? 💍
    </h1>

    <div class="buttons">
        <button id="yesBtn" onclick="sayYes()">
            Yes, I will! ❤️
        </button>

        <button id="noBtn"
                onmouseenter="moveNo()"
                onclick="moveNo()">
            No 🙈
        </button>
    </div>

    <div id="success">
        <h2>Yayyyyy! ❤️🥹</h2>
        <p>
            I knew you would say YES!
            <br><br>
            You are my favourite person.
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

function moveNo() {
    const btn = document.getElementById("noBtn");

    const maxX = window.innerWidth - btn.offsetWidth - 20;
    const maxY = window.innerHeight - btn.offsetHeight - 20;

    btn.style.position = "fixed";
    btn.style.left = Math.max(10, Math.random() * maxX) + "px";
    btn.style.top = Math.max(10, Math.random() * maxY) + "px";
}

function sayYes() {

    document.getElementById("success").style.display = "block";

    document.querySelector(".message").style.display = "none";
    document.getElementById("noBtn").style.display = "none";
    document.getElementById("yesBtn").style.display = "none";

    const emojis = ["❤️", "💕", "💖", "🌹", "🌸", "✨", "💗", "💐"];

    function createHeart() {
        const item = document.createElement("div");

        item.className = "floating";
        item.innerHTML = emojis[
            Math.floor(Math.random() * emojis.length)
        ];

        item.style.left = Math.random() * 100 + "vw";
        item.style.fontSize = (20 + Math.random() * 25) + "px";

        const duration = 3 + Math.random() * 4;
        item.style.animationDuration = duration + "s";

        document.body.appendChild(item);

        setTimeout(() => item.remove(), duration * 1000);
    }

    for (let i = 0; i < 60; i++) {
        setTimeout(createHeart, i * 100);
    }

    setInterval(createHeart, 250);
}

</script>

</body>
</html>
