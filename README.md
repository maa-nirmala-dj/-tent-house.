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

    <!-- Your existing content goes here -->
    <div id="gatekeeper">
        <div class="gate-card">
            <!-- Your gatekeeper content -->
        </div>
    </div>

    <script>
        // ========== PWA INSTALLATION SCRIPT ==========
        let deferredPrompt = null;

        // Listen for beforeinstallprompt event
        window.addEventListener('beforeinstallprompt', (e) => {
            // Prevent the mini-infobar from appearing on mobile
            e.preventDefault();
            // Stash the event for later use
            deferredPrompt = e;
            // Show the install banner
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

            // Show the install prompt
            deferredPrompt.prompt();

            // Wait for the user to respond to the prompt
            const { outcome } = await deferredPrompt.userChoice;

            if (outcome === 'accepted') {
                console.log('✅ PWA installed successfully!');
                // Track installation
                if (window.gtag) {
                    gtag('event', 'app_installed');
                }
                dismissInstallBanner();
            } else {
                console.log('❌ User dismissed the install prompt');
            }

            // Clear the deferredPrompt for the next time.
            deferredPrompt = null;
        }

        // Check if app is already installed
        window.addEventListener('appinstalled', () => {
            console.log('✅ MND App installed successfully!');
            dismissInstallBanner();
            deferredPrompt = null;
        });

        // Check if running as PWA
        function isPWA() {
            return window.matchMedia('(display-mode: standalone)').matches ||
                   window.navigator.standalone === true ||
                   document.referrer.includes('android-app://');
        }

        // Register Service Worker
        if ('serviceWorker' in navigator) {
            navigator.serviceWorker.register('./sw.js')
                .then(registration => {
                    console.log('✅ Service Worker registered:', registration);
                })
                .catch(error => {
                    console.log('⚠️ Service Worker registration failed:', error);
                });
        }

        // Optional: Show different UI for iOS vs Android
        function isIOSDevice() {
            return /iPad|iPhone|iPod/.test(navigator.userAgent) && !window.MSStream;
        }

        function isAndroidDevice() {
            return /Android/.test(navigator.userAgent);
        }

        // Auto-hide banner after 30 seconds if not interacted
        setTimeout(() => {
            if (!isPWA() && deferredPrompt === null) {
                // Only auto-hide if no prompt is available
            }
        }, 30000);

        console.log('🎯 PWA Setup Complete');
        console.log('📱 Running as PWA:', isPWA());
        console.log('🍎 iOS Device:', isIOSDevice());
        console.log('🤖 Android Device:', isAndroidDevice());
    </script>

</body>
</html>
