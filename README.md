<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine, Tav? 😏</title>
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

        /* Love Heart Mouse Cursor */
        body {
            cursor: url('https://cur.cursors-4u.net/love/lov-1/lov36.ani'), auto;
        }

        /* Hidden GIFs for No button click */
        .memes {
            display: none;
            text-align: center;
        }

        .memes img {
            width: 60%;
            margin-top: 20px;
            border-radius: 10px;
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
            <img class="gif" src="https://media.giphy.com/media/aftvlKz6bGzS0/giphy.gif" alt="Sexy GIF">
            <img class="gif" src="https://media.giphy.com/media/2Wv76xVF415S0/giphy.gif" alt="New GIF">
        </div>

        <div class="buttons">
            <button class="yes" onclick="celebrate()">Yes! (Roll Persuasion)</button>
            <button class="no" onmouseover="moveButton(this)" onclick="showMemes()">No (Wisdom Saving Throw)</button>
        </div>
    </div>

    <!-- Memes that will appear if "No" is clicked -->
    <div class="memes" id="memesContainer">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExdmc0c2txZmY0eHE0NGFzZWY5aWt4OWV3cWd1ZnFqNWIxajg3OGh4NCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/W0c3xcZ3F1d0EYYb0f/giphy.gif" alt="Meme 1">
        <img src="https://media.giphy.com/media/7SF5scGB2AFrgsXP63/giphy.gif?cid=790b7611vg4skqff4xq44asef9ikx9ewqgufqj5b1j878hx4&ep=v1_gifs_search&rid=giphy.gif&ct=g" alt="Meme 2">
        <img src="https://media.giphy.com/media/T1WqKkLY753dZghbu6/giphy.gif?cid=790b7611vg4skqff4xq44asef9ikx9ewqgufqj5b1j878hx4&ep=v1_gifs_search&rid=giphy.gif&ct=g" alt="Meme 3">
        <img src="https://media.giphy.com/media/a9xhxAxaqOfQs/giphy.gif?cid=790b7611vg4skqff4xq44asef9ikx9ewqgufqj5b1j878hx4&ep=v1_gifs_search&rid=giphy.gif&ct=g" alt="Meme 4">
        <img src="https://media.giphy.com/media/iJJ6E58EttmFqgLo96/giphy.gif?cid=790b7611vg4skqff4xq44asef9ikx9ewqgufqj5b1j878hx4&ep=v1_gifs_search&rid=giphy.gif&ct=g" alt="Meme 5">
    </div>

    <!-- Background Music (Looping Playlist) -->
    <audio id="bgMusic" autoplay loop>
        <source src="https://www.myinstants.com/media/sounds/i-wanna-get-freaky-with-you.mp3" type="audio/mpeg">
        <source src="https://www.myinstants.com/media/sounds/genuine-pony.mp3" type="audio/mpeg">
        <source src="https://www.myinstants.com/media/sounds/lets-get-it-on.mp3" type="audio/mpeg">
    </audio>

    <!-- Sad Music when No button is clicked -->
    <audio id="sadMusic" src="https://www.myinstants.com/media/sounds/sad-music.mp3" preload="auto"></audio>

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

        // Show memes when "No" is clicked and play sad music
        function showMemes() {
            document.getElementById("memesContainer").style.display = "block";
            document.getElementById("sadMusic").play();  // Play sad music
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

