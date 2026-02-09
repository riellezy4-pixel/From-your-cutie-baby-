<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Him 🤍</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Montserrat:wght@300;400&family=Playfair+Display:ital,wght@0,400;1,600&display=swap" rel="stylesheet">
    <style>
        :root { --deep-blue: #1a2a6c; --gold: #f5af19; --rose: #ee0979; --soft-white: #f8f9fa; }
        
        body { 
            margin: 0; 
            font-family: 'Montserrat', sans-serif; 
            background: linear-gradient(to bottom, #1a2a6c, #b21f1f, #fdbb2d);
            background-attachment: fixed;
            color: var(--soft-white); 
            overflow-x: hidden; 
            text-align: center; 
        }
        
        /* Lock Screen */
        #lock { position: fixed; inset: 0; background: #111; z-index: 2000; display: flex; flex-direction: column; justify-content: center; align-items: center; }
        .lock-card { padding: 40px; border-radius: 20px; border: 1px solid rgba(255,255,255,0.2); backdrop-filter: blur(10px); }
        input { padding: 12px; border: none; border-radius: 5px; margin: 20px 0; outline: none; text-align: center; font-size: 16px; background: rgba(255,255,255,0.9); }

        .container { max-width: 650px; margin: 0 auto; padding: 60px 20px; position: relative; z-index: 100; }
        h1 { font-family: 'Playfair Display', serif; font-size: 3rem; color: white; text-shadow: 0 0 20px rgba(255,255,255,0.5); }
        
        .btn { background: transparent; color: white; border: 2px solid white; padding: 15px 45px; border-radius: 5px; font-weight: bold; cursor: pointer; font-size: 1rem; transition: 0.4s; text-transform: uppercase; letter-spacing: 2px; }
        .btn:hover { background: white; color: #1a2a6c; box-shadow: 0 0 20px rgba(255,255,255,0.4); }

        /* Envelope */
        #envelope-wrapper { display: none; margin-top: 50px; cursor: pointer; }
        .envelope { position: relative; width: 200px; height: 130px; background: #fff; margin: 0 auto; border-radius: 5px; transition: 0.5s; box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
        .envelope::before { content: ""; position: absolute; top: 0; left: 0; border-left: 100px solid transparent; border-right: 100px solid transparent; border-top: 80px solid #ddd; transform-origin: top; transition: 0.5s; z-index: 2; }
        .envelope.open::before { transform: rotateX(180deg); }
        .heart-seal { position: absolute; top: 40%; left: 50%; transform: translate(-50%, -50%); font-size: 40px; z-index: 3; filter: grayscale(1); opacity: 0.8; }

        #content { display: none; opacity: 0; transition: 2s ease; }
        
        /* Romantic Letter */
        .letter-paper { 
            background: rgba(255, 255, 255, 0.95); 
            padding: 50px; 
            border-radius: 2px; 
            box-shadow: 0 30px 60px rgba(0,0,0,0.4); 
            text-align: left; 
            line-height: 2; 
            font-family: 'Playfair Display', serif; 
            font-size: 1.2rem; 
            color: #222;
            white-space: pre-line; 
            margin-top: 50px; 
            border-top: 10px solid var(--deep-blue);
        }

        /* The Love Rain */
        .rain-drop {
            position: fixed;
            top: -50px;
            font-family: 'Dancing Script', cursive;
            font-weight: bold;
            color: white;
            opacity: 0.7;
            white-space: nowrap;
            pointer-events: none;
            z-index: 1;
            animation: fall linear infinite;
        }

        @keyframes fall {
            to { transform: translateY(110vh); }
        }
    </style>
</head>
<body>

    <div id="lock">
        <div class="lock-card">
            <h1 style="font-size: 2rem;">For Him.</h1>
            <input type="password" id="pass" placeholder="Enter password">
            <br>
            <button class="btn" onclick="unlock()">Unlock 🤍</button>
        </div>
    </div>

    <div class="container">
        <div id="question-area" style="display:none;">
            <h1>Will you be my Valentine?</h1>
            <button class="btn" onclick="showEnvelope()">I have a letter for you</button>
        </div>

        <div id="envelope-wrapper" onclick="revealLetter()">
            <div class="envelope" id="env">
                <div class="heart-seal">✉️</div>
            </div>
            <p style="margin-top: 20px; font-style: italic;">Tap to open</p>
        </div>

        <div id="content">
            <div class="letter-paper" id="letterText"></div>
            <p style="margin-top: 100px; font-family: 'Dancing Script'; font-size: 2rem;">Forever Yours.</p>
        </div>
    </div>

    <script>
        const fullLetter = `My love,\n\nI’ve been thinking about you a lot lately, about how you walked into my life in the most unexpected way and somehow made everything feel lighter. There are days when the world feels loud and heavy, and then there’s you—your laugh, your presence, the calm you bring even when things get messy. I don’t always say this out loud, but having you in my life is one of the things I’m most grateful for.\n\nThank you for choosing me every day, even on the days when I’m not at my best. Thank you for being patient when I’m moody, tired, or quiet. Thank you for listening to my stories, even the random ones that don’t always make sense. You remind me that love doesn’t have to be perfect to be real. It just has to be honest.\n\nI love how you make ordinary moments feel special. The simple talks, the jokes we share, the times we just sit and exist together—those moments are my favorite. With you, I’ve learned that comfort can be beautiful. I’ve learned that peace can feel like home.\n\nYou inspire me to be better—not in a pressured way, but in a gentle way. When I doubt myself, you remind me of my worth. You don’t just love me; you believe in me, and that’s something I hold close to my heart.\n\nI know we’re both still learning. But I want you to know that I choose to work through those days with you. I choose patience over pride. I choose honesty over silence. I choose us, not because we’re perfect, but because we’re willing to grow together.\n\nI admire your strength, even when you don’t see it in yourself. I admire how you try, how you keep going, how you show up for the people you care about. You don’t have to be perfect for me to love you. I love you for who you are, for the effort you give, for the heart you carry.\n\nThank you for being my safe place. Thank you for being my comfort. I promise to keep trying to be someone who listens, who understands, and who shows love not just with words, but with actions.\n\nNo matter how busy life gets, I hope you always remember this: you are important to me. You are valued. You are cared for deeply. I’m proud of you for who you are and for who you’re becoming. And I’m grateful that out of all the people in this world, I get to walk this part of life with you.\n\nWith all my love,\nAlways yours 🤍`;

        function unlock() {
            if(document.getElementById('pass').value.toLowerCase() === "mylove") {
                document.getElementById('lock').style.display = "none";
                document.getElementById('question-area').style.display = "block";
            } else { alert("Try again, love. 🌸"); }
        }

        function showEnvelope() {
            document.getElementById('question-area').style.display = "none";
            document.getElementById('envelope-wrapper').style.display = "block";
        }

        function revealLetter() {
            document.getElementById('env').classList.add('open');
            setTimeout(() => {
                document.getElementById('envelope-wrapper').style.display = "none";
                document.getElementById('content').style.display = "block";
                setTimeout(() => document.getElementById('content').style.opacity = "1", 50);
                
                typeWriter();
                startLoveRain(); // This starts the 1,000 "I love you"s raining
            }, 600);
        }

        let charIdx = 0;
        function typeWriter() {
            if (charIdx < fullLetter.length) {
                document.getElementById('letterText').innerHTML += fullLetter.charAt(charIdx);
                charIdx++;
                setTimeout(typeWriter, 35);
            }
        }

        function startLoveRain() {
            let rainCount = 0;
            const totalDrops = 1000;
            
            const rainInterval = setInterval(() => {
                if (rainCount >= totalDrops) {
                    clearInterval(rainInterval);
                    return;
                }
                createDrop();
                rainCount++;
            }, 100); // New "I love you" every 100ms
        }

        function createDrop() {
            const drop = document.createElement('div');
            drop.className = 'rain-drop';
            drop.textContent = 'I love you';
            
            // Random horizontal position
            drop.style.left = Math.random() * 100 + 'vw';
            
            // Random fall speed for variety
            const duration = Math.random() * 3 + 4; // 4 to 7 seconds
            drop.style.animationDuration = duration + 's';
            
            // Random transparency/glow
            drop.style.opacity = Math.random() * 0.5 + 0.2;
            drop.style.fontSize = Math.random() * 10 + 12 + 'px';
            
            document.body.appendChild(drop);
            
            // Remove from memory after it falls
            setTimeout(() => { drop.remove(); }, duration * 1000);
        }
    </script>
</body>
</html>
