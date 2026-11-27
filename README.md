<!DOCTYPE html>
<html>
<head>
    <title>Fun Proposal</title>
</head>
<body>

<h2>Will you marry me? 💍</h2>

<!-- YES Button -->
<button onclick="sayYes()">Yes</button>

<!-- NO Button (moving) -->
<button id="noBtn" onmouseover="moveButton()">No</button>

<script>
    function sayYes() {
        alert("I knew it! ❤️");
    }

    function moveButton() {
        var btn = document.getElementById("noBtn");

        // Random position within window
        var x = Math.random() * (window.innerWidth - 100);
        var y = Math.random() * (window.innerHeight - 50);

        btn.style.position = "absolute";
        btn.style.left = x + "px";
        btn.style.top = y + "px";
    }
</script>

</body>
</html>
