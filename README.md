<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacking Hub - Join the Underground</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: #1a1a1a;
            color: #0f0;
            font-family: 'Courier New', monospace;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }
        .header {
            text-align: center;
            padding: 20px;
            background: #000;
            width: 100%;
            box-shadow: 0 0 10px #0f0;
        }
        .header h1 {
            font-size: 36px;
            margin: 0;
            text-shadow: 0 0 5px #0f0;
        }
        .content {
            text-align: center;
            padding: 50px;
            background: #2c2f33;
            border-radius: 10px;
            margin: 20px;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.3);
        }
        .content p {
            font-size: 24px;
            margin: 20px 0;
        }
        .discord-button {
            display: inline-block;
            padding: 15px 30px;
            background: #ff4444;
            color: #fff;
            text-decoration: none;
            font-size: 20px;
            border-radius: 5px;
            transition: background 0.3s, box-shadow 0.3s;
        }
        .discord-button:hover {
            background: #cc3333;
            box-shadow: 0 0 10px #ff4444;
        }
        .matrix {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.2;
        }
    </style>
</head>
<body>
    <canvas id="matrix" class="matrix"></canvas>
    <div class="header">
        <h1>Welcome to the Underground: RATs, Hacks, and More!</h1>
    </div>
    <div class="content">
        <p>Join our elite hacking server! Learn to deploy RATs, master cyber skills, and dominate the game!</p>
        <a href="https://discord.gg/mcM7wvQMCh" class="discord-button">Join the Hacking Hub!</a>
    </div>
    <script>
        // Matrix-style background animation
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');
        canvas.height = window.innerHeight;
        canvas.width = window.innerWidth;
        const chars = '01';
        const fontSize = 14;
        const columns = canvas.width / fontSize;
        const drops = [];
        for (let x = 0; x < columns; x++) drops[x] = 1;
        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = '#0F0';
            ctx.font = fontSize + 'px monospace';
            for (let i = 0; i < drops.length; i++) {
                const text = chars.charAt(Math.floor(Math.random() * chars.length));
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) drops[i] = 0;
                drops[i]++;
            }
        }
        setInterval(draw, 33);
    </script>
</body>
</html>
