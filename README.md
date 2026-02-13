<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Princess 💗👑</title>

<style>
body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(135deg, #ff4e88, #ff99ac);
    font-family: 'Segoe UI', sans-serif;
    overflow: hidden;
    text-align: center;
}

.card {
    background: white;
    padding: 40px;
    border-radius: 25px;
    box-shadow: 0 20px 50px rgba(0,0,0,0.3);
    width: 340px;
    position: relative;
}

h1 {
    color: #ff2e63;
    margin-bottom: 10px;
}

h2 {
    color: #333;
    font-weight: normal;
}

.buttons {
    margin-top: 30px;
    position: relative;
    height: 150px;
}

button {
    padding: 12px 28px;
    font-size: 18px;
    border: none;
    border-radius: 40px;
    cursor: pointer;
    position: absolute;
    transition: 0.3s ease;
}

#yesBtn {
    background: #ff2e63;
    color: white;
    left: 20%;
    transform: scale(1);
}

#noBtn {
    background: #444;
    color: white;
    left: 55%;
}

.message {
    margin-top: 20px;
    font-size: 18px;
    color: #ff2e63;
    min-height: 40px;
}

.heart {
    position: absolute;
    font-size: 22px;
    animation: floatUp 4s linear forwards;
}

@keyframes floatUp {
    0% { opacity: 1; transform: translateY(0); }
    100% { opacity: 0; transform: translateY(-300px); }
}
</style>
</head>

<body>

<audio id="bgMusic" loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<div class="card">
    <h1>Princess 💗👑</h1>
    <h2>Will you be my Valentine? 💘</h2>

    <div class="buttons">
        <button id="yesBtn">Yes 💖</button>
        <button id="noBtn">No 💔</button>
    </div>

    <div class="message" id="messageText"></div>
</div>

<script>
const noBtn = document.getElementById("noBtn");
const yesBtn = document.getElementById("yesBtn");
const messageText = document.getElementById("messageText");
const bgMusic = document.getElementById("bgMusic");

let scale = 1;
let speed = 1;

const messages = [
    "Are you sure Princess? 🥺",
    "My heart is fragile 💔",
    "You can't escape destiny 😌",
    "Just press Yes already 😭",
    "We both know it's Yes 💕"
];

function moveButton() {
    const x = Math.random() * (window.innerWidth - 120);
    const y = Math.random() * (window.innerHeight - 120);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";

    scale += 0.25;
    yesBtn.style.transform = "scale(" + scale + ")";

    messageText.textContent = messages[Math.floor(Math.random() * messages.length)];
}

noBtn.addEventListener("mouseover", moveButton);
noBtn.addEventListener("click", moveButton);

yesBtn.addEventListener("click", function() {
    bgMusic.play();
    messageText.textContent = "Yaaaaay! 🥰 You just made me the happiest man alive 💕";

    for (let i = 0; i < 30; i++) {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.top = Math.random() * window.innerHeight + "px";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 4000);
    }
});
</script>

</body>
</html>
