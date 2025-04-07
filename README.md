<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Radhe Radhe💖🙌</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            overflow: hidden;
            background-color: #ffcce6;
        }
        
        .container {
            width: 100vw;
            height: 100vh;
            position: relative;
        }
        
        .slide {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 1s ease-in-out;
            padding: 20px;
        }
        
        .slide.active {
            opacity: 1;
        }
        
        .photo-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-bottom: 30px;
            width: 80%;
            max-width: 800px;
        }
        
        .photo-grid-6 {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-template-rows: repeat(2, 1fr);
            gap: 15px;
            margin-bottom: 30px;
            width: 90%;
            max-width: 900px;
        }
        
        .photo {
            width: 100%;
            height: 180px;
            border-radius: 10px;
            object-fit: cover;
            border: 5px solid white;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
            transition: transform 0.5s ease;
        }
        
        .photo:hover {
            transform: scale(1.1);
            z-index: 10;
        }
        
        .enlarge-animation {
            animation: enlarge 5s infinite alternate;
        }
        
        @keyframes enlarge {
            0% {
                transform: scale(1);
            }
            100% {
                transform: scale(1.15);
            }
        }
        
        .message {
            font-size: 2rem;
            color: #ff3399;
            text-align: center;
            margin: 20px 0;
            animation: fadeIn 2s;
            max-width: 80%;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 100;
        }
        
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff3399;
            transform: rotate(45deg);
            opacity: 0;
        }
        
        .heart:before, .heart:after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff3399;
            border-radius: 50%;
        }
        
        .heart:before {
            top: -10px;
            left: 0;
        }
        
        .heart:after {
            left: -10px;
            top: 0;
        }
        
        .nav-buttons {
            position: absolute;
            bottom: 30px;
            width: 100%;
            display: flex;
            justify-content: center;
            gap: 20px;
            z-index: 100;
        }
        
        button {
            padding: 10px 20px;
            background-color: #ff3399;
            color: white;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        button:hover {
            background-color: #ff66b2;
            transform: scale(1.1);
        }
        
        .slide-1 {
            background: linear-gradient(to right, #ffcce6, #ff99cc);
        }
        
        .slide-2 {
            background: linear-gradient(to right, #e6ccff, #cc99ff);
        }
        
        .slide-3 {
            background: linear-gradient(to right, #ccf2ff, #99e6ff);
        }
        
        .slide-4 {
            background: linear-gradient(to right, #f9f9cc, #fff066);
        }
        
        .fireworks {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            opacity: 0;
        }
        
        .balloon {
            position: absolute;
            width: 40px;
            height: 50px;
            border-radius: 50%;
            opacity: 0;
        }
        
        h1 {
            font-size: 3rem;
            color: #ff3399;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            margin-bottom: 20px;
            animation: bounce 1s infinite alternate;
        }
        
        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-20px); }
        }
        
        .video-container {
            width: 80%;
            max-width: 800px;
            margin: 20px 0;
            border: 10px solid white;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
            overflow: hidden;
            position: relative;
        }
        
        .video-placeholder {
            width: 100%;
            height: 400px;
            background-color: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 1.5rem;
            position: relative;
            overflow: hidden;
        }
        
        .video-overlay {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .video-placeholder:hover .video-overlay {
            opacity: 1;
        }
        
        .play-button {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: rgba(255, 51, 153, 0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .play-button:hover {
            transform: scale(1.1);
            background-color: rgba(255, 51, 153, 1);
        }
        
        .play-icon {
            width: 0;
            height: 0;
            border-top: 20px solid transparent;
            border-bottom: 20px solid transparent;
            border-left: 30px solid white;
            margin-left: 5px;
        }
        
        .heartbeat {
            animation: heartbeat 1.5s infinite;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            14% { transform: scale(1.3); }
            28% { transform: scale(1); }
            42% { transform: scale(1.3); }
            70% { transform: scale(1); }
        }
        
        .special-message-container {
            width: 80%;
            max-width: 800px;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 0 30px rgba(255, 102, 179, 0.5);
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .special-message-container::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, 
                rgba(255,51,153,0) 0%, 
                rgba(255,51,153,0.2) 50%, 
                rgba(255,51,153,0) 100%);
            animation: shine 3s infinite;
            z-index: 1;
        }
        
        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(30deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(30deg); }
        }
        
        .special-message {
            font-size: 1.8rem;
            color: #ff3399;
            line-height: 1.6;
            margin-bottom: 20px;
            position: relative;
            z-index: 2;
        }
        
        .special-signature {
            font-size: 2.2rem;
            font-family: 'Brush Script MT', cursive;
            color: #ff3399;
            margin-top: 20px;
            position: relative;
            z-index: 2;
        }
        
        .progress-bar {
            position: absolute;
            bottom: 15px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 6px;
            background-color: rgba(255, 255, 255, 0.5);
            border-radius: 3px;
            overflow: hidden;
            z-index: 100;
        }
        
        .progress {
            height: 100%;
            width: 0;
            background-color: #ff3399;
            transition: width 0.3s ease;
        }
        
        .slide-indicator {
            display: flex;
            position: absolute;
            bottom: 70px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 100;
        }
        
        .indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.5);
            margin: 0 5px;
            cursor: pointer;
        }
        
        .indicator.active {
            background-color: #ff3399;
            transform: scale(1.2);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="hearts" id="hearts"></div>
        <div class="fireworks" id="fireworks"></div>
        
        <!-- Slide 1: Introduction with 4 photos -->
        <div class="slide slide-1" id="slide1">
            <h1>Happy Birthday Duplicate😍❤️!</h1>
            <div class="photo-grid">
                <img src="withdad.jpg" alt="Poorva 1" class="photo enlarge-animation" style="animation-delay: 0s;">
                <img src="withfamily.jpg" alt="Poorva 2" class="photo enlarge-animation" style="animation-delay: 1s;">
                <img src="childpoorva.jpg" alt="Poorva 3" class="photo enlarge-animation" style="animation-delay: 2s;">
                <img src="withmom.jpg" alt="Poorva 4" class="photo enlarge-animation" style="animation-delay: 3s;">
            </div>
            <div class="message">Happy wala birthday vivekji and meghaji ke ladki ko😍🥳</div>
        </div>
        
        <!-- Slide 2: Six photos in a grid -->
        <div class="slide slide-2" id="slide2">
            <h1>kuch pasandida tasvireeeeee 😁😉</h1>
            <div class="photo-grid-6">
                <img src="lolipop.jpg.JPG" alt="Memory 1" class="photo enlarge-animation" style="animation-delay: 0.5s;">
                <img src="mela.jpg.jpg" alt="Memory 2" class="photo enlarge-animation" style="animation-delay: 1s;">
                <img src="ghibli.jpg" alt="Memory 3" class="photo enlarge-animation" style="animation-delay: 1.5s;">
                <img src="redtop.jpg" alt="Memory 4" class="photo enlarge-animation" style="animation-delay: 2s;">
                <img src="teashirt.jpg" alt="Memory 5" class="photo enlarge-animation" style="animation-delay: 2.5s;">
                <img src="kamartalav.jpg" alt="Memory 6" class="photo enlarge-animation" style="animation-delay: 3s;">
            </div>
            <div class="message">Ab me sabki tarah to nahi hu to socha thoda cse touch me tko surprise karvau😜🤪</div>
        </div>
        
        <!-- Slide 3: Video section -->
        <div class="slide slide-3" id="slide3">
            <h1>Ab tak ka safar😜</h1>
            <div class="video-container">
                <div class="video-placeholder">
                    <img src="COLAGE.jpg" alt="Birthday Video" style="width: 100%; height: 100%; object-fit: cover;">
                    <div class="video-overlay">
                        <div class="play-button">
                            <div class="play-icon"></div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="message">Dekh moti tu haa bol ya na bol lekin tere harr problem me mai aaise hi tera haat pakad k khada rahugaa .............................................. As a jigri jhannat yaar🤝</div>
        </div>
        
        <!-- Slide 4: Special message -->
        <div class="slide slide-4" id="slide4">
            <h1 class="heartbeat">Tere liye bata hua thoda sa pyaar💖</h1>
            <div class="special-message-container">
                <div class="special-message">
                    Happy wala birthday moti dhanyavad tere mata and dad ko jinhone itni pyari bacchi di thi mana ki wahi bacchi badi hokar thodi golu molo mastikhor or markundi cow ho gayi lekin uspe suit bhi krta. Chal chal ave teri baat thodi krra me khud imagine mt kr isme poorva bhakareee. Me to meri jigri jhannat matrin ki baat krra jisko me bahut pyaar se duplicate bolta😍. Ye poorva bhakareee na badi haramkhor he jhagadte rehti mere se baat krna chod deti baat baat pe pata nahi q 🙂 thik he ab thodi akkal aa gayi usko. Lekin kuch bhi bolo meri duplicate badi cute he ek time pe mko wo munna bolti thi pata nahi wo kaha gayi lekin ye bhi manageable he. Chal chal boht hua ab soja badiya chaddar odh kar boht jyada udd mt 
Janamdin din ki khup khup anumodna😅😍❤🫶🏻🥰

                </div>
                <div class="special-signature">
                    With love and best wishes
                </div>
            </div>
        </div>
        
        <div class="nav-buttons">
            <button id="prevBtn">Previous</button>
            <button id="nextBtn">Next</button>
        </div>
        
        <div class="slide-indicator" id="slideIndicator">
            <div class="indicator active" data-slide="0"></div>
            <div class="indicator" data-slide="1"></div>
            <div class="indicator" data-slide="2"></div>
            <div class="indicator" data-slide="3"></div>
        </div>
        
        <div class="progress-bar">
            <div class="progress" id="progress"></div>
        </div>
    </div>
    
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const slides = document.querySelectorAll('.slide');
            const prevBtn = document.getElementById('prevBtn');
            const nextBtn = document.getElementById('nextBtn');
            const indicators = document.querySelectorAll('.indicator');
            const progress = document.getElementById('progress');
            let currentSlide = 0;
            let autoSlideInterval;
            const autoSlideDuration = 7000; // 7 seconds per slide
            
            // Show first slide initially
            slides[currentSlide].classList.add('active');
            
            // Update indicator and progress
            function updateIndicators() {
                // Update dot indicators
                indicators.forEach((indicator, index) => {
                    if (index === currentSlide) {
                        indicator.classList.add('active');
                    } else {
                        indicator.classList.remove('active');
                    }
                });
                
                // Update progress bar
                progress.style.width = `${(currentSlide + 1) / slides.length * 100}%`;
            }
            
            // Function to change slides
            function goToSlide(index) {
                slides[currentSlide].classList.remove('active');
                currentSlide = index;
                slides[currentSlide].classList.add('active');
                updateIndicators();
                
                // Add animations based on the current slide
                createHearts();
                if (currentSlide === slides.length - 1) {
                    createConfetti();
                    createBalloons();
                }
                
                // Reset auto slide timer
                clearInterval(autoSlideInterval);
                startAutoSlide();
            }
            
            // Next button functionality
            nextBtn.addEventListener('click', function() {
                const nextIndex = (currentSlide + 1) % slides.length;
                goToSlide(nextIndex);
            });
            
            // Previous button functionality
            prevBtn.addEventListener('click', function() {
                const prevIndex = (currentSlide - 1 + slides.length) % slides.length;
                goToSlide(prevIndex);
            });
            
            // Indicator dots functionality
            indicators.forEach(indicator => {
                indicator.addEventListener('click', function() {
                    const slideIndex = parseInt(this.getAttribute('data-slide'));
                    goToSlide(slideIndex);
                });
            });
            
            // Auto slide functionality
            function startAutoSlide() {
                autoSlideInterval = setInterval(() => {
                    const nextIndex = (currentSlide + 1) % slides.length;
                    goToSlide(nextIndex);
                }, autoSlideDuration);
                
                // Start progress animation
                progress.style.transition = `width ${autoSlideDuration}ms linear`;
                progress.style.width = '100%';
            }
            
            // Animated hearts
            function createHeart() {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                
                // Random position
                const posX = Math.random() * window.innerWidth;
                const posY = Math.random() * window.innerHeight;
                
                // Random size
                const size = Math.random() * 20 + 10;
                
                heart.style.left = posX + 'px';
                heart.style.top = posY + 'px';
                heart.style.width = size + 'px';
                heart.style.height = size + 'px';
                
                document.getElementById('hearts').appendChild(heart);
                
                // Animate the heart
                setTimeout(() => {
                    heart.style.opacity = '0.8';
                    const animationDuration = Math.random() * 3 + 2;
                    heart.style.animation = `floatUp ${animationDuration}s ease-in forwards`;
                    
                    // Create keyframe animation dynamically
                    const keyframes = `
                        @keyframes floatUp {
                            0% {
                                transform: rotate(45deg) translateY(0) translateX(0);
                                opacity: 0.8;
                            }
                            100% {
                                transform: rotate(45deg) translateY(-${window.innerHeight}px) translateX(${(Math.random() - 0.5) * 200}px);
                                opacity: 0;
                            }
                        }
                    `;
                    
                    const styleSheet = document.createElement('style');
                    styleSheet.type = 'text/css';
                    styleSheet.innerText = keyframes;
                    document.head.appendChild(styleSheet);
                    
                    // Remove the heart after animation
                    setTimeout(() => {
                        heart.remove();
                        styleSheet.remove();
                    }, animationDuration * 1000);
                }, 10);
            }
            
            function createHearts() {
                for (let i = 0; i < 15; i++) {
                    setTimeout(createHeart, i * 100);
                }
            }
            
            // Confetti animation
            function createConfetti() {
                const colors = ['#ff3399', '#66ccff', '#ffcc66', '#99ff99', '#cc99ff'];
                
                for (let i = 0; i < 100; i++) {
                    const confetti = document.createElement('div');
                    confetti.classList.add('confetti');
                    
                    const color = colors[Math.floor(Math.random() * colors.length)];
                    confetti.style.backgroundColor = color;
                    
                    const posX = Math.random() * window.innerWidth;
                    const posY = -20;
                    const size = Math.random() * 8 + 5;
                    
                    confetti.style.left = posX + 'px';
                    confetti.style.top = posY + 'px';
                    confetti.style.width = size + 'px';
                    confetti.style.height = size + 'px';
                    confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '0';
                    
                    document.getElementById('fireworks').appendChild(confetti);
                    
                    // Animate the confetti
                    setTimeout(() => {
                        confetti.style.opacity = '1';
                        const animationDuration = Math.random() * 3 + 2;
                        confetti.style.animation = `fall ${animationDuration}s ease-in forwards`;
                        
                        // Create keyframe animation dynamically
                        const keyframes = `
                            @keyframes fall {
                                0% {
                                    transform: translateY(0) rotate(0deg);
                                    opacity: 1;
                                }
                                100% {
                                    transform: translateY(${window.innerHeight + 100}px) rotate(${Math.random() * 360}deg);
                                    opacity: 0;
                                }
                            }
                        `;
                        
                        const styleSheet = document.createElement('style');
                        styleSheet.type = 'text/css';
                        styleSheet.innerText = keyframes;
                        document.head.appendChild(styleSheet);
                        
                        // Remove the confetti after animation
                        setTimeout(() => {
                            confetti.remove();
                            styleSheet.remove();
                        }, animationDuration * 1000);
                    }, 10);
                }
            }
            
            // Balloon animation for the final slide
            function createBalloons() {
                const colors = ['#ff3399', '#66ccff', '#ffcc66', '#99ff99', '#cc99ff'];
                
                for (let i = 0; i < 20; i++) {
                    const balloon = document.createElement('div');
                    balloon.classList.add('balloon');
                    
                    const color = colors[Math.floor(Math.random() * colors.length)];
                    balloon.style.backgroundColor = color;
                    
                    const posX = Math.random() * window.innerWidth;
                    const posY = window.innerHeight + 50;
                    const size = Math.random() * 30 + 40;
                    
                    balloon.style.left = posX + 'px';
                    balloon.style.top = posY + 'px';
                    balloon.style.width = size + 'px';
                    balloon.style.height = size * 1.2 + 'px';
                    
                    document.getElementById('fireworks').appendChild(balloon);
                    
                    // Add string to balloon
                    const string = document.createElement('div');
                    string.style.position = 'absolute';
                    string.style.width = '2px';
                    string.style.height = '80px';
                    string.style.backgroundColor = '#ffffff';
                    string.style.bottom = '-80px';
                    string.style.left = '50%';
                    string.style.transform = 'translateX(-50%)';
                    balloon.appendChild(string);
                    
                    // Animate the balloon
                    setTimeout(() => {
                        balloon.style.opacity = '0.8';
                        const animationDuration = Math.random() * 10 + 15;
                        balloon.style.animation = `float ${animationDuration}s ease-in forwards`;
                        
                        // Create keyframe animation dynamically
                        const keyframes = `
                            @keyframes float {
                                0% {
                                    transform: translateY(0) rotate(0deg);
                                    opacity: 0.8;
                                }
                                100% {
                                    transform: translateY(-${window.innerHeight + 200}px) translateX(${(Math.random() - 0.5) * 300}px) rotate(${(Math.random() - 0.5) * 40}deg);
                                    opacity: 0;
                                }
                            }
                        `;
                        
                        const styleSheet = document.createElement('style');
                        styleSheet.type = 'text/css';
                        styleSheet.innerText = keyframes;
                        document.head.appendChild(styleSheet);
                        
                        // Remove the balloon after animation
                        setTimeout(() => {
                            balloon.remove();
                            styleSheet.remove();
                        }, animationDuration * 1000);
                    }, Math.random() * 5000); // Staggered starts for balloons
                }
            }
            
            // Set up image animations
            const animatedImages = document.querySelectorAll('.enlarge-animation');
            animatedImages.forEach(img => {
                img.addEventListener('mouseover', function() {
                    this.style.zIndex = '10';
                });
                img.addEventListener('mouseout', function() {
                    this.style.zIndex = '1';
                });
            });
            
            // Add click effect to play button
            const playButton = document.querySelector('.play-button');
            if (playButton) {
                playButton.addEventListener('click', function() {
                    alert('This is where the video would play if it were a real video player!');
                });
            }
            
            // Initial animations and auto slide
            createHearts();
            updateIndicators();
            startAutoSlide();
            
            // Reset progress animation when slide changes
            progress.addEventListener('transitionend', function() {
                progress.style.transition = 'none';
                progress.style.width = '0';
                setTimeout(() => {
                    progress.style.transition = `width ${autoSlideDuration}ms linear`;
                    progress.style.width = '100%';
                }, 50);
            });
        });
    </script>
</body>
</html>
