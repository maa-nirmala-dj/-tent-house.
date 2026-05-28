<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="description" content="Maa Nirmala DJ & Tent House - Elite Digital Portfolio">
    
    <meta name="theme-color" content="#D4AF37">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="MND Tent House">
    <meta name="application-name" content="MNDs Hub">
    
    <!-- PWA Manifest Link -->
    <link rel="manifest" href="manifest.json">
    <link rel="apple-touch-icon" href="https://i.postimg.cc/76mz1v2j/file-0000000090a471fa84cbecd48a774885.png">
    <link rel="icon" type="image/png" href="https://i.postimg.cc/76mz1v2j/file-0000000090a471fa84cbecd48a774885.png">

    <title>Maa Nirmala DJ & Tent House | SECURE HUB</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Outfit:wght@200;400;600&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        :root {
            /* --- ELITE DARK THEME --- */
            --bg-body: #050505;
            --bg-card: rgba(20, 20, 20, 0.9);
            --border-color: rgba(212, 175, 55, 0.3);
            --gold-primary: #D4AF37;
            --gold-shine: #FFD700;
            --text-main: #ffffff;
            --text-sub: #b3b3b3;
            --glass-blur: blur(25px);
            --nav-glass: blur(30px);
        }

        [data-theme="light"] {
            --bg-body: #f2f2f2;
            --bg-card: rgba(255, 255, 255, 0.95);
            --border-color: rgba(180, 140, 40, 0.3);
            --gold-primary: #b08d26;
            --gold-shine: #d4a017;
            --text-main: #111111;
            --text-sub: #555555;
        }

        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-track { background: #000; }
        ::-webkit-scrollbar-thumb { background: var(--gold-primary); border-radius: 10px; }
        
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; outline: none; }
        body { background-color: var(--bg-body); color: var(--text-main); font-family: 'Outfit', sans-serif; overflow-x: hidden; min-height: 100vh; transition: background-color 0.4s ease, color 0.4s ease; }

        /* PWA Install Banner Styles */
        #install-banner {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(20px);
            border-bottom: 2px solid var(--gold-primary);
            padding: 15px 20px;
            z-index: 99999;
            justify-content: space-between;
            align-items: center;
            gap: 15px;
            animation: slideDown 0.4s ease-out;
        }

        #install-banner.show {
            display: flex;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .install-banner-content {
            display: flex;
            align-items: center;
            gap: 12px;
            flex-grow: 1;
        }

        .install-banner-icon {
            width: 40px;
            height: 40px;
            border-radius: 8px;
            background: linear-gradient(135deg, var(--gold-primary), #FFD700);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #000;
            font-size: 18px;
            flex-shrink: 0;
        }

        .install-banner-text h4 {
            margin: 0;
            color: var(--gold-primary);
            font-size: 14px;
            font-weight: bold;
            font-family: 'Cinzel';
        }

        .install-banner-text p {
            margin: 2px 0 0 0;
            color: #aaa;
            font-size: 11px;
        }

        .install-banner-buttons {
            display: flex;
            gap: 8px;
            flex-shrink: 0;
        }

        .install-btn {
            background: var(--gold-primary);
            color: #000;
            border: none;
            padding: 8px 16px;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            font-size: 12px;
            transition: 0.3s;
        }

        .install-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 0 15px var(--gold-primary);
        }

        .install-close {
            background: transparent;
            border: none;
            color: #888;
            font-size: 18px;
            cursor: pointer;
            padding: 5px;
            transition: 0.3s;
        }

        .install-close:hover {
            color: var(--gold-primary);
        }

        /* GATEKEEPER */
        #gatekeeper { position: fixed; inset: 0; z-index: 9999; background: var(--bg-body); display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 20px; text-align: center; }
        .gate-card { width: 100%; max-width: 400px; max-height: 85vh; background: rgba(10, 10, 10, 0.95); border: 1px solid var(--gold-primary); border-radius: 20px; padding: 40px 25px; box-shadow: 0 0 80px rgba(212, 175, 55, 0.15); backdrop-filter: blur(20px); position: relative; overflow-y: auto; overflow-x: hidden; animation: pulseCard 4s infinite alternate; }
        @keyframes pulseCard { from { transform: scale(1); border-color: rgba(212,175,55,0.3); } to { transform: scale(1.005); border-color: rgba(212,175,55,0.6); } }
        .gate-img-frame { width: 110px; height: 110px; margin: 0 auto 20px; border-radius: 50%; padding: 3px; border: 2px solid var(--gold-primary); box-shadow: 0 0 30px rgba(212, 175, 55, 0.3); }
        .gate-img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; }
        .gate-title { font-family: 'Cinzel'; color: var(--gold-primary); font-size: 26px; margin-bottom: 5px; text-shadow: 0 0 15px rgba(212, 175, 55, 0.5); font-weight: 700; }
        .gate-sub { color: #666; font-size: 11px; letter-spacing: 4px; margin-bottom: 30px; font-family: 'Rajdhani'; text-transform: uppercase; }
        .gate-input-group { position: relative; margin-bottom: 15px; text-align: left; }
        .gate-input { width: 100%; padding: 15px 15px 15px 45px; background: rgba(255, 255, 255, 0.05); border: 1px solid #333; color: #fff; font-size: 16px; font-family: 'Rajdhani'; transition: 0.3s; border-radius: 10px; }
        .gate-input:focus { border-color: var(--gold-primary); background: rgba(212, 175, 55, 0.08); box-shadow: 0 0 15px rgba(212,175,55,0.1); }
        .gate-icon { position: absolute; left: 15px; top: 17px; color: #555; transition: 0.3s; }
        .gate-input:focus + .gate-icon { color: var(--gold-primary); }
        .gate-btn { width: 100%; padding: 16px; background: linear-gradient(135deg, var(--gold-primary), #997d2d); color: #000; font-weight: 800; font-size: 16px; border: none; cursor: pointer; border-radius: 10px; transition: 0.3s; }
        .gate-btn:active { transform: scale(0.98); }
        .loading-text { margin-top: 20px; font-size: 12px; color: var(--gold-primary); font-family: 'Rajdhani'; display: none; letter-spacing: 1px; font-weight: bold; }

        /* MAIN UI */
        #main-interface { display: none; opacity: 0; transition: opacity 1.5s ease; padding-bottom: 90px; }
        .bg-fx { position: fixed; inset: 0; z-index: -2; pointer-events: none; overflow: hidden; }
        .orb { position: absolute; border-radius: 50%; filter: blur(120px); opacity: 0.15; animation: float 15s infinite alternate; }
        .orb-1 { width: 350px; height: 350px; background: var(--gold-primary); top: -10%; left: -10%; }
        .orb-2 { width: 300px; height: 300px; background: #00e5ff; bottom: -10%; right: -10%; }
        @keyframes float { 0% { transform: translate(0,0); } 100% { transform: translate(50px, 50px); } }

        /* Navbar & Hamburger */
        .navbar { display: flex; justify-content: space-between; align-items: center; padding: 15px 5%; position: sticky; top: 0; z-index: 1000; background: rgba(5, 5, 5, 0.85); backdrop-filter: var(--nav-glass); border-bottom: 1px solid var(--border-color); }
        .brand { font-family: 'Cinzel'; color: var(--gold-primary); font-weight: 700; font-size: 18px; display: flex; align-items: center; gap: 12px; }
        .controls { display: flex; align-items: center; gap: 15px; }
        .nav-btn { font-size: 20px; cursor: pointer; color: var(--text-main); background: none; border: none; }

        .menu-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.7); z-index: 5999; display: none; opacity: 0; transition: 0.3s; }
        .menu-overlay.active { display: block; opacity: 1; }
        .side-menu { position: fixed; top: 0; left: -280px; width: 260px; height: 100%; background: rgba(10,10,10,0.98); border-right: 1px solid var(--gold-primary); z-index: 6000; transition: left 0.3s ease; }
        .side-menu.open { left: 0; }
        .menu-close { align-self: flex-end; margin: 0 20px 20px 0; font-size: 24px; color: var(--gold-primary); cursor: pointer; }
        .side-link { display: flex; align-items: center; padding: 18px 25px; color: #fff; text-decoration: none; border-bottom: 1px solid #222; font-family: 'Outfit'; font-size: 15px; font-weight: 500; transition: 0.3s; }
        .side-link i { color: var(--gold-primary); margin-right: 15px; font-size: 18px; width: 20px; text-align: center; }
        .side-link:hover { background: rgba(212,175,55,0.1); padding-left: 30px; }
        .menu-logo { text-align: center; padding-bottom: 20px; border-bottom: 1px solid var(--border-color); margin-bottom: 10px; }
        .menu-logo img { width: 80px; height: 80px; border-radius: 50%; border: 2px solid var(--gold-primary); }

        /* Profile Section */
        .container { width: 100%; max-width: 800px; margin: 0 auto; padding: 0 20px; }
        .profile-wrapper { text-align: center; padding: 60px 0 30px; }
        .img-container { width: 160px; height: 160px; margin: 0 auto 20px; position: relative; border-radius: 50%; padding: 5px; background: linear-gradient(135deg, var(--gold-primary), transparent); }
        .profile-pic { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; border: 4px solid var(--bg-body); background: #000; }
        h1 { font-family: 'Rajdhani', sans-serif; font-size: 32px; font-weight: 700; background: linear-gradient(to right, var(--text-main), var(--gold-primary), var(--text-main)); -webkit-background-clip: text; -webkit-text-fill-color: transparent; margin-bottom: 5px; }
        .verified { color: #1DA1F2; font-size: 20px; vertical-align: middle; margin-left: 5px; }
        .bio { color: var(--gold-primary); font-size: 13px; letter-spacing: 2px; font-weight: 600; text-transform: uppercase; }

        /* Welcome & Content */
        .welcome-popup { display: flex; position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background: rgba(0,0,0,0.85); z-index: 999999999; justify-content: center; align-items: center; animation: fadeIn 0.3s ease; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        
        .welcome-box { background: linear-gradient(135deg, #110e08 0%, #050505 100%); border: 2px solid #D4AF37; border-radius: 20px; padding: 30px; text-align: center; width: 92%; max-width: 450px; box-shadow: 0 20px 60px rgba(0,0,0,0.9); position: relative; animation: popIn 0.4s ease; }
        @keyframes popIn { from { opacity: 0; transform: scale(0.9); } to { opacity: 1; transform: scale(1); } }
        
        .close-btn { position: absolute; top: 15px; right: 20px; color: #D4AF37; font-size: 35px; cursor: pointer; transition: 0.3s; }
        .close-btn:hover { color: #fff; }
    </style>
</head>
<body data-theme="dark">

    <!-- PWA Install Banner -->
    <div id="install-banner">
        <div class="install-banner-content">
            <div class="install-banner-icon">
                <i class="fas fa-download"></i>
            </div>
            <div class="install-banner-text">
                <h4>🎉 Install MND App</h4>
                <p>Add to your home screen for quick access</p>
            </div>
        </div>
        <div class="install-banner-buttons">
            <button class="install-btn" onclick="installPWA()">
                <i class="fas fa-plus"></i> Install
            </button>
            <button class="install-close" onclick="dismissInstallBanner()">
                <i class="fas fa-times"></i>
            </button>
        </div>
    </div>

    <!-- GATEKEEPER -->
    <div id="gatekeeper">
        <div class="gate-card">
            <div class="gate-img-frame"><img src="https://i.postimg.cc/76mz1v2j/file-0000000090a471fa84cbecd48a774885.png" class="gate-img" alt="Profile"></div>
            <h2 class="gate-title">MAA NIRMALA DJ</h2>
            <div class="gate-sub">SECURE PORTFOLIO GATEWAY</div>
            <div class="gate-input-group"><input type="text" id="g-name" class="gate-input" placeholder="YOUR FULL NAME"><i class="fas fa-user gate-icon"></i></div>
            <div class="gate-input-group"><input type="tel" id="g-phone" class="gate-input" placeholder="YOUR MOBILE NUMBER"><i class="fas fa-phone gate-icon"></i></div>
            <button class="gate-btn" id="btn-verify" onclick="initiateSecureEntry()"><i class="fas fa-fingerprint"></i> VERIFY & ENTER</button>
            <div class="loading-text" id="g-status"><i class="fas fa-circle-notch fa-spin"></i> OPENING WAIT FEW SEC...</div>
        </div>
    </div>

    <!-- WELCOME POPUP -->
    <div id="royalWelcomePopup" class="welcome-popup" style="display:none;">
        <div class="welcome-box">
            <span class="close-btn" onclick="document.getElementById('royalWelcomePopup').style.display='none'">&times;</span>
            <div style="color:#D4AF37; font-size:16px; line-height:1.6; font-family:'Cinzel', serif; font-weight:bold;">
                ━━━━━━━━━━━━━<br>
                <span style="font-size:26px; color:#fff; text-shadow:0 0 10px #D4AF37; line-height: 1.2;">🎉 WELCOME TO 🎉</span><br>
                <span style="font-size:30px; color:#FFD700; text-shadow:0 0 20px #FFD700; line-height: 1.2;"> MAA NIRMALA DJ </span><br>
                ━━━━━━━━━━━━━━━
            </div>
            <div style="color:#ddd; font-family:'Outfit', sans-serif; font-size:15px; text-align:left; margin-top:25px; line-height:2;">
                <i class="fas fa-volume-up" style="color:#D4AF37; width:20px;"></i> <b>Powerful Sound System</b><br>
                <i class="fas fa-lightbulb" style="color:#D4AF37; width:20px;"></i> <b>Premium Lighting & DJ Effects</b><br>
                <i class="fas fa-music" style="color:#D4AF37; width:20px;"></i> <b>Unforgettable Vibes for Every Event</b><br>
                <i class="fas fa-gift" style="color:#ff3333; width:20px;"></i> <b style="color:#ff3333;">Special Gate Offer Available!</b><br>
                <i class="fas fa-hand-point-right" style="color:#D4AF37; width:20px;"></i> <b>Book Now & Make Your Event Grand</b>
            </div>
            <div style="margin-top: 25px; padding-top: 20px; border-top: 1px dashed rgba(212,175,55,0.4); text-align: center;">
                <p style="color:#D4AF37; font-family:'Cinzel'; font-weight:bold; font-size:18px; margin:0 0 10px 0;">📞 Contact / Booking:</p>
                <a href="tel:+917294969938" style="display:inline-block; background:#25D366; color:#fff; padding:10px 25px; border-radius:30px; text-decoration:none; font-weight:bold; font-family:'Outfit'; margin:0 5px;">📞 Call Now</a>
                <p style="color:#aaa; font-family:'Outfit'; font-size:12px; line-height:1.5; margin:15px 0 0 0;">
                    <i class="fas fa-map-marker-alt" style="color:#ff3333;"></i> <b>Address:</b><br>
                    Tola Beltikri, Kaddhar, Katoria, Banka, Bihar, India (813106)
                </p>
            </div>
        </div>
    </div>

    <script>
        // ========== PWA INSTALLATION SCRIPT ==========
        let deferredPrompt = null;

        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
            showInstallBanner();
        });

        function showInstallBanner() {
            const banner = document.getElementById('install-banner');
            if (banner) {
                banner.classList.add('show');
            }
        }

        function dismissInstallBanner() {
            const banner = document.getElementById('install-banner');
            if (banner) {
                banner.classList.remove('show');
            }
        }

        async function installPWA() {
            if (!deferredPrompt) {
                alert('❌ App installation is not available on this device.\n\n📱 For iOS: Use Share > Add to Home Screen\n🤖 For Android: Look for "Install" in the browser menu');
                return;
            }

            deferredPrompt.prompt();
            const { outcome } = await deferredPrompt.userChoice;

            if (outcome === 'accepted') {
                console.log('✅ PWA installed successfully!');
                dismissInstallBanner();
            }

            deferredPrompt = null;
        }

        window.addEventListener('appinstalled', () => {
            console.log('✅ MND App installed successfully!');
            dismissInstallBanner();
            deferredPrompt = null;
        });

        // Register Service Worker
        if ('serviceWorker' in navigator) {
            navigator.serviceWorker.register('./sw.js')
                .then(registration => {
                    console.log('✅ Service Worker registered');
                })
                .catch(error => {
                    console.log('⚠️ Service Worker registration failed:', error);
                });
        }

        // Show Welcome Popup
        window.addEventListener('DOMContentLoaded', () => {
            document.getElementById('royalWelcomePopup').style.display = 'flex';
        });

        // Gatekeeper Login
        function initiateSecureEntry() {
            const name = document.getElementById('g-name').value.trim();
            const phone = document.getElementById('g-phone').value.trim();
            
            if (!name || !phone) {
                alert('⚠️ Please enter your name and phone number!');
                return;
            }

            const loading = document.getElementById('g-status');
            loading.style.display = 'block';
            
            setTimeout(() => {
                alert('✅ Welcome ' + name + '! Access Granted.');
                document.getElementById('gatekeeper').style.display = 'none';
                loading.style.display = 'none';
            }, 2000);
        }

        console.log('🎯 App Setup Complete');
    </script>

</body>
</html>
