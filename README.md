<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎂 Birthday! 🎂</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Press Start 2P', cursive;
            background: 
                linear-gradient(45deg, 
                    #2c1810 0%, #3d2817 25%, 
                    #4a3728 50%, #5d4037 75%, #6d4c41 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
            position: relative;
            image-rendering: pixelated;
            image-rendering: crisp-edges;
        }
        
        .pixel-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 25% 25%, rgba(255, 255, 255, 0.1) 1px, transparent 1px),
                radial-gradient(circle at 75% 75%, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
            background-size: 8px 8px;
            pointer-events: none;
            z-index: 1;
        }
        
        .birthday-title {
            font-size: 2rem;
            color: #ffeb3b;
            text-shadow: 
                2px 2px 0px #ff5722,
                4px 4px 0px #4868f8,
                6px 6px 8px rgba(0, 0, 0, 0.6);
            margin: 20px 0;
            animation: pixel-bounce 1.7s infinite;
            text-align: center;
            letter-spacing: 2px;
            position: relative;
            z-index: 4;
        }
        
        @keyframes pixel-bounce {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-10px);
            }
        }
        
        .content-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            width: 100%;
            max-width: 1100px;
            padding: 60px 40px;
            margin: 0 auto;
    
        }
        
        .left-panel, .right-panel {
            flex: 1;
            min-width: 400px;
            display: flex;
            flex-direction: column;
            gap: 60px;
            padding: 30px; 
            max-width: 600px;
        }

        
        /* Future Letter Styles */
        .future-letter {
            background: rgba(30, 30, 30, 0.9);
            border: 4px solid #5d4037;
            padding: 20px;
            position: relative;
            z-index: 2;
            display: none;
        }
        
        .future-letter.visible {
            display: block;
            animation: letter-appear 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        
        @keyframes letter-appear {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        
        .letter-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 4px solid #5d4037;
        }
        
        .letter-title {
            color: #ffeb3b;
            font-size: 14px;
            text-shadow: 2px 2px 0px #4937eb;
        }
        
        .letter-date {
            color: #0c0502;
            font-size: 10px;
        }
        
        .letter-content {
            color: #fffcf6;
            font-size: 10px;
            line-height: 1.8;
            white-space: pre-wrap;
            margin-bottom: 15px; 
        }
        
        .letter-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
            padding-top: 10px;
            border-top: 2px solid #5d4037;
            font-size: 8px;
            color: #a0614a;
        }
        
        .letter-close {
            background: #5d4037;
            border: none;
            color: #fff3e0;
            padding: 5px 10px;
            font-family: 'Press Start 2P', cursive;
            font-size: 8px;
            cursor: pointer;
        }
        
        /* Future Form Styles */
        .future-form {
            background: rgba(77, 41, 35, 0.8);
            border: 4px solid #262758;
            padding: 20px;
            position: relative;
            z-index: 2;
        }
        
        .future-form h2 {
            color: #ffeb3b;
            font-size: 14px;
            margin-bottom: 15px;
            text-align: center;
            text-shadow: 2px 2px 0px #384fcf;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-label {
            display: block;
            color: hsl(36, 100%, 96%);
            font-size: 13px;
            margin-bottom: 7px;
        }
        
        .future-form textarea {
            width: 100%;
            height: 200px;
            background: rgba(61, 57, 100, 0.603);
            border: 2px solid #5d4037;
            color: #fff3e0;
            font-family: 'Press Start 2P', cursive;
            font-size: 10px;
            padding: 10px;
            resize: none;
        }
        
        .future-form select {
            width: 100%;
            background: rgba(61, 57, 100, 0.603);
            border: 2px solid #5d4037;
            color: #fff3e0;
            font-family: 'Press Start 2P', cursive;
            font-size: 10px;
            padding: 10px;
            margin-bottom: 20px;
        }
        
        .future-form button {
            width: 100%;
            margin-top: 20px;
        }
        
        /* Cake Styles */
        .cake-container {
            position: relative;
            margin: 20px 0;
            animation: cake-spawn 0.7s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            z-index: 2;
        }
        
        @keyframes cake-spawn {
            0% {
                transform: scale(0);
                opacity: 0;
            }
            100% {
                transform: scale(1);
                opacity: 1;
            }
        }
        
        .cake {
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            filter: drop-shadow(4px 4px 0px rgba(13, 6, 77, 0.8));
        }
        
        .cake-layer {
            position: relative;
            margin-bottom: -4px;
            image-rendering: pixelated;
        }
        
        .cake-layer-1 {
            width: 200px;
            height: 50px;
            background: 
                linear-gradient(90deg, 
                    #e4f168 0%, #8d6e63 12.5%,
                    #795548 12.5%, #795548 25%,
                    #e4f168 0%, #8d6e63 62.5%,
                    #795548 37.5%, #795548 50%,
                    #8d6e63 50%, #8d6e63 62.5%,
                    #e4f168 0%, #8d6e63 62.5%,
                    #8d6e63 75%, #8d6e63 65.5%,
                   #e4f168 0%, #8d6e63 100%);
            border: 6px solid #5d4037;
            position: relative;
        }
        
        .cake-layer-2 {
            width: 136px;
            height: 40px;
            background: 
                linear-gradient(90deg, 
                    #e91e63 0%, #e91e63 16.66%,
                    #c2185b 16.66%, #c2185b 33.33%,
                    #e91e63 33.33%, #e91e63 50%,
                    #c2185b 50%, #c2185b 66.66%,
                    #e91e63 66.66%, #e91e63 83.33%,
                    #c2185b 83.33%, #c2185b 100%);
            border: 4px solid #5d4037;
            z-index: 2;
        }
        
        .frosting {
            position: absolute;
            top: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 110%;
            height: 13px;
            background: 
                linear-gradient(90deg, 
                    #fff3e0 0%, #fff3e0 25%,
                    #ffe0b2 25%, #ffe0b2 50%,
                    #fff3e0 50%, #fff3e0 75%,
                    #ffe0b2 75%, #ffe0b2 100%);
            background-size: 8px 8px;
            z-index: 2;
        }
        
        .candles-container {
            position: absolute;
            top: -28px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 16px;
            z-index: 10;
        }
        
        .candle {
            position: relative;
            width: 8px;
            height: 32px;
            background: 
                linear-gradient(180deg, 
                    #ffeb3b 0%, #ffeb3b 25%,
                    #ffc107 25%, #ffc107 50%,
                    #ffeb3b 50%, #ffeb3b 75%,
                    #ffc107 75%, #ffc107 100%);
            image-rendering: pixelated;
        }
        
        .candle:nth-child(even) {
            background: 
                linear-gradient(180deg, 
                    #e91e63 0%, #e91e63 25%,
                    #c2185b 25%, #c2185b 33.33%,
                    #e91e63 33.33%, #e91e63 50%,
                    #c2185b 50%, #c2185b 66.66%,
                    #e91e63 66.66%, #e91e63 83.33%,
                    #c2185b 83.33%, #c2185b 100%);
        }
        
        .flame {
            position: absolute;
            top: -12px;
            left: 45%;
            transform: translateX(-60%);
            width: 9px;
            height: 9px;
            background: 
                radial-gradient(circle, 
                    #ffeb3b 0%, #ffeb3b 30%,
                    #ff9800 30%, #ff9800 60%,
                    #ff5722 60%, #ff5722 100%);
            animation: pixel-flame 0.9s infinite;
            transition: opacity 0.10s ease;
            image-rendering: pixelated;
        }
        
        .flame::after {
            content: '';
            position: absolute;
            top: -4px;
            left: 2px;
            width: 4px;
            height: 4px;
            background: #ffc547;
            animation: pixel-flame-tip 0.10s infinite alternate;
        }
        
        .flame.blown-out {
            opacity: 0;
            animation: none;
        }
        
        .flame.blown-out::after {
            display: none;
        }
        
        @keyframes pixel-flame {
            0%, 100% {
                transform: translateX(-50%) scale(1);
            }
            50% {
                transform: translateX(-50%) scale(1.2);
            }
        }
        
        @keyframes pixel-flame-tip {
            0% {
                transform: translate(0px, 0px);
            }
            100% {
                transform: translate(1px, -1px);
            }
        }
        
        /* Controls */
        .controls {
            margin: 20px 0;
            text-align: center;
            z-index: 2;
            position: relative;
        }
        
        .pixel-button {
            background: linear-gradient(135deg, #4caf50 0%, #388e3c 100%);
            border: 4px solid #2e7d32;
            color: #ffffff;
            padding: 15px 30px;
            font-size: 10px;
            font-family: 'Press Start 2P', cursive;
            cursor: pointer;
            margin: 10px;
            transition: all 0.15s ease;
            text-transform: uppercase;
            letter-spacing: 3px;
            position: relative;
            image-rendering: pixelated;
        }
        
        .pixel-button:hover {
            background: linear-gradient(135deg, #66bb6a 0%, #4caf50 100%);
            transform: translate(-2px, -2px);
            box-shadow: 2px 2px 0px #2e7d32;
        }
        
        .pixel-button:active {
            transform: translate(0px, 0px);
            box-shadow: none;
        }
        
        .mic-button {
            background: linear-gradient(135deg, #f44336 0%, #d32f2f 100%);
            border: 4px solid #c62828;
        }
        
        .mic-button:hover {
            background: linear-gradient(135deg, #ef5350 0%, #f44336 100%);
            box-shadow: 2px 2px 0px #c62828;
        }
        
        .mic-button.recording {
            background: linear-gradient(135deg, #ff1744 0%, #d50000 100%);
            animation: pixel-pulse 1s infinite;
        }
        
        @keyframes pixel-pulse {
            0% {
                transform: translate(-2px, -2px) scale(1);
            }
            50% {
                transform: translate(-2px, -2px) scale(1.05);
            }
            100% {
                transform: translate(-2px, -2px) scale(1);
            }
        }
        
        /* Mixtape Player */
        .mixtape-player {
            width: 100%;
            height: 585px;
            border: none;
            margin-top: 30px;
        }
        
        /* Wish Card */
        .wish-card {
            background: rgb(71, 44, 40);
            border: 4px solid #262758;
            padding: 20px;
            margin-bottom: 30px;
            position: relative;
            z-index: 2;
        }
        
        .wish-card h2 {
            color: #ffeb3b;
            font-size: 14px;
            margin-bottom: 15px;
            text-align: center;
            text-shadow: 2px 2px 0px #ff5722;
        }
        
        .wish-card p {
            color: #fff3e0;
            font-size: 10px;
            line-height: 1.5;
            margin-bottom: 15px;
        }
        
        /* Instructions */
        .instructions {
            background: #3e2723;
            border: 4px solid #5d4037;
            padding: 16px;
            margin: 16px 0;
            text-align: center;
            font-size: 10px;
            color: #fff3e0;
            letter-spacing: 1px;
            line-height: 1.6;
            position: relative;
            z-index: 2;
        }
        
        .instructions::before {
            content: '★ INSTRUCTIONS ★';
            position: absolute;
            top: -8px;
            left: 16px;
            background: #3e2723;
            color: #ffeb3b;
            padding: 0 8px;
            font-size: 8px;
        }
        
        /* Volume Indicator */
        .volume-indicator {
            width: 160px;
            height: 16px;
            background: #3e2723;
            border: 2px solid #5d4037;
            margin: 16px auto;
            overflow: hidden;
            position: relative;
            z-index: 2;
            display: none;
        }
        
        .volume-bar {
            height: 100%;
            background: 
                linear-gradient(90deg, 
                    #4caf50 0%, #4caf50 25%,
                    #8bc34a 25%, #8bc34a 50%,
                    #4caf50 50%, #4caf50 75%,
                    #8bc34a 75%, #8bc34a 100%);
            width: 0%;
            transition: width 0.1s ease;
            background-size: 8px 8px;
        }
        
        /* Celebration Message */
        .celebration-message {
            font-size: 12px;
            color: #ffeb3b;
            text-align: center;
            margin: 16px 0;
            opacity: 0;
            transform: translateY(16px);
            transition: all 0.5s ease;
            letter-spacing: 2px;
            text-shadow: 2px 2px 0px #ff5722;
            z-index: 2;
            position: relative;
        }
        
        .celebration-message.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Confetti */
        .confetti {
            position: fixed;
            pointer-events: none;
            z-index: 1000;
            animation: pixel-confetti-fall 60s ease-out forwards;
            font-size: 30px;
            image-rendering: pixelated;
        }
        
        @keyframes pixel-confetti-fall {
            0% {
                transform: translateY(-100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(180deg);
                opacity: 0;
            }
        }
        
        /* Decorations */
        .decorations {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        
        .pixel-star {
            position: absolute;
            font-size: 16px;
            color: #ffeb3b;
            animation: pixel-twinkle 10s infinite;
            text-shadow: 1px 1px 0px #ff5722;
        }
        
        .pixel-star:nth-child(1) {
            top: 15%;
            left: 10%;
            animation-delay: 0s;
        }
        
        .pixel-star:nth-child(2) {
            top: 25%;
            right: 15%;
            animation-delay: 0.5s;
        }
        
        .pixel-star:nth-child(3) {
            bottom: 35%;
            left: 8%;
            animation-delay: 1s;
        }
        
        .pixel-star:nth-child(4) {
            bottom: 25%;
            right: 12%;
            animation-delay: 1.5s;
        }
        
        .pixel-star:nth-child(5) {
            top: 40%;
            left: 20%;
            animation-delay: 0.8s;
        }
        
        .pixel-star:nth-child(6) {
            top: 60%;
            right: 25%;
            animation-delay: 1.2s;
        }
        
        @keyframes pixel-twinkle {
            0%, 100% {
                opacity: 0.6;
                transform: scale(1);
            }
            50% {
                opacity: 1;
                transform: scale(1.2);
            }
        }
        
        /* Cozy Glow */
        .cozy-glow {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(255, 235, 59, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            z-index: 0;
            animation: cozy-pulse 4s ease-in-out infinite;
        }
        
        @keyframes cozy-pulse {
            0%, 100% {
                transform: translate(-50%, -50%) scale(1);
                opacity: 0.3;
            }
            50% {
                transform: translate(-50%, -50%) scale(1.1);
                opacity: 0.1;
            }
        }
        
        /* Creator Credit */
        .creator-credit {
            font-size: 15px;
            color: #f7f5f2;
            margin-top: 20px;
            text-align: top;
            z-index: 2;
            position: relative;
            opacity: 12;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .birthday-title {
                font-size: 1.5rem;
                margin: 16px;
            }
            
            .content-container {
                flex-direction: column;
                padding: 10px;
            }
            
            .left-panel, .right-panel {
                min-width: 100%;
            }
            
            .cake-layer-1 {
                width: 160px;
                height: 40px;
            }
            
            .cake-layer-2 {
                width: 112px;
                height: 32px;
            }
            
            .instructions {
                margin: 8px 0;
                padding: 12px;
                font-size: 6px;
            }
            
            .pixel-button {
                padding: 8px 16px;
                font-size: 8px;
                margin: 4px;
            }
            
            .candles-container {
                gap: 12px;
            }
            
            .candle {
                width: 6px;
                height: 24px;
            }
            
            .flame {
                width: 6px;
                height: 6px;
                top: -8px;
            }
            
            .wish-card h2, .future-form h2, .letter-title {
                font-size: 12px;
            }
            
            .wish-card p, .letter-content {
                font-size: 8px;
            }
            
            .mixtape-player {
                height: 200px;
         
            }
        }
    </style>
</head>
<body>
    
    <div class="pixel-overlay"></div>
    <div class="cozy-glow"></div>
    
    <div class="decorations">
        <div class="pixel-star">★</div>
        <div class="pixel-star">★</div>
        <div class="pixel-star">★</div>
        <div class="pixel-star">★</div>
        <div class="pixel-star">★</div>
        <div class="pixel-star">★</div>

</div>

    </div>

    <h1 class="birthday-title">HAPPY 21st BIRTHDAY BERKY</h1>
    
    <div class="content-container">
        <div class="left-panel">
            <iframe class="mixtape-player" src="https://mewtru.com/mixtape/playback?v=1uORSiEOd7o%2CtNjZndIA6F8%2CmmtcEJZHB-o%2CpKFd12id5oQ%2CYP7ghF9pwys&to=berky"
                    frameborder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" 
                    loading="lazy"></iframe>
            
            <div class="wish-card">
                <h2>⋆. 𐙚˚࿔ Hey B 𝜗𝜚˚⋆</h2>
                <p>Finally your official first year of the twenties, how's your birthday celebration going? i hope life serves you well at this moment</p>
                <p>We may have just met, but I'm glad our paths crossed. Somehow, knowing you already feels like rediscovering color in a life that was running low on brightness.</p>
                <p>As you step into 21, may serenity meet your storms, unexpected beauty in the mundane, and may happiness gently settle beside you even on the stillest days</p>
                <p>May your dreams rise like quiet prayers, and may each one—no matter how distant—be answered by time with solemn grace</p>
                <p>It's a privilege to be on Earth at the same time as you.
                <p>In storms that shake what you believe, May you still find quiet reprieve
                   <p>Once again, happy birthday, bless you & long live.</p>
                <p>───────୨୧ ──────── ୨୧ ───────── ୨୧ ──────── ୨୧ ──── ୨୧</p>
            </div>
        </div>
        
        <div class="right-panel">
            <div class="instructions">
                <p>MAKE A WISH & BLOW THE CANDLE</p>
                <p>꒷꒦︶꒷꒦︶ ๋ ࣭ ⭑꒷꒦꒷꒦︶꒷꒦︶ ๋ ࣭ ⭑꒷꒦꒷꒦︶꒷꒦︶ ๋ ࣭ ⭑꒷꒦</p>
            </div>
            
            <div class="cake-container">
                <div class="cake">
                    <div class="candles-container" id="candlesContainer">
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                        <div class="candle">
                            <div class="flame"></div>
                        </div>
                    </div>
                    
                    <div class="cake-layer cake-layer-2">
                        <div class="frosting"></div>
                    </div>
                    <div class="cake-layer cake-layer-1">
                        <div class="frosting"></div>
                    </div>
                </div>
            </div>
            
            <div class="controls">
                <button class="pixel-button mic-button" id="micButton" onclick="toggleMicrophone()">USE MIC</button>
                <button class="pixel-button" onclick="blowCandles()">CLICK ME</button>
                
            </div>
            
            <div class="volume-indicator" id="volumeIndicator">
                <div class="volume-bar" id="volumeBar"></div>
            </div>
            
            <div class="celebration-message" id="celebrationMessage">
                <p>★THE MIC ISN'T WORKING?</p>
                   <p></p> THAT'S OKAY</p>
                <p>MAY ALL YOUR WISHES COME TRUE★</p>
            </div>
            
            <!-- Future Form -->
            <div class="future-form" id="futureForm">
                <h2>★ WRITE YOUR FUTURE SELF A LETTER★</h2>
                <div class="form-group">
                 <form action="https://formspree.io/f/yourFormIdHere" method="POST" id="futureForm">
                    <label class="form-label">Add your email before write the letter here:</label>
  <textarea name="letter" rows="10" cols="40" placeholder="Dear Future Me..." required></textarea>

  <br><br>

  <input type="email" name="email" placeholder="Your email">
  
  <br><br>
</form>

                </div>
                <div class="form-group">
                    <label class="form-label">DELIVER IN:</label>
                    <select id="deliveryTime">
                        <option value="1">1 Year</option>
                        <option value="2">2 Years</option>
                        <option value="3">3 Years</option>
                        <option value="5">5 Years</option>
                    </select>
                </div>
                <button class="pixel-button" onclick="saveFutureLetter()">SEAL LETTER</button>
                <button class="pixel-button" onclick="viewSavedLetter()" id="viewLetterBtn" style="display: none;">VIEW SAVED LETTER</button>
            </div>
            
            <!-- Future Letter Display -->
            <div class="future-letter" id="futureLetter">
                <div class="letter-header">
                    <div class="letter-title">LETTER TO FUTURE SELF</div>
                    <div class="letter-date" id="letterDate"></div>
                </div>
                <div class="letter-content" id="letterContent"></div>
                <div class="letter-footer">
                    <div class="letter-delivery" id="letterDelivery"></div>
                    <button class="letter-close" onclick="closeLetter()">CLOSE</button>
                </div>
            </div>
        </div>
    </div>
    
    <div class="creator-credit">created by Audi</div>

    <script>
        let candlesLit = 5;
        let isRecording = false;
        let audioContext;
        let microphone;
        let analyser;
        let dataArray;
        let animationId;
        
        // 8-bit style click sound
        function playClickSound() {
            const audioContext = new (window.AudioContext || window.webkitAudioContext)();
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.type = 'square';
            oscillator.frequency.setValueAtTime(880, audioContext.currentTime);
            oscillator.frequency.exponentialRampToValueAtTime(440, audioContext.currentTime + 0.1);
            
            gainNode.gain.setValueAtTime(0.1, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.1);
            
            oscillator.start(audioContext.currentTime);
            oscillator.stop(audioContext.currentTime + 0.1);
        }
        
        // 8-bit style blow sound
        function playBlowSound() {
            const audioContext = new (window.AudioContext || window.webkitAudioContext)();
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.type = 'sawtooth';  
            oscillator.frequency.setValueAtTime(200, audioContext.currentTime);
            oscillator.frequency.exponentialRampToValueAtTime(50, audioContext.currentTime + 0.5);
            
            gainNode.gain.setValueAtTime(0.05, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.5);
            
            oscillator.start(audioContext.currentTime);
            oscillator.stop(audioContext.currentTime + 0.5);
        }
        
        // Create pixel-style confetti
        function createConfetti() {
            const pixelConfetti = ['◆', '◇', '●', '○', '■', '□', '▲', '△', '♦', '★', '☆'];
            const colors = ['#ffeb3b', '#ff5722', '#4caf50', '#2196f3', '#e91e63', '#ff9800'];
            
            for (let i = 0; i < 60; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.className = 'confetti';
                    confetti.textContent = pixelConfetti[Math.floor(Math.random() * pixelConfetti.length)];
                    confetti.style.color = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.left = Math.random() * 100 + 'vw';
                    confetti.style.animationDelay = Math.random() * 2 + 's';
                    confetti.style.animationDuration = (Math.random() * 2 + 2) + 's';
                    document.body.appendChild(confetti);
                    
                    setTimeout(() => confetti.remove(), 5000);
                }, i * 80);
            }
        }
        
        // Blow out candles function
        function blowCandles() {
            if (candlesLit <= 0) return;
            
            playClickSound();
            playBlowSound();
            
            const flames = document.querySelectorAll('.flame');
            const randomFlame = flames[Math.floor(Math.random() * flames.length)];
            
            if (randomFlame && !randomFlame.classList.contains('blown-out')) {
                randomFlame.classList.add('blown-out');
                candlesLit--;
                
                if (candlesLit === 0) {
                    setTimeout(() => {
                        createConfetti();
                        document.getElementById('celebrationMessage').classList.add('show');
                    }, 500);
                }
            }
        }
        
        // Microphone functionality
        async function toggleMicrophone() {
            const micButton = document.getElementById('micButton');
            const volumeIndicator = document.getElementById('volumeIndicator');
            
            if (!isRecording) {
                try {
                    const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
                    setupAudioAnalysis(stream);
                    
                    micButton.textContent = 'STOP MIC';
                    micButton.classList.add('recording');
                    volumeIndicator.style.display = 'block';
                    isRecording = true;
                } catch (error) {
                    alert('Microphone access denied. Please allow microphone access and try again.');
                    console.error('Error accessing microphone:', error);
                }
            } else {
                stopMicrophone();
            }
        }
        
        function setupAudioAnalysis(stream) {
            audioContext = new (window.AudioContext || window.webkitAudioContext)();
            analyser = audioContext.createAnalyser();
            microphone = audioContext.createMediaStreamSource(stream);
            
            analyser.fftSize = 256;
            const bufferLength = analyser.frequencyBinCount;
            dataArray = new Uint8Array(bufferLength);
            
            microphone.connect(analyser);
            
            checkAudioLevel();
            
        }
        
        function checkAudioLevel() {
            if (!isRecording) return;
            
            analyser.getByteFrequencyData(dataArray);
            
            let sum = 0;
            for (let i = 0; i < dataArray.length; i++) {
                sum += dataArray[i];
            }
            const average = sum / dataArray.length;
            
            // Update volume indicator
            const volumeBar = document.getElementById('volumeBar');
            const volumePercent = Math.min((average / 50) * 100, 100);
            volumeBar.style.width = volumePercent + '%';
            
            // Check if blow detected (high volume)
            if (average > 10 && candlesLit > 0) {
                blowCandleWithMic();
            }
            
            animationId = requestAnimationFrame(checkAudioLevel);
        }
        
        function blowCandleWithMic() {
            const flames = document.querySelectorAll('.flame:not(.blown-out)');
            if (flames.length === 0) return;
            
            const randomFlame = flames[Math.floor(Math.random() * flames.length)];
            randomFlame.classList.add('blown-out');
            candlesLit--;
            
            playBlowSound();
            
            if (candlesLit === 0) {
                stopMicrophone();
                setTimeout(() => {
                    createConfetti();
                    document.getElementById('celebrationMessage').classList.add('show');
                }, 500);
            }
        }
        
        function stopMicrophone() {
            isRecording = false;
            
            if (microphone && microphone.mediaStream) {
                microphone.mediaStream.getTracks().forEach(track => track.stop());
            }
            
            if (audioContext) {
                audioContext.close();
            }
            
            if (animationId) {
                cancelAnimationFrame(animationId);
            }
            
            const micButton = document.getElementById('micButton');
            const volumeIndicator = document.getElementById('volumeIndicator');
            
            micButton.textContent = 'USE MIC';
            micButton.classList.remove('recording');
            volumeIndicator.style.display = 'none';
        }
        
        // Future Letter Functions
        function saveFutureLetter() {
            const message = document.getElementById('futureMessage').value.trim();
            const deliveryYears = document.getElementById('deliveryTime').value;
            
            if (!message) {
                alert('Please write a message to your future self!');
                return;
            }
            
            const today = new Date();
            const deliveryDate = new Date();
            deliveryDate.setFullYear(today.getFullYear() + parseInt(deliveryYears));
            
            const letterData = {
                message: message,
                created: today.toISOString(),
                delivery: deliveryDate.toISOString(),
                deliveryYears: deliveryYears
            };
            
            localStorage.setItem('futureLetter', JSON.stringify(letterData));
            playClickSound();
            
            // Show the view letter button
            document.getElementById('viewLetterBtn').style.display = 'block';
            
            alert(`Letter saved! It will be delivered to you in ${deliveryYears} year${deliveryYears > 1 ? 's' : ''}.`);
        }
        
        function viewSavedLetter() {
            const savedLetter = localStorage.getItem('futureLetter');
            if (!savedLetter) return;
            
            const letterData = JSON.parse(savedLetter);
            const createdDate = new Date(letterData.created);
            const deliveryDate = new Date(letterData.delivery);
            
            // Format dates
            const options = { year: 'numeric', month: 'long', day: 'numeric' };
            const createdStr = createdDate.toLocaleDateString('en-US', options);
            const deliveryStr = deliveryDate.toLocaleDateString('en-US', options);
            
            // Display the letter
            document.getElementById('letterContent').textContent = letterData.message;
            document.getElementById('letterDate').textContent = `Written on ${createdStr}`;
            document.getElementById('letterDelivery').textContent = `Scheduled for ${deliveryStr}`;
            
            // Show the letter and hide the form
            document.getElementById('futureForm').style.display = 'none';
            document.getElementById('futureLetter').classList.add('visible');
            playClickSound();
        }
        
        function closeLetter() {
            document.getElementById('futureLetter').classList.remove('visible');
            document.getElementById('futureForm').style.display = 'block';
            playClickSound();
        }
        
        // Check for saved letter on load
        window.addEventListener('DOMContentLoaded', () => {
            const savedLetter = localStorage.getItem('futureLetter');
            if (savedLetter) {
                document.getElementById('viewLetterBtn').style.display = 'block';
            }
            
            // Add click sound to all buttons
            document.querySelectorAll('button').forEach(button => {
                button.addEventListener('click', playClickSound);
            });
            
            // Auto-create some confetti on page load
            setTimeout(() => {
                createConfetti();
            }, 1000);
        });
        
        // Cleanup on page unload
        window.addEventListener('beforeunload', () => {
            if (isRecording) {
                stopMicrophone();
            }
        });
    </script>
    <script>
  const form = document.getElementById("futureForm");
  form.addEventListener("submit", function (e) {
    e.preventDefault();
    fetch(form.action, {
      method: "POST",
      body: new FormData(form),
      headers: { Accept: "application/json" }
    })
    .then(() => {
      form.innerHTML = "<p>📩 Thanks! Your letter has been sent.</p>";
    })
    .catch(() => {
      form.innerHTML = "<p>❌ Oops! Something went wrong. Try again later.</p>";
    });
  });
</script>
</body>
</body>
</html>
