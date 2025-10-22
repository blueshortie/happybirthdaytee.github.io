<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Tee!</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            color: white;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            text-align: center;
            position: relative;
            z-index: 10;
        }
        
        header {
            margin-bottom: 3rem;
            animation: fadeIn 1.5s ease-out;
        }
        
        h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            text-shadow: 0 0 15px rgba(255, 255, 255, 0.5);
            background: linear-gradient(to right, #ffd700, #ffed4e, #ffd700);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .subtitle {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        
        .birthday-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            margin: 2rem auto;
            max-width: 800px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: slideUp 1s ease-out;
        }
        
        .message {
            font-size: 1.3rem;
            line-height: 1.6;
            margin-bottom: 2rem;
            text-align: left;
        }
        
        .cake-container {
            position: relative;
            margin: 3rem auto;
            width: 300px;
            height: 200px;
        }
        
        .cake {
            position: absolute;
            width: 200px;
            height: 80px;
            background: #f8c8dc;
            border-radius: 10px 10px 0 0;
            bottom: 0;
            left: 50px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .cake:before {
            content: '';
            position: absolute;
            width: 220px;
            height: 20px;
            background: #ff9ec0;
            border-radius: 10px;
            bottom: 80px;
            left: -10px;
        }
        
        .cake:after {
            content: '';
            position: absolute;
            width: 240px;
            height: 20px;
            background: #ff7ba9;
            border-radius: 10px;
            bottom: 100px;
            left: -20px;
        }
        
        .candle {
            position: absolute;
            width: 10px;
            height: 40px;
            background: #ff6b6b;
            border-radius: 5px;
            bottom: 120px;
            left: 95px;
            z-index: 5;
        }
        
        .flame {
            position: absolute;
            width: 15px;
            height: 25px;
            background: #ffd700;
            border-radius: 50% 50% 20% 20%;
            bottom: 160px;
            left: 92.5px;
            animation: flicker 1.5s infinite alternate;
            box-shadow: 0 0 15px #ff9500, 0 0 30px #ff9500;
        }
        
        .decoration {
            position: absolute;
            width: 15px;
            height: 15px;
            background: #ff6b6b;
            border-radius: 50%;
            bottom: 110px;
            left: 50px;
            box-shadow: 
                40px 0 0 #4cd964,
                80px 0 0 #5ac8fa,
                120px 0 0 #ffcc00,
                160px 0 0 #ff9500;
        }
        
        .balloons {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 2rem 0;
        }
        
        .balloon {
            width: 60px;
            height: 70px;
            border-radius: 50%;
            position: relative;
            animation: float 6s ease-in-out infinite;
        }
        
        .balloon:before {
            content: '';
            position: absolute;
            width: 2px;
            height: 80px;
            background: white;
            bottom: -80px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .balloon:nth-child(1) {
            background: #ff2d55;
            animation-delay: 0s;
        }
        
        .balloon:nth-child(2) {
            background: #5ac8fa;
            animation-delay: 0.5s;
        }
        
        .balloon:nth-child(3) {
            background: #4cd964;
            animation-delay: 1s;
        }
        
        .balloon:nth-child(4) {
            background: #ffcc00;
            animation-delay: 1.5s;
        }
        
        .balloon:nth-child(5) {
            background: #ff9500;
            animation-delay: 2s;
        }
        
        .gifts {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 3rem 0;
        }
        
        .gift {
            width: 80px;
            height: 80px;
            position: relative;
            animation: bounce 2s infinite;
            cursor: pointer;
        }
        
        .gift-box {
            width: 80px;
            height: 60px;
            background: #ff2d55;
            position: relative;
        }
        
        .gift-box:before {
            content: '';
            position: absolute;
            width: 100%;
            height: 20px;
            background: #ff6b6b;
            top: 20px;
        }
        
        .gift-box:after {
            content: '';
            position: absolute;
            width: 20px;
            height: 60px;
            background: #ff6b6b;
            left: 30px;
        }
        
        .gift-lid {
            width: 90px;
            height: 20px;
            background: #ff6b6b;
            position: absolute;
            top: -10px;
            left: -5px;
        }
        
        .gift:nth-child(2) .gift-box {
            background: #5ac8fa;
        }
        
        .gift:nth-child(2) .gift-box:before,
        .gift:nth-child(2) .gift-box:after,
        .gift:nth-child(2) .gift-lid {
            background: #87ceeb;
        }
        
        .gift:nth-child(3) .gift-box {
            background: #4cd964;
        }
        
        .gift:nth-child(3) .gift-box:before,
        .gift:nth-child(3) .gift-box:after,
        .gift:nth-child(3) .gift-lid {
            background: #7cfc00;
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background: #ffcc00;
            border-radius: 50%;
            opacity: 0.8;
            animation: confettiFall 5s linear infinite;
        }
        
        .footer {
            margin-top: 3rem;
            font-size: 1.2rem;
            opacity: 0.8;
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        @keyframes flicker {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }
        
        @keyframes confettiFall {
            0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            h1 { font-size: 2.5rem; }
            .subtitle { font-size: 1.2rem; }
            .birthday-card { padding: 2rem; }
            .message { font-size: 1.1rem; }
            .cake-container { transform: scale(0.8); }
        }
    </style>
</head>
<body>
    <!-- Confetti -->
    <div id="confetti-container"></div>
    
    <div class="container">
        <header>
            <h1>Happy Birthday Thanush!</h1>
            <p class="subtitle">Wishing you a day filled with joy, laughter, and wonderful moments!</p>
        </header>
        
        <div class="balloons">
            <div class="balloon"></div>
            <div class="balloon"></div>
            <div class="balloon"></div>
            <div class="balloon"></div>
            <div class="balloon"></div>
        </div>
        
        <div class="birthday-card">
            <div class="message">
                <p>Dear Thanush,</p>
                <br>
                <p>On your special day, I wanted to create something as unique and wonderful as you are! May this birthday bring you endless happiness, success in all your endeavors, and memories that will last a lifetime.</p>
                <br>
                <p>You're an amazing friend, and I'm so grateful to have you in my life. Here's to celebrating you today and always!</p>
                <br>
                <p>With lots of love and best wishes,</p>
                <p>Your friend Tee</p>
            </div>
            
            <div class="cake-container">
                <div class="cake"></div>
                <div class="candle"></div>
                <div class="flame"></div>
                <div class="decoration"></div>
            </div>
        </div>
        
        <div class="gifts">
            <div class="gift">
                <div class="gift-lid"></div>
                <div class="gift-box"></div>
            </div>
            <div class="gift">
                <div class="gift-lid"></div>
                <div class="gift-box"></div>
            </div>
            <div class="gift">
                <div class="gift-lid"></div>
                <div class="gift-box"></div>
            </div>
        </div>
        
        <div class="footer">
            <p>Made with ❤️ for Thanush's special day</p>
        </div>
    </div>

    <script>
        // Create confetti
        function createConfetti() {
            const container = document.getElementById('confetti-container');
            const colors = ['#ffcc00', '#ff2d55, #5ac8fa', '#4cd964', '#ff9500', '#bf5af2'];
            
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.className = 'confetti';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.background = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.width = Math.random() * 10 + 5 + 'px';
                confetti.style.height = confetti.style.width;
                confetti.style.animationDelay = Math.random() * 5 + 's';
                confetti.style.animationDuration = (Math.random() * 3 + 3) + 's';
                container.appendChild(confetti);
            }
        }
        
        // Initialize when page loads
        window.onload = function() {
            createConfetti();
            
            // Add click effect to gifts
            const gifts = document.querySelectorAll('.gift');
            gifts.forEach(gift => {
                gift.addEventListener('click', function() {
                    this.style.transform = 'scale(1.2)';
                    setTimeout(() => {
                        this.style.transform = '';
                    }, 300);
                });
            });
        };
    </script>
</body>
</html>
