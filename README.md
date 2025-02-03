<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine, Tav?</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Uncial+Antiqua&display=swap');

        body {
            font-family: 'Uncial Antiqua', cursive;
            text-align: center;
            background: url('https://i.imgur.com/MecSY7M.jpeg') no-repeat center center fixed;
            background-size: cover;
            color: white;
            padding: 50px;
            cursor: url('https://cur.cursors-4u.net/love/lov-1/lov36.ani'), auto;
        }
        .container {
            background: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 15px;
            display: inline-block;
            box-shadow: 0 4px 8px rgba(0,0,0,0.5);
        }
        h1 {
            color: #FFD700;
            text-shadow: 2px 2px 8px black;
        }
        .heart {
            font-size: 40px;
            color: red;
        }
        .gif-container {
            width: 80%;
            max-width: 500px;
            margin: 20px auto;
        }
        .gif {
            width: 100%;
            border-radius: 10px;
            display: none;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            font-size: 18px;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            font-weight: bold;
        }
        .yes {
            background-color: #FFD700;
            color: black;
        }
        .no {
            background-color: red;
            color: white;
            position: absolute;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Will you be my Valentine, Tav? <span class="heart">❤️</span></h1>
        
        <p>Our love story is better than any Baldur’s Gate quest.</p>
        <p>Without you, my heart feels like Astarion in sunlight.</p>
        
        <!-- GIF Slideshow -->
        <div class="gif-container">
            <img class="gif" src="https://media.giphy.com/media/l2R0cE5EqO3QHiCoU/giphy.gif" alt="Heart GIF">
            <img class="gif" src="https://media.giphy.com/media/fvjBHSTYMcE1fKcrP9/giphy.gif" alt="Funny GIF">
            <img class="gif" src="https://media.giphy.com/media/ZOStzpF9H5syI/giphy.gif" alt="Romantic GIF">
        </div>

        <div class="buttons">
            <button class="yes" onclick="celebrate()">Yes! (Roll Persuasion)</button>
            <button class="no" onmouseover="moveButton(this)">No (Wisdom Saving Throw)</button>
        </div>
    </div>

    <!-- Background Music -->
    <audio id="bgMusic" loop autoplay>
        <source src="https://www.myinstants.com/media/sounds/i-wanna-get-freaky-with-you.mp3" type="audio/mpeg">
    </audio>

    <script>
        // Slideshow functionality
        let currentGif = 0;
        const gifs = document.querySelectorAll(".gif");

        function showNextGif() {
            gifs.forEach((gif, index) => {
                gif.style.display = index === currentGif ? "block" : "none";
            });
            currentGif = (currentGif + 1) % gifs.length;
        }

        // Show the first GIF and start the slideshow
        showNextGif();
        setInterval(showNextGif, 3000);

        // Make the "No" button run away
        function moveButton(button) {
            let x = Math.random() * window.innerWidth - 100;
            let y = Math.random() * window.innerHeight - 50;
            button.style.left = x + 'px';
            button.style.top = y + 'px';
        }

        // Celebration when "Yes" is clicked
        function celebrate() {
            alert("YES! Our romance is now a critical success! 🎲❤️😉");

            // Confetti effect
            let confettiContainer = document.createElement("div");
            confettiContainer.style.position = "fixed";
            confettiContainer.style.top = "0";
            confettiContainer.style.left = "0";
            confettiContainer.style.width = "100%";
            confettiContainer.style.height = "100%";
            confettiContainer.style.pointerEvents = "none";
            document.body.appendChild(confettiContainer);

            for (let i = 0; i < 100; i++) {
                let confetti = document.createElement("div");
                confetti.innerHTML = "❤️";
                confetti.style.position = "absolute";
                confetti.style.left = Math.random() * 100 + "vw";
                confetti.style.top = Math.random() * -10 + "vh";
                confetti.style.fontSize = Math.random() * 24 + 12 + "px";
                confetti.style.animation = "falling 2s linear infinite";
                confettiContainer.appendChild(confetti);
            }

            // Remove confetti after 5 seconds
            setTimeout(() => confettiContainer.remove(), 5000);
        }
    </script>

    <style>
        @keyframes falling {
            to {
                transform: translateY(100vh);
            }
        }
    </style>

</body>
</html>

