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
        .meme {
            width: 80%;
            max-width: 500px;
            border-radius: 10px;
            margin: 20px 0;
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
        
        <!-- Funny Baldur’s Gate meme (working link) -->
        <img class="meme" src="https://i.imgur.com/2Z5NyU4.jpeg" alt="Baldur's Gate meme">
        
        <div class="buttons">
            <button class="yes" onclick="alert('YES! Our romance is now a critical success! 🎲❤️')">Yes! (Roll Persuasion)</button>
            <button class="no" onmouseover="moveButton(this)">No (Wisdom Saving Throw)</button>
        </div>
    </div>

    <script>
        function moveButton(button) {
            let x = Math.random() * window.innerWidth - 100;
            let y = Math.random() * window.innerHeight - 50;
            button.style.left = x + 'px';
            button.style.top = y + 'px';
        }
    </script>

</body>
</html>
