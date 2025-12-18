<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love</title>
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: #0A1A2F;
        color: #F6F1EA;
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        flex-direction: column;
    }

    /* LOGIN */
    #login-page {
        text-align: center;
    }
    #login-page input {
        padding: 10px;
        margin: 10px 0;
        border: none;
        border-radius: 5px;
        width: 200px;
    }
    #login-page button {
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        background-color: #C48B9F;
        color: #F6F1EA;
        font-weight: bold;
        cursor: pointer;
    }

    /* MAIN PAGE */
    #main-page {
        display: none;
        flex-direction: column;
        align-items: center;
        padding: 20px;
        max-width: 900px;
        width: 90%;
    }

    /* HEADER VIDEO */
    #header {
        width: 100%;
        margin-bottom: 15px;
        border-radius: 15px;
        overflow: hidden;
    }
    #header-video {
        width: 100%;
        max-height: 400px;
        object-fit: cover;
        border-radius: 15px;
    }
    #header p {
        text-align: center;
        margin-top: 10px;
        font-size: 1.1em;
        line-height: 1.4em;
        color: #F6F1EA;
    }

    @media (max-width: 768px) {
        #header-video { max-height: 300px; }
        #header p { font-size: 1em; }
    }

    .emotion-button {
        background-color: #C48B9F;
        color: #F6F1EA;
        border: none;
        padding: 12px 20px;
        margin: 8px;
        border-radius: 8px;
        font-size: 1em;
        cursor: pointer;
        transition: all 0.3s;
    }
    .emotion-button:hover { background-color: #D1A3B3; }

    #message-box {
        margin-top: 20px;
        text-align: center;
        background-color: #0B1F3B;
        padding: 20px;
        border-radius: 10px;
        width: 100%;
    }

    #message-box img, #message-box video, #message-box audio {
        max-width: 100%;
        margin-top: 10px;
        border-radius: 10px;
    }
</style>
</head>
<body>

<!-- LOGIN PAGE -->
<div id="login-page">
    <h1>Welcome My Big Animal 💙</h1>
    <p>Sorry for all the late replies and naps I told you, actually I was just so busy making and working on this for weeks 😂😘.</p>
<p>And I wanted to show this to you now, before Christmas week starts… and before you chug a ton of beers 😜… so you’ll actually be sober enough to read it 💙</p>
    <input type="text" id="username" placeholder="Username"><br>
    <input type="password" id="password" placeholder="Password"><br>
    <button onclick="checkLogin()">Enter</button>
    <p id="login-error" style="color: #FFAAAA;"></p>
</div>

<!-- MAIN PAGE -->
<div id="main-page">
    <!-- HEADER VIDEO -->
    <div id="header">
        <video id="header-video" playsinline>
            <source src="assets/videos/header.mp4" type="video/mp4">
        </video>
        <p>To my biggest Atay, I made this special for you. This space holds my heart, our memories, and everything I feel for you. I couldn’t think of a perfect gift, so I took my time to make this so I could say and show everything, all specially made just for you. Merry Christmas! 🎄💙</p>
    </div>

    <!-- BUTTONS -->
    <div id="buttons">
        <button class="emotion-button" onclick="showMessage('miss')">I just want you</button>
        <button class="emotion-button" onclick="showMessage('love')">Why I love you</button>
        <button class="emotion-button" onclick="showMessage('happy')">Why I’m happy to have you</button>
        <button class="emotion-button" onclick="showMessage('mad')">If you are mad with me</button>
        <button class="emotion-button" onclick="showMessage('doubt')">Our favorite memory of us</button>
        <button class="emotion-button" onclick="showMessage('lucky')">Why I'm lucky to have you</button>
    </div>

    <!-- MESSAGE BOX -->
    <div id="message-box">
        <p>Click a button to see my message 💌</p>
    </div>
</div>

<script>
function checkLogin() {
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    const error = document.getElementById('login-error');
    const video = document.getElementById('header-video');

    if(username === 'hinico' && password === 'iloveyou') {
        document.getElementById('login-page').style.display = 'none';
        document.getElementById('main-page').style.display = 'flex';

        // play header video with sound
        video.muted = false;
        video.play().catch(() => console.log("Autoplay blocked, user interaction required."));
    } else {
        error.textContent = 'Incorrect username or password 💔';
    }
}

