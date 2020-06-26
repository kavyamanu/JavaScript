# JavaScript
This is part of JavaScript 30 days challenge. 
Below is the code for Day#1 challenge in Javascript 30.

    <!DOCTYPE HTML>
    <html>
    <head>
        <title> Js30_Day#1</title>
        <link rel="icon" href="https://upload.wikimedia.org/wikipedia/commons/thumb/8/88/Number_1_in_green_rounded_square.svg/600px-Number_1_in_green_rounded_square.svg.png">
        <style>
        body
        {
            background-image: url(https://images.unsplash.com/photo-1579532649672-13fac8cde626?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1868&q=80);
        }
        .key
            {
            padding: 1rem .5rem ;
            border: 4px solid rgb(19, 78, 10);
            border-radius: 5px;
            margin: 1rem;
            font-size: 1.5rem;
            color: rgb(17, 99, 30);
            transition: all 0.09s;
            width: 100px;
            text-align: center;
            }
        .keys {
            padding-inline-start: 20rem;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            }
        .playing 
            {
            transform:scale(1.1);
            border-color: rgb(214, 114, 189);
            box-shadow: 0 0 20px rgb(218, 114, 157);
            }
        kbd{
            font-size: 40px;
            display: block;
            }
        span
        {
            color: rgb(85, 11, 48);
            text-shadow:0 0 5px rgb(85, 17, 82);
        }
        .text
        {
            color: rgb(161, 36, 113);
            text-shadow:0 0 5px darkgreen;
            font-size: 3rem;
            padding-inline-end:15rem;
            position: absolute;
            top: 40%;
            left: 85%;
            transform: translate(-50%, -50%);
        }
        </style>
    </head>
    <body>
        <h2 class="text">Day#1</h2>
        <div class="keys">
            <div data-key="65" class="key">
            <kbd>A</kbd>
            <span>clap</span>
            </div> 
            <div data-key="83" class="key"> 
            <kbd>S</kbd>
            <span>drum</span>
            </div>
            <div data-key="68" class="key">
            <kbd>D</kbd>
            <span>boom</span>
            </div>
            <div data-key="70" class="key">
            <kbd>F</kbd>
            <span>kick</span>
            </div>
        </div>
        <audio data-key="65" src="file:///C:/Users/USER/Downloads/applause.mp3"></audio>
        <audio data-key="83" src="file:///C:/Users/USER/Downloads/Bass-Drum-Hit-Level-6c-www.fesliyanstudios.com.mp3"></audio>
        <audio data-key="68" src="file:///C:/Users/USER/Downloads/Explosion+1.mp3"></audio>
        <audio data-key="70" src="file:///C:/Users/USER/Downloads/Crunchy-Punch-B-www.fesliyanstudios.com.mp3"></audio>
        <script>
        
            function addTeenas(e) 
            {
                const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
                const key = document.querySelector(`.key[data-key="${e.keyCode}"]`);
                if(!audio) return;
                audio.currentTime=0;
                audio.play();
                key.classList.add("playing");
            }
            function removerTernas(e)
            {
                if (e.propertyName !== 'transform') return;
                this.classList.remove("playing");
            }
            window.addEventListener('keydown', addTeenas);
            const keys = document.querySelectorAll('.key');
            keys.forEach(key => key.addEventListener('transitionend', removerTernas));
            keys.forEach(key => key.addEventListener('transitionend', removerTernas));
         </script>
    </body>
    </html>
