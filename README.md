<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>শুভ দীপাবলি</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"> <!-- Font Awesome for icons -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&family=Charm:wght@400;700&display=swap'); /* Added Charm font for religious feel */

        body {
            font-family: 'Poppins', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            background: linear-gradient(to bottom, #ffecd2 0%, #fcb69f 100%); /* Warm religious gradient */
            text-align: center;
            padding: 20px;
            box-sizing: border-box;
            overflow-x: hidden; /* Prevent horizontal scroll */
            position: relative; /* For fireworks */
        }
        .container {
            background-color: rgba(255, 255, 255, 0.9); /* Slightly translucent white */
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
            max-width: 550px;
            width: 100%;
            border: 3px solid #ff7e5f; /* Border for religious touch */
            animation: fadeIn 1s ease-out;
            position: relative;
            z-index: 10; /* Ensure container is above fireworks */
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        h1 {
            font-family: 'Charm', cursive; /* Religious font for greeting */
            color: #d42a2a;
            margin-bottom: 20px;
            font-size: 3em;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        #senderNameDisplay {
            font-family: 'Charm', cursive;
            color: #28a745;
            font-size: 2em;
            margin-bottom: 15px;
            min-height: 2em;
            font-weight: bold;
            animation: slideIn 0.8s ease-out;
        }
        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-50px); }
            to { opacity: 1; transform: translateX(0); }
        }
        img {
            max-width: 100%;
            height: auto;
            margin-bottom: 10px; /* Reduced margin to make space for good wishes */
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            border: 2px solid #ff7e5f;
            animation: bounceIn 1s ease-out;
        }
        @keyframes bounceIn {
            0% { transform: scale(0.5); opacity: 0; }
            50% { transform: scale(1.1); opacity: 1; }
            70% { transform: scale(0.9); }
            100% { transform: scale(1); }
        }
        .good-wishes {
            font-family: 'Poppins', sans-serif;
            font-size: 1.1em;
            color: #555;
            margin-bottom: 25px; /* Spacing below good wishes */
            line-height: 1.6;
        }
        label {
            font-size: 1.1em;
            color: #333;
            margin-bottom: 8px;
            display: block;
        }
        input[type="text"] {
            width: calc(100% - 24px);
            padding: 12px;
            margin-bottom: 18px;
            border: 1px solid #ff7e5f; /* Thematic border */
            border-radius: 8px;
            font-size: 1.1em;
            box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
        }
        .button-group {
            display: flex;
            justify-content: center;
            flex-wrap: wrap; /* Allow buttons to wrap on smaller screens */
            gap: 15px; /* Spacing between buttons */
            margin-top: 15px;
        }
        button {
            background-color: #ff7e5f; /* Thematic button color */
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.1em;
            font-weight: bold;
            transition: background-color 0.3s ease, transform 0.2s ease;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            display: inline-flex; /* For icon and text alignment */
            align-items: center;
            gap: 8px; /* Space between icon and text */
        }
        button:hover {
            background-color: #feb47b;
            transform: translateY(-2px);
        }
        .whatsapp-share-button {
            background-color: #25D366; /* WhatsApp green */
            padding: 15px 30px; /* Make it more prominent */
            font-size: 1.2em;
        }
        .whatsapp-share-button:hover {
            background-color: #1DA851;
        }
        /* Hidden elements are completely gone */
        .hidden {
            display: none !important; 
        }
        /* Fireworks effect styles */
        .fireworks {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 5; /* Below container */
        }
        .firework {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ffeb3b; /* Yellow spark */
            border-radius: 50%;
            opacity: 0;
            animation: fireworkExplode 1.5s forwards ease-out;
        }
        @keyframes fireworkExplode {
            0% { transform: scale(0) translate(0, 0); opacity: 1; }
            20% { opacity: 1; }
            100% { transform: scale(1.5) translate(var(--x), var(--y)); opacity: 0; }
        }
        /* Sparkle effect */
        .sparkle {
            position: absolute;
            background-color: white;
            opacity: 0;
            animation: sparkle 1s forwards ease-out;
            border-radius: 50%;
        }
        @keyframes sparkle {
            0% { transform: scale(0); opacity: 0.8; }
            100% { transform: scale(1.5); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="fireworks" id="fireworksContainer"></div>

    <div class="container">
        <h1 id="greetingText">শুভ দীপাবলি!</h1>
        <p id="senderNameDisplay"></p>
        
        <img src="laxmi.gif" alt="Laxmi Mata Animation"> 

        <p class="good-wishes">
            আলোর উৎসব দীপাবলির এই শুভক্ষণে, আপনার জীবন সুখ, সমৃদ্ধি ও আনন্দে ভরে উঠুক। দেবী লক্ষ্মী আপনার গৃহে শান্তি ও ঐশ্বর্য নিয়ে আসুক।
        </p>

        <label for="yourName">আপনার নাম লিখুন:</label>
        <input type="text" id="yourName" placeholder="আপনার নাম">
        
        <div class="button-group">
            <button onclick="shareViaWhatsApp()" class="whatsapp-share-button">
                <i class="fab fa-whatsapp"></i> WhatsApp এ শেয়ার করুন
            </button>
        </div>
        
        <!-- The following div is now completely hidden, as per your request -->
        <div id="shareOptionsContainer" class="hidden">
            <p style="margin-top: 20px; font-weight: bold; color: #d42a2a;">আপনার তৈরি লিঙ্ক:</p>
            <div id="shareLinkDisplay"></div>
            <button onclick="copyLink()" style="margin-top: 15px;">লিঙ্ক কপি করুন</button>
        </div>
    </div>

    <script>
        let currentShareLink = ''; 

        document.addEventListener('DOMContentLoaded', () => {
            const params = new URLSearchParams(window.location.search);
            const senderName = params.get('from');
            const senderNameDisplay = document.getElementById('senderNameDisplay');
            const greetingText = document.getElementById('greetingText');

            if (senderName) {
                greetingText.textContent = `শুভ দীপাবলি!`;
                senderNameDisplay.textContent = `${decodeURIComponent(senderName)} এর পক্ষ থেকে।`;
                setTimeout(createFireworksInitial, 500); 
            } else {
                greetingText.textContent = `শুভ দীপাবলি!`;
                senderNameDisplay.textContent = '';
            }
        });

        // This function is now private to the shareViaWhatsApp, as no other button calls it directly
        function generateLink() {
            const yourName = document.getElementById('yourName').value.trim();
            const baseUrl = window.location.origin + window.location.pathname;
            const shareLink = `${baseUrl}?from=${encodeURIComponent(yourName)}`;
            currentShareLink = shareLink;
        }

        // This function for copying link is still here in case you want to enable it later,
        // but the shareOptionsContainer is hidden by default.
        function copyLink() {
            const textToCopy = currentShareLink;
            
            navigator.clipboard.writeText(textToCopy).then(() => {
                alert('লিঙ্ক কপি করা হয়েছে!');
            }).catch(err => {
                console.error('লিঙ্ক কপি করতে ব্যর্থ:', err);
                alert('লিঙ্ক কপি করতে সমস্যা হয়েছে। অনুগ্রহ করে ম্যানুয়ালি কপি করুন।');
            });
        }

        // Function to share specifically via WhatsApp
        function shareViaWhatsApp() {
            const yourName = document.getElementById('yourName').value.trim();
            if (!yourName) {
                alert('অনুগ্রহ করে আপনার নাম লিখুন যাতে লিঙ্কটি তৈরি করা যায়!');
                return;
            }

            // Ensure the link is generated first
            generateLink(); 

            const shareText = `আপনাকে এবং আপনার পরিবারকে দীপাবলির শুভেচ্ছা! ${yourName} এর পক্ষ থেকে। এই লিঙ্কটিতে ক্লিক করে দেখুন:`;

            if (navigator.share) {
                navigator.share({
                    title: 'শুভ দীপাবলি শুভেচ্ছা!',
                    text: shareText,
                    url: currentShareLink,
                }).then(() => {
                    console.log('Successfully shared');
                }).catch((error) => {
                    console.error('Error sharing:', error);
                    // Fallback to WhatsApp Web URL if native share fails
                    window.open(`https://api.whatsapp.com/send?text=${encodeURIComponent(shareText)} ${encodeURIComponent(currentShareLink)}`, '_blank');
                });
            } else {
                // Direct fallback to WhatsApp Web URL
                window.open(`https://api.whatsapp.com/send?text=${encodeURIComponent(shareText)} ${encodeURIComponent(currentShareLink)}`, '_blank');
            }
        }

        // Fireworks Effect JavaScript - (unchanged)
        const initialFireworkCount = 45; 
        const repeatFireworkCount = 30;  

        function createFirework(x, y) {
            const fireworksContainer = document.getElementById('fireworksContainer');
            const firework = document.createElement('div');
            firework.className = 'firework';
            
            const colors = ['#ffeb3b', '#ff9800', '#f44336', '#e91e63', '#9c27b0', '#2196f3', '#03a9f4', '#FFD700', '#ADFF2F', '#FFFF00', '#FFA500']; 
            firework.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];

            firework.style.left = `${x}px`;
            firework.style.top = `${y}px`;

            const endX = (Math.random() - 0.5) * 500; 
            const endY = (Math.random() - 0.5) * 500; 

            firework.style.setProperty('--x', `${endX}px`);
            firework.style.setProperty('--y', `${endY}px`);

            fireworksContainer.appendChild(firework);

            for (let i = 0; i < 30; i++) { 
                const sparkle = document.createElement('div');
                sparkle.className = 'sparkle';
                sparkle.style.width = sparkle.style.height = `${Math.random() * 7 + 4}px`; 
                sparkle.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                
                const sparkleX = x + (Math.random() - 0.5) * 100; 
                const sparkleY = y + (Math.random() - 0.5) * 100;
                sparkle.style.left = `${sparkleX}px`;
                sparkle.style.top = `${sparkleY}px`;
                sparkle.style.animationDelay = `${Math.random() * 0.8}s`; 
                fireworksContainer.appendChild(sparkle);
                sparkle.addEventListener('animationend', () => sparkle.remove());
            }

            firework.addEventListener('animationend', () => firework.remove());
        }

        function createFireworksInitial() {
            for (let i = 0; i < initialFireworkCount; i++) {
                const randomX = Math.random() * window.innerWidth;
                const randomY = Math.random() * window.innerHeight * 0.7; 
                setTimeout(() => createFirework(randomX, randomY), i * 100); 
            }
            setTimeout(createFireworksRepeat, 5000); 
        }

        function createFireworksRepeat() {
             for (let i = 0; i < repeatFireworkCount; i++) {
                const randomX = Math.random() * window.innerWidth;
                const randomY = Math.random() * window.innerHeight * 0.7;
                setTimeout(() => createFirework(randomX, randomY), i * 200); 
            }
            setTimeout(createFireworksRepeat, 5000); 
        }
    </script>
</body>
</html>
<script type="text/javascript">
	atOptions = {
		'key' : 'd16d0c0cf367da58cd7827ba8d08b33c',
		'format' : 'iframe',
		'height' : 50,
		'width' : 320,
		'params' : {}
	};
</script>
<script type="text/javascript" src="//www.highperformanceformat.com/d16d0c0cf367da58cd7827ba8d08b33c/invoke.js"></script>