function showMessage(type) {
    const box = document.getElementById('message-box');
    box.innerHTML = '';

    switch(type) {
        case 'miss':
            box.innerHTML = `
                <p>I just want you.. my stupid, stubborn animal above😄 anyone and anything else.
I’m completely content with you. You are everything I want and everything I need.
You balance me in ways I never knew I needed, and with you, I feel whole.</p>
<p>Above all else, I just want Nicolas Pleithner.. the one who lives at Dorfplatz 4,
the one with a little more white hair now 😜 but somehow looks even hotter than before.
You. Just you.
I want to be with you everywhere and every time 🥺 in the quiet moments, the noisy ones, the ordinary days, and the unforgettable ones.</p>
<p>I hope this long distance is only shaping us back together so we can spend more time side by side, fall asleep together, and wake up next to each other every morning.
You’re my person, my balance, my comfort, and my choice...  always 💙</p>
                <video controls autoplay playsinline>
                    <source src="assets/videos/memory1.mp4" type="video/mp4">
                </video>
            `;
            break;

        case 'love':
            box.innerHTML = `
                <button class="emotion-button" id="revealLoveBtn">
                    Oh why did you click this? Do you really wanna know why I love you?
                </button>
            `;
            document.getElementById('revealLoveBtn').addEventListener('click', () => {
                box.innerHTML = `
<p>Hi Nico,</p>
<p>I don’t really know where to start, but I know I want to start with you.
There was a time in my life when everything felt uncertain. I didn’t really know what to do or where to go. I kept telling myself, maybe I should be here, maybe I should be there, trying to push myself out of my comfort zone and figure things out. Not everything worked out the way I expected.. but somehow, all of it led me to where I was meant to be.
It led me back to you.</p>

<p>I truly believe now that I was meant to go there, because it brought me to finding you again. And I feel so lucky to have met you in this lifetime, and lucky to have found someone who makes me happy just by being you.
Being with you has let me experience things I’ve never experienced before. A kind of love I didn’t even know was possible. You’ve shown me what it feels like to be loved in a way that’s calm, genuine, and real. You make me want to be a better version of myself… not out of pressure, but because I want to be better for us. I want to take care of you, treat you well, and love you the way you deserve.</p>

<p>You probably don’t realize how much you make me happy. Or how much I want to grow, just so I can love you better every day.
I’m grateful for everything we’ve shared, from the trips we took, how we started as friends, slowly getting to know each other, spending time together, laughing, and eventually becoming inseparable. Even now, when distance separates us, I want you to know that I really, truly love you.</p>

<p>This love wasn’t instant. It’s the kind of love that revealed itself over time.. the kind you confirm through moments, choices, and feelings. And I know now that this is the love I want.
I realized how deeply I loved you in moments I didn’t expect. When you told me I hurt your feelings, and my heart ached knowing I caused you pain. When I dropped you off at the airport it suddenly became real that we wouldn’t see each other for a long time. That ache in my heart told me everything.</p>

<p>I love you for who you are. For stepping out of your comfort zone for me. For making the effort to make me feel loved, secure, and cared for. For meeting me halfway, even though we come from different cultures and different backgrounds.
I appreciate you more than you know for cooking for me, for surprising me, for giving me your time when you didn’t have to. For the long flights, the hotels, the holidays you spent just so we could be together. None of that was small to me.. it meant everything.</p>

<p>From the little surprises to the big ones, from your touch to your kisses and your hugs….you make me feel deeply loved. 
And I love you exactly as you are—even when you’re a little stupid sometimes. It honestly just makes me laugh more, like you more, and love you even more. And this is a love I don’t ever want to lose.</p>

<p>I love you my biggest atay 💙</p>
<img src="assets/images/love.jpg" alt="Much love, Chi 😘">
                `;
            });
            break;

        case 'happy':
            box.innerHTML = `
<p>* You make me laugh even when I’m actively trying not to</p>
<p>* You put up with my moods like a pro (seriously, award-worthy behavior 🏆)</p>
<p>* You make ordinary days feel special without even trying</p>
<p>* I felt so special — and honestly moved — when you cooked me pasta for the first time (and yes, it was VERY yummy 🍝)</p>
<p>* You show up for me by actually visiting me, and that means more than you know</p>
<p>* You treat me to holidays that turn into meaningful, lasting memories with you</p>
<p>* You annoy me in a way I’d miss immediately if it ever stopped</p>
<p>* You make me feel wanted, loved, and chosen</p>
<p>* You give me very good sexy time… rawrrr 😏🔥</p>
<p>* You never forget to text me (which still amazes me hahaha)</p>
<p>* You’ve taught me a lot just by being you — including how to be stupid… just kidding 😜</p>
<p>* You challenge me to be better, and you make me want to be better — for myself and for you</p>
<p>* You feel like home, even when you’re far away</p>
<p>* And honestly… just you (and your cactus 🌵) are more than enough to make me happy</p>
<p>* We can talk our problems and I really appreciate it even if first we will gonna argue but we try to communicate it openly</p>
<p>* You perfectly balance me out, you are calm and I am not 😭😂</p>
<img src="assets/images/happy.jpg" alt="Thanks for just being you, you make me the happiest😘">
            `;
            break;

        case 'mad':
            box.innerHTML = `
                <p>Incase you're mad with me, watch this again...🤣😝 got it?🤗😂</p>
               <video controls playsinline>
            <source src="assets/videos/sorry1.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

       
            `;
            break;

        case 'doubt':
            box.innerHTML = `
                <p>Of all the trips we’ve been on, of all the photos we’ve taken… this is my absolute favorite memory and picture of us.
Just seeing it makes me feel so connected to you, and even months later, I can still feel the butterflies I had that day.
That’s the moment I realized… I really liked you 🤭♥️</p>
                <img src="assets/images/stronger.jpg" alt="Stronger">
            `;
            break;

        case 'lucky':
            box.innerHTML = `
                <p>You know the very first reason why I’m so lucky to have you?</p>
<p>Because you’re insanely handsome.
I honestly can’t stop taking pictures of you… and okay.... this is supposed to be my little secret, but I can’t help staring at you sometimes.
Especially when you’re sleeping.... that’s when I get to admire just how handsome my boyfriend really is. 😍</p>
                <video controls playsinline>
            <source src="assets/videos/lucky.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

        <video controls playsinline>
            <source src="assets/videos/sorry2.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

            `;
            break;

        default:
            box.innerHTML = `<p>Click a button to see my message 💌</p>`;
    }
}
</script>
</body>
</html>
