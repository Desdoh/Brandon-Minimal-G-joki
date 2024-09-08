<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Scrolling Text</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #000;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        .marquee {
            width: 100%;
            white-space: nowrap;
            overflow: hidden;
            box-sizing: border-box;
            color: #fff;
            font-size: 24px;
            font-weight: bold;
        }
        .marquee-content {
            display: inline-block;
            padding-left: 100%; /* Start from right outside the view */
            animation: marquee 10s linear infinite;
        }
        @keyframes marquee {
            0% {
                transform: translateX(100%);
            }
            100% {
                transform: translateX(-100%);
            }
        }
    </style>
</head>
<body>
    <div class="marquee">
        <div class="marquee-content">
            Minimal Engga Joki lah | Katanya pro tp kok Joki | Lawak kali |
        </div>
    </div>
    <script>
        // To ensure the animation runs for at least 3 minutes
        const duration = 180000; // 3 minutes in milliseconds
        const animationDuration = 10000; // Duration of one full scroll (10 seconds)

        document.querySelector('.marquee-content').style.animationDuration = `${animationDuration}ms`;

        setTimeout(() => {
            document.querySelector('.marquee-content').style.animationPlayState = 'paused';
        }, duration);
    </script>
</body>
</html>
