<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>هديتك</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;700&display=swap');

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
            font-family: 'Tajawal', sans-serif;
            background: #121212;
            text-align: center;
            color: #fff;
            overflow: hidden;
            position: relative;
        }
        .sparkles {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }
        .sparkles span {
            position: absolute;
            width: 6px;
            height: 6px;
            background: #ffcc00;
            opacity: 0.7;
            border-radius: 50%;
            animation: sparkle 3s linear infinite;
        }
        @keyframes sparkle {
            from {
                transform: translateY(0);
                opacity: 0.7;
            }
            to {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }
        #gift-box {
            font-size: 70px;
            cursor: pointer;
            transition: transform 0.3s ease-in-out;
            animation: bounce 1.5s infinite;
        }
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        #gift-box:hover {
            transform: scale(1.1);
        }
        #message, #image, #button, #final-message, #footer, #next-button, #final-text {
            display: none;
        }
        #message {
            font-size: 24px;
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 10px;
            margin-top: 20px;
            animation: fadeIn 1s ease-in-out;
        }
        #button {
            background-color: #ffcc00;
            color: black;
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 20px;
            margin-top: 15px;
            transition: background 0.3s;
            box-shadow: 0px 4px 10px rgba(255, 204, 0, 0.5);
        }
        #button:hover {
            background-color: #ffaa00;
        }
        #image {
            width: 320px;
            margin-top: 20px;
            border-radius: 15px;
            box-shadow: 0px 4px 10px rgba(255, 204, 0, 0.5);
            animation: fadeIn 1s ease-in-out;
            display: none;
        }
        #final-message {
            font-size: 22px;
            margin-top: 20px;
            font-weight: bold;
            animation: fadeIn 1.5s ease-in-out;
        }
        #footer {
            margin-top: 30px;
            font-size: 14px;
            color: rgba(255, 255, 255, 0.8);
        }
        #next-button {
            background-color: #ffcc00;
            color: black;
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 20px;
            margin-top: 15px;
            transition: background 0.3s;
            box-shadow: 0px 4px 10px rgba(255, 204, 0, 0.5);
        }
        #next-button:hover {
            background-color: #ffaa00;
        }
        #final-text {
            font-size: 22px;
            font-weight: bold;
            margin-top: 20px;
            display: none;
            animation: fadeIn 1.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div class="sparkles"></div>
    <div id="gift-box" onclick="showMessage()">🎁</div>
    <div id="message">❤️🎊 كل لحظة في العيد هي هدية من الله، استمتع بها بكل حب وفرح</div>
    <button id="button" onclick="showImage()">🎉 خذ عيديتك</button>
    <img id="image" src="https://i.postimg.cc/vZndJKwq/0b9e1070def2a8871e8d55d35ef8a465.jpg" alt="عيديتك">
    <div id="final-message">الروح لا يليق بها سوى أن تزهر، فحين تتفتح أزهارها، تنثر عبيرها في أرجاء الحياة، وتُلهم القلوب من حولها. في هذا العيد، أتمنى لك أوقاتًا مليئة بالفرح والسعادة، وأن تظل روحك متألقة ومزهرة دائمًا. عيدك سعيد وكل عام وأنت بخير ♡.</div>
    <button id="next-button" onclick="showFinalText()">التالي</button>
    <div id="final-text">وين عيديتي 🙂؟</div>
    <div id="footer">تصميم Jolliet</div>

    <script>
    function showMessage() {
        document.getElementById('gift-box').style.display = 'none';
        document.getElementById('message').style.display = 'block';
        document.getElementById('button').style.display = 'block';
    }
    function showImage() {
        document.getElementById('message').style.display = 'none';
        document.getElementById('button').style.display = 'none';
        document.getElementById('image').style.display = 'block';
        document.getElementById('final-message').style.display = 'block';
        document.getElementById('next-button').style.display = 'block';
    }
    function showFinalText() {
        document.getElementById('next-button').style.display = 'none';
        document.getElementById('final-message').style.display = 'none';
        document.getElementById('image').style.display = 'none';
        document.getElementById('final-text').style.display = 'block';
    }
    
    function createSparkles() {
        const sparkleContainer = document.querySelector('.sparkles');
        for (let i = 0; i < 30; i++) {
            let sparkle = document.createElement('span');
            sparkle.style.left = Math.random() * 100 + 'vw';
            sparkle.style.top = Math.random() * 100 + 'vh';
            sparkle.style.animationDuration = (Math.random() * 2 + 1) + 's';
            sparkleContainer.appendChild(sparkle);
        }
    }
    createSparkles();
    </script>
</body>
</html>
