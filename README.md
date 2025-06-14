<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Untuk Nana ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Animated Background */
        .background-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .floating-heart {
            position: absolute;
            color: rgba(255, 255, 255, 0.1);
            font-size: 20px;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        /* Container Styles */
        .container {
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(102, 126, 234, 0.1), transparent);
            animation: shine 3s infinite;
            z-index: 1;
            pointer-events: none;
        }

        @keyframes shine {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Page-specific styles */
        .page {
            display: none;
            animation: fadeIn 0.5s ease-in;
        }

        .page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Login Page Styles */
        .login-header {
            margin-bottom: 30px;
        }

        .login-header h1 {
            color: #4a5568;
            font-size: 2.5em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .login-header p {
            color: #718096;
            font-size: 1.1em;
        }

        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #4a5568;
            font-weight: 600;
        }

        .form-group input {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-size: 16px;
            transition: all 0.3s ease;
            background: white;
            position: relative;
            z-index: 10;
        }

        .form-group input:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
            background: white;
        }

        .login-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
        }

        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(102, 126, 234, 0.3);
        }

        .error-message {
            color: #e53e3e;
            margin-top: 15px;
            padding: 10px;
            background: rgba(229, 62, 62, 0.1);
            border-radius: 8px;
            display: none;
        }

        /* Apology Page Styles */
        .apology-header {
            margin-bottom: 30px;
        }

        .apology-header h1 {
            color: #4a5568;
            font-size: 2.8em;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .apology-message {
            color: #4a5568;
            font-size: 1.2em;
            line-height: 1.8;
            margin-bottom: 30px;
            text-align: left;
        }

        .apology-message p {
            margin-bottom: 20px;
        }

        /* Surprise Page Styles */
        .surprise-header h1 {
            color: #4a5568;
            font-size: 2.5em;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .surprise-content {
            color: #4a5568;
            font-size: 1.1em;
            line-height: 1.8;
            text-align: left;
        }

        .surprise-content p {
            margin-bottom: 15px;
        }

        .poem {
            background: linear-gradient(45deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            font-style: italic;
            border-left: 4px solid #667eea;
        }

        /* Photo Gallery Styles */
        .photo-gallery {
            margin: 30px 0;
        }

        .photo-gallery h3 {
            color: #4a5568;
            font-size: 1.5em;
            margin-bottom: 20px;
            text-align: center;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .photo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }

        .photo-frame {
            position: relative;
            background: white;
            border: 3px solid #667eea;
            border-radius: 15px;
            height: 200px;
            overflow: hidden;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.2);
        }

        .photo-frame:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
            border-color: #764ba2;
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .photo-frame:hover img {
            transform: scale(1.05);
        }

        .photo-label {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(102, 126, 234, 0.9), transparent);
            color: white;
            padding: 15px 10px 10px;
            font-size: 0.9em;
            font-weight: 600;
            text-align: center;
        }

        .photo-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(45deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            color: #667eea;
            font-size: 0.9em;
            text-align: center;
        }

        .photo-placeholder .upload-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
            display: block;
        }

        /* Navigation Buttons */
        .nav-buttons {
            margin-top: 30px;
            display: flex;
            gap: 15px;
            justify-content: center;
        }

        .nav-btn {
            padding: 12px 24px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 25px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .nav-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 16px rgba(102, 126, 234, 0.3);
        }

        .nav-btn.secondary {
            background: linear-gradient(45deg, #a0aec0, #718096);
        }

        .nav-btn.secondary:hover {
            box-shadow: 0 8px 16px rgba(160, 174, 192, 0.3);
        }

        /* Cute Animations */
        .cute-emoji {
            font-size: 2em;
            display: inline-block;
            animation: bounce 2s infinite;
            margin: 0 10px;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        .floating-emoji {
            position: absolute;
            font-size: 1.5em;
            animation: floatEmoji 4s ease-in-out infinite;
            pointer-events: none;
            z-index: 5;
        }

        @keyframes floatEmoji {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.7; }
            50% { transform: translateY(-15px) rotate(10deg); opacity: 1; }
        }

        .emoji-1 { top: 20px; right: 20px; animation-delay: 0s; }
        .emoji-2 { bottom: 20px; left: 20px; animation-delay: 1s; }
        .emoji-3 { top: 60%; right: 10px; animation-delay: 2s; }
        .emoji-4 { bottom: 60%; left: 10px; animation-delay: 3s; }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            .card {
                padding: 30px 25px;
            }
            
            .login-header h1,
            .apology-header h1,
            .surprise-header h1 {
                font-size: 2em;
            }
            
            .nav-buttons {
                flex-direction: column;
            }
            
            .nav-btn {
                width: 100%;
            }
            
            .photo-grid {
                grid-template-columns: 1fr;
                gap: 15px;
            }
            
            .photo-frame {
                height: 180px;
            }
        }

        /* Loading animation */
        .loading {
            display: none;
            text-align: center;
            color: #667eea;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #667eea;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            animation: spin 1s linear infinite;
            margin: 0 auto 10px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Background Animation -->
    <div class="background-animation" id="bgAnimation"></div>

    <div class="container">
        <!-- Login Page -->
        <div class="page active" id="loginPage">
            <div class="card">
                <div class="floating-emoji emoji-1">🐻</div>
                <div class="floating-emoji emoji-2">🐰</div>
                <div class="floating-emoji emoji-3">💙</div>
                <div class="floating-emoji emoji-4">✨</div>
                
                <div class="login-header">
                    <h1>Halo BANANA <span class="cute-emoji">💕</span></h1>
                    <p>INI DARI JAKYY, SEMOGA TIDAK ALAY HAHAHAHA</p>
                </div>
                
                <form id="loginForm" style="position: relative; z-index: 20;">
                    <div class="form-group">
                        <label for="username">Username:</label>
                        <input type="text" id="username" name="username" required autocomplete="off">
                    </div>
                    
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input type="password" id="password" name="password" required autocomplete="off">
                    </div>
                    
                    <button type="submit" class="login-btn">
                        <span class="btn-text">Masuk</span>
                        <div class="loading">
                            <div class="spinner"></div>
                            <span>Memverifikasi...</span>
                        </div>
                    </button>
                </form>
                
                <div class="error-message" id="errorMessage">
                    ELU SIAPE? INI KHUSUS NANA
                </div>
            </div>
        </div>

        <!-- Apology Page -->
        <div class="page" id="apologyPage">
            <div class="card">
                <div class="floating-emoji emoji-1">🐻</div>
                <div class="floating-emoji emoji-2">🐰</div>
                <div class="floating-emoji emoji-3">💙</div>
                <div class="floating-emoji emoji-4">✨</div>
                
                <div class="apology-header">
                    <h1>maaf ya kalo menurutmu alay maklum masih belajar gais<span class="cute-emoji">💖</span></h1>
                </div>
                
                <div class="apology-message">
                    <p>AAAYYYY, aku tau aku udaaa membuuat kesalahan yang bikin kamu kecewa . Aku nyeseelllll bangett karena udaa ngelakuin itu ke kamuuu :).</p>
                    
                    <p>SUMPAAHH AKU MASII KEPIKIRAN TAUUUU gabisaa tidurr nihh sampee. butuuhh maap yang benar benar maap hehehehehehehehehehehehehehehe.</p>
                    
                    <p>aku mau minta maaf sedalam dalamnya kaya kamu. maa juga Aku pernah janji ga bentak kamu lagi tapi aku ingkar janji.</p>
                    
                    <p>Maaf yaa nana kitaa saling memaafkan yaa? OKEEYYY???? <span class="cute-emoji">💕</span></p>
                </div>
                
                <div class="nav-buttons">
                    <button class="nav-btn" onclick="showPage('surprisePage')">
                        LANJUT GAK!!?? AKU MEMAKSA <span class="cute-emoji">🎁</span>
                    </button>
                </div>
            </div>
        </div>

        <!-- Surprise Page -->
        <div class="page" id="surprisePage">
            <div class="card">
                <div class="floating-emoji emoji-1">🐻</div>
                <div class="floating-emoji emoji-2">🐰</div>
                <div class="floating-emoji emoji-3">💙</div>
                <div class="floating-emoji emoji-4">✨</div>
                
                <div class="surprise-header">
                    <h1>KHUSUS KMU BANGET INI MAH <span class="cute-emoji">🌟</span></h1>
                </div>
                
                <div class="surprise-content">
                    <p>sedikit keindahan dari seorang banana.</p>
                    
                    <!-- Photo Gallery Section -->
                    <div class="photo-gallery">
                        <h3>deyymm broohhh <span class="cute-emoji">📸</span></h3>
                        <div class="photo-grid">
                            <!-- FOTO 1: Ganti URL di src="" dengan link foto Anda -->
                            <div class="photo-frame">
                                <img src="WhatsApp Image 2025-06-15 at 04.17.00_1d900266.jpg" 
                                     alt="cantik bener kak"
                                     onerror="this.parentElement.innerHTML='<div class=&quot;photo-placeholder&quot;><span class=&quot;upload-icon&quot;>📷</span><div>Foto Pertama Kita</div><small>Ganti URL di kode</small></div>'">
                                <div class="photo-label">cantik bener kak</div>
                            </div>
                            
                            <!-- FOTO 2: Ganti URL di src="" dengan link foto Anda -->
                            <div class="photo-frame">
                                <img src="WhatsApp Image 2025-06-15 at 04.30.27_26f39216.jpg" 
                                     alt="Momen Bahagia"
                                     onerror="this.parentElement.innerHTML='<div class=&quot;photo-placeholder&quot;><span class=&quot;upload-icon&quot;>💕</span><div>Momen Bahagia</div><small>Ganti URL di kode</small></div>'">
                                <div class="photo-label">serem kalo cemberut makannya aku takut hahahahahahahaaha</div>
                            </div>
                            
                            <!-- FOTO 3: Ganti URL di src="" dengan link foto Anda -->
                            <div class="photo-frame">
                                <img src="WhatsApp Image 2025-06-15 at 04.26.38_888f1967.jpg" 
                                     alt="Masa Depan Kita"
                                     onerror="this.parentElement.innerHTML='<div class=&quot;photo-placeholder&quot;><span class=&quot;upload-icon&quot;>🌟</span><div>Masa Depan Kita</div><small>Ganti URL di kode</small></div>'">
                                <div class="photo-label">ini sih bukan manusia lagi kecantikannya</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="poem">
                        <p><strong>pantun nih pantun</strong></p>
                        <p>"ikan hiu makan tomat, i love you nana laknat"</p>
                    </div>
                    
                    <p>ehhh maafin aku pliissss maaf yaa? maafin yaa? kalo ga di maafin aku ga tidur lagi.</p>
                    <p> oiya ini 100 astaghfirullahnya disini aja ya </p>
                    <p>Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah  
Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah Astaghfirullah </p>
<p>hehehe udaahh lunass lohh yaahhh</p>
                    
                    <p>otheey segitu duluu yaaa nanaa cukup sekian terima gaji...ppapaaaiii <span class="cute-emoji">💖</span></p>
                </div>
                
                <div class="nav-buttons">
                    <button class="nav-btn secondary" onclick="showPage('apologyPage')">
                        <span class="cute-emoji">← </span> Kembali
                    </button>
                    <button class="nav-btn" onclick="showPage('loginPage')">
                        <span class="cute-emoji">🏠</span> Beranda
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Create floating background hearts
        function createFloatingHearts() {
            const bgAnimation = document.getElementById('bgAnimation');
            const hearts = ['💙', '💜', '💫', '✨', '🌟'];
            
            for (let i = 0; i < 15; i++) {
                const heart = document.createElement('div');
                heart.className = 'floating-heart';
                heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                heart.style.left = Math.random() * 100 + '%';
                heart.style.top = Math.random() * 100 + '%';
                heart.style.animationDelay = Math.random() * 6 + 's';
                heart.style.animationDuration = (4 + Math.random() * 4) + 's';
                bgAnimation.appendChild(heart);
            }
        }

        // Show specific page
        function showPage(pageId) {
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => page.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
        }

        // Login validation
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const errorMessage = document.getElementById('errorMessage');
            const button = document.querySelector('.login-btn');
            const btnText = button.querySelector('.btn-text');
            const loading = button.querySelector('.loading');
            
            // Show loading
            btnText.style.display = 'none';
            loading.style.display = 'block';
            button.disabled = true;
            
            setTimeout(() => {
                if (username.toLowerCase() === 'banati eka rizqiah' && password === '11.04.06') {
                    // Successful login
                    showPage('apologyPage');
                    // Reset form
                    document.getElementById('loginForm').reset();
                } else {
                    // Failed login
                    errorMessage.style.display = 'block';
                    // Shake animation for error
                    errorMessage.style.animation = 'none';
                    setTimeout(() => {
                        errorMessage.style.animation = 'shake 0.5s ease-in-out';
                    }, 10);
                }
                
                // Hide loading
                btnText.style.display = 'inline';
                loading.style.display = 'none';
                button.disabled = false;
            }, 1500);
        });

        // Add shake animation for errors
        const style = document.createElement('style');
        style.textContent = `
            @keyframes shake {
                0%, 100% { transform: translateX(0); }
                25% { transform: translateX(-5px); }
                75% { transform: translateX(5px); }
            }
        `;
        document.head.appendChild(style);

        // Initialize
        createFloatingHearts();

        // Add some interactive effects
        document.addEventListener('mousemove', function(e) {
            const emojis = document.querySelectorAll('.floating-emoji');
            emojis.forEach((emoji, index) => {
                const rect = emoji.getBoundingClientRect();
                const centerX = rect.left + rect.width / 2;
                const centerY = rect.top + rect.height / 2;
                const deltaX = e.clientX - centerX;
                const deltaY = e.clientY - centerY;
                const distance = Math.sqrt(deltaX * deltaX + deltaY * deltaY);
                
                if (distance < 100) {
                    const angle = Math.atan2(deltaY, deltaX);
                    const force = (100 - distance) / 100;
                    const moveX = -Math.cos(angle) * force * 10;
                    const moveY = -Math.sin(angle) * force * 10;
                    
                    emoji.style.transform = `translate(${moveX}px, ${moveY}px) rotate(${force * 15}deg)`;
                } else {
                    emoji.style.transform = '';
                }
            });
        });

        // Hide error message when user starts typing
        document.getElementById('username').addEventListener('input', function() {
            document.getElementById('errorMessage').style.display = 'none';
        });

        document.getElementById('password').addEventListener('input', function() {
            document.getElementById('errorMessage').style.display = 'none';
        });

        // Add entrance animation for pages
        function showPage(pageId) {
            const pages = document.querySelectorAll('.page');
            const targetPage = document.getElementById(pageId);
            
            pages.forEach(page => {
                if (page.classList.contains('active')) {
                    page.style.animation = 'fadeOut 0.3s ease-out';
                    setTimeout(() => {
                        page.classList.remove('active');
                        page.style.animation = '';
                    }, 300);
                }
            });
            
            setTimeout(() => {
                targetPage.classList.add('active');
                targetPage.style.animation = 'fadeIn 0.5s ease-in';
            }, 300);
        }

        // Add fadeOut animation
        const fadeOutStyle = document.createElement('style');
        fadeOutStyle.textContent = `
            @keyframes fadeOut {
                from { opacity: 1; transform: translateY(0); }
                to { opacity: 0; transform: translateY(-20px); }
            }
        `;
        document.head.appendChild(fadeOutStyle);
    </script>
</body>
</html>
