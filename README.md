# Shaurya-New-Year-2026
NEW YEAR WEB PAGE 2026
[new year 2026.html](https://github.com/user-attachments/files/24397185/new.year.2026.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-sc[golden_brown.mp3](https://github.com/user-attachments/files/24397186/golden_brown.mp3)
ale=1.0">
    <title>2026 | Shaurya Kashyap - AI Expert</title>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel+Decorative:wght@700&family=Montserrat:wght@200;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --gold: #d4af37;
            --gold-glow: rgba(212, 175, 55, 0.5);
            --bg: #000000;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background-color: var(--bg);
            color: #fff;
            font-family: 'Montserrat', sans-serif;
            overflow: hidden;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        canvas { position: absolute; top: 0; left: 0; z-index: 1; }

        .main-card {
            position: relative;
            z-index: 10;
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid rgba(255, 215, 0, 0.15);
            padding: 40px;
            border-radius: 40px;
            text-align: center;
            width: 90%;
            max-width: 450px;
            box-shadow: 0 0 60px rgba(0,0,0,1);
            animation: cardEntrance 1.5s ease-out;
        }

        @keyframes cardEntrance {
            from { opacity: 0; transform: scale(0.9) translateY(30px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        h1 {
            font-family: 'Cinzel Decorative', serif;
            font-size: clamp(1.4rem, 5vw, 2.2rem);
            background: linear-gradient(to bottom, #fcf6ba, var(--gold));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 25px;
            letter-spacing: 4px;
            filter: drop-shadow(0 0 10px var(--gold-glow));
        }

        .countdown {
            display: flex;
            justify-content: space-around;
            margin-bottom: 30px;
        }

        .unit span {
            display: block;
            font-size: 2.2rem;
            font-weight: 200;
            color: #fff;
            text-shadow: 0 0 15px var(--gold-glow);
        }

        .unit label {
            font-size: 0.55rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            color: var(--gold);
        }

        .controls {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .btn {
            padding: 14px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            background: rgba(255, 255, 255, 0.05);
            color: white;
            cursor: pointer;
            font-size: 0.85rem;
            font-weight: 600;
            transition: 0.4s;
            text-decoration: none;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .btn:hover {
            background: var(--gold);
            color: black;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(212, 175, 55, 0.3);
        }

        .btn-primary { background: #fff; color: #000; border: none; }

        #qr-box {
            display: none;
            margin: 20px auto;
            padding: 10px;
            background: #fff;
            border-radius: 10px;
            width: 140px;
            animation: fadeIn 0.5s;
        }

        #qr-box img { width: 100%; height: auto; }

        .footer {
            margin-top: 30px;
            font-size: 0.7rem;
            letter-spacing: 1px;
            color: rgba(255,255,255,0.5);
        }

        .footer b {
            display: block;
            color: var(--gold);
            font-size: 0.95rem;
            margin-top: 8px;
            letter-spacing: 2px;
        }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    </style>
</head>
<body>

<canvas id="fireworks"></canvas>

<div class="main-card">
    <h1>HAPPY NEW YEAR 2026</h1>
    
    <div class="countdown">
        <div class="unit"><span id="d">00</span><label>Days</label></div>
        <div class="unit"><span id="h">00</span><label>Hrs</label></div>
        <div class="unit"><span id="m">00</span><label>Min</label></div>
        <div class="unit"><span id="s">00</span><label>Sec</label></div>
    </div>

    <div id="qr-box">
        <img id="qr-img" src="" alt="QR Code">
    </div>

    <div class="controls">
        <button class="btn btn-primary" onclick="playSong()" id="playBtn">🎵 Play Golden Brown</button>
        <button class="btn" onclick="genQR()">🖼️ Generate QR Code</button>
        <button class="btn" onclick="shareWA()">💬 WhatsApp Shaurya's Wish</button>
        <button class="btn" onclick="shareIG()">📸 Link for IG Story</button>
    </div>

    <div class="footer">
        MADE WITH EFFORTS AND LOVE BY
        <b>SHAURYA KASHYAP (AI EXPERT)</b>
    </div>
</div>

<audio id="audio" loop>
    <source src="golden_brown.mp3" type="audio/mpeg">
</audio>

<script>
    const audio = document.getElementById('audio');
    
    // 1. Audio Fix
    function playSong() {
        if(audio.paused) {
            audio.play().catch(() => alert("Error: Add 'golden_brown.mp3' to the same folder!"));
            document.getElementById('playBtn').innerText = "⏸ Pause Music";
        } else {
            audio.pause();
            document.getElementById('playBtn').innerText = "🎵 Play Golden Brown";
        }
    }

    // 2. QR Fix (Works when Public)
    function genQR() {
        const box = document.getElementById('qr-box');
        const img = document.getElementById('qr-img');
        const url = window.location.href;
        img.src = `https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${encodeURIComponent(url)}`;
        box.style.display = box.style.display === 'block' ? 'none' : 'block';
    }

    function shareWA() {
        const text = encodeURIComponent("✨ Shaurya Kashyap (AI Expert) sent you a 2026 New Year Wish! View it here: " + window.location.href);
        window.open(`https://api.whatsapp.com/send?text=${text}`, '_blank');
    }

    function shareIG() {
        navigator.clipboard.writeText(window.location.href);
        alert("Link Copied! Paste this into your Instagram 'Link Sticker'.");
    }

    // 3. Countdown
    const end = new Date("Jan 1, 2026 00:00:00").getTime();
    setInterval(() => {
        const now = new Date().getTime();
        const diff = end - now;
        document.getElementById('d').innerText = Math.floor(diff/(1000*60*60*24)).toString().padStart(2,'0');
        document.getElementById('h').innerText = Math.floor((diff%(1000*60*60*24))/(1000*60*60)).toString().padStart(2,'0');
        document.getElementById('m').innerText = Math.floor((diff%(1000*60*60))/(1000*60)).toString().padStart(2,'0');
        document.getElementById('s').innerText = Math.floor((diff%(1000*60))/1000).toString().padStart(2,'0');
    }, 1000);

    // 4. Fireworks
    const cvs = document.getElementById('fireworks');
    const ctx = cvs.getContext('2d');
    cvs.width = window.innerWidth; cvs.height = window.innerHeight;
    let parts = [];

    class P {
        constructor(x,y,c) {
            this.x=x; this.y=y; this.c=c;
            this.v={x:(Math.random()-0.5)*8, y:(Math.random()-0.5)*8};
            this.a=1;
        }
        show() { ctx.globalAlpha=this.a; ctx.fillStyle=this.c; ctx.beginPath(); ctx.arc(this.x,this.y,2,0,Math.PI*2); ctx.fill(); }
        up() { this.x+=this.v.x; this.y+=this.v.y; this.a-=0.01; }
    }

    function loop() {
        ctx.fillStyle='rgba(0,0,0,0.1)'; ctx.fillRect(0,0,cvs.width,cvs.height);
        parts.forEach((p,i) => { if(p.a>0){p.up(); p.show();} else parts.splice(i,1); });
        if(Math.random()<0.05) {
            let x=Math.random()*cvs.width, y=Math.random()*cvs.height*0.5;
            let col=`hsl(${Math.random()*360},70%,60%)`;
            for(let i=0;i<40;i++) parts.push(new P(x,y,col));
        }
        requestAnimationFrame(loop);
    }
    loop();
</script>
</body>
</html>
