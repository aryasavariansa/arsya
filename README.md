<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arya Savariansah - Portfolio Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #ffd700;
            --primary-dark: #ffcc00;
            --primary-light: #fff8e1;
            --secondary: #00ffff;
            --danger: #ff4757;
            --success: #2ed573;
            --dark: #121212;
            --dark-light: #1e1e1e;
            --dark-lighter: #2a2a2a;
            --light: #ffffff;
            --gray: #8a8a8a;
            --sidebar-width: 280px;
            --border-radius: 16px;
            --box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --gradient-gold: linear-gradient(135deg, #ffd700 0%, #ffed4e 100%);
            --gradient-cyan: linear-gradient(135deg, #00ffff 0%, #00bcd4 100%);
            --gradient-dark: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            --gradient-success: linear-gradient(135deg, #2ed573 0%, #7bed9f 100%);
            --gradient-purple: linear-gradient(135deg, #a855f7 0%, #c084fc 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        body {
            display: flex;
            min-height: 100vh;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: var(--light);
            overflow: hidden;
        }

        /* ===== SIDEBAR TETAP TANPA SCROLL ===== */
        .sidebar {
            width: var(--sidebar-width);
            background: linear-gradient(180deg, #0f0f0f 0%, #1a1a1a 100%);
            color: var(--light);
            height: 100vh;
            position: fixed;
            left: 0;
            top: 0;
            display: flex;
            flex-direction: column;
            box-shadow: 5px 0 30px rgba(0, 0, 0, 0.5);
            z-index: 100;
            overflow-y: hidden;
            transition: var(--transition);
            border-right: 1px solid rgba(255, 215, 0, 0.1);
        }

        .sidebar-header {
            padding: 40px 30px 30px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            flex-shrink: 0;
            position: relative;
        }

        .profile-section {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 30px;
            position: relative;
        }

        .profile-img-container {
            position: relative;
            cursor: pointer;
            transition: var(--transition);
        }

        .profile-img-container:hover {
            transform: scale(1.05);
        }

        .profile-img {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: var(--gradient-gold);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 28px;
            color: #000;
            box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);
            border: 3px solid rgba(255, 215, 0, 0.5);
            overflow: hidden;
            object-fit: cover;
            background-color: #000;
        }

        .profile-img-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--gradient-gold);
        }

        .profile-img-upload {
            position: absolute;
            bottom: -5px;
            right: -5px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            display: none;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 0.8rem;
            box-shadow: 0 4px 10px rgba(255, 215, 0, 0.3);
            transition: var(--transition);
            z-index: 10;
        }

        .profile-img-container:hover .profile-img-upload {
            display: flex;
        }

        .admin-mode .profile-img-upload {
            display: flex;
        }

        .profile-img-upload:hover {
            transform: scale(1.2);
            box-shadow: 0 6px 15px rgba(255, 215, 0, 0.4);
        }

        .profile-info h2 {
            font-size: 1.4rem;
            margin-bottom: 8px;
            font-weight: 700;
            color: var(--light);
        }

        .profile-info p {
            font-size: 0.9rem;
            color: var(--primary);
            font-weight: 500;
        }

        /* Menu Navigasi Sidebar */
        .nav-menu {
            list-style: none;
            padding: 30px 0;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .nav-menu li {
            margin-bottom: 5px;
            position: relative;
        }

        .nav-menu a {
            display: flex;
            align-items: center;
            color: #aaa;
            text-decoration: none;
            padding: 16px 30px;
            transition: var(--transition);
            font-size: 1rem;
            font-weight: 500;
        }

        .nav-menu a:hover {
            color: var(--light);
            transform: translateX(5px);
        }

        .nav-menu a.active {
            color: var(--primary);
            background: linear-gradient(90deg, rgba(255, 215, 0, 0.1), transparent);
        }

        .nav-menu a i {
            width: 24px;
            margin-right: 15px;
            font-size: 1.2rem;
        }

        /* Admin Panel di Sidebar */
        .admin-section {
            padding: 25px 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            flex-shrink: 0;
        }

        .admin-toggle {
            background: linear-gradient(135deg, #1e1e1e 0%, #2a2a2a 100%);
            color: var(--primary);
            border: 1px solid rgba(255, 215, 0, 0.3);
            width: 100%;
            padding: 14px;
            border-radius: 12px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            font-weight: 600;
            transition: var(--transition);
            font-size: 0.95rem;
        }

        .admin-toggle:hover {
            transform: translateY(-3px);
            border-color: var(--primary);
        }

        .admin-panel {
            background: linear-gradient(135deg, #1a1a1a 0%, #252525 100%);
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 25px;
            margin-top: 20px;
            display: none;
            border: 1px solid rgba(255, 215, 0, 0.1);
            animation: slideDown 0.3s ease;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .admin-panel.active {
            display: block;
        }

        .admin-input {
            width: 100%;
            padding: 12px 16px;
            margin-bottom: 15px;
            background: #0f0f0f;
            border: 2px solid rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            font-size: 0.95rem;
            transition: var(--transition);
            color: var(--light);
        }

        .admin-input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(255, 215, 0, 0.1);
        }

        .admin-btn {
            width: 100%;
            padding: 14px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 700;
            transition: var(--transition);
            margin-bottom: 10px;
            font-size: 0.95rem;
        }

        .admin-btn:hover {
            transform: translateY(-2px);
        }

        .sidebar-footer {
            padding: 25px 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: var(--gray);
            font-size: 0.85rem;
            text-align: center;
            flex-shrink: 0;
        }

        /* ===== KONTEN UTAMA DENGAN SCROLL DI POJOK KANAN ===== */
        .main-content {
            flex: 1;
            margin-left: var(--sidebar-width);
            min-height: 100vh;
            padding: 0;
            overflow-y: auto;
            background: linear-gradient(135deg, rgba(10, 10, 10, 0.95) 0%, rgba(26, 26, 26, 0.98) 100%);
            height: 100vh;
            width: calc(100% - var(--sidebar-width));
            position: fixed;
            right: 0;
            top: 0;
            scrollbar-width: thin;
            scrollbar-color: var(--primary) rgba(255, 255, 255, 0.1);
        }

        /* Custom Scrollbar seperti Google/Apps Modern */
        .main-content::-webkit-scrollbar {
            width: 12px;
        }

        .main-content::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }

        .main-content::-webkit-scrollbar-thumb {
            background: var(--gradient-gold);
            border-radius: 10px;
            border: 3px solid transparent;
            background-clip: content-box;
        }

        .main-content::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(135deg, #ffcc00 0%, #ffed4e 100%);
            background-clip: content-box;
        }

        /* Header Konten */
        .content-header {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.9) 0%, rgba(26, 26, 26, 0.95) 100%);
            padding: 30px 50px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 99;
            backdrop-filter: blur(10px);
            box-shadow: 0 5px 30px rgba(0, 0, 0, 0.5);
            width: 100%;
        }

        .page-title h2 {
            font-size: 2.2rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            font-weight: 800;
        }

        .page-title p {
            color: var(--gray);
            font-size: 1.1rem;
            max-width: 600px;
        }

        .edit-status {
            color: var(--primary);
            font-size: 0.9rem;
            padding: 10px 20px;
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.1) 0%, rgba(255, 215, 0, 0.05) 100%);
            border-radius: 50px;
            display: none;
            border: 1px solid rgba(255, 215, 0, 0.2);
            font-weight: 600;
        }

        /* ===== TOMBOL TAMBAH WORK DI POJOK KANAN ATAS ===== */
        .floating-add-btn {
            position: fixed;
            top: 100px;
            right: 40px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50px;
            padding: 15px 25px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
            z-index: 999;
            display: none;
            align-items: center;
            gap: 10px;
            font-size: 0.95rem;
        }

        .floating-add-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.4);
        }

        .floating-add-btn i {
            font-size: 1.1rem;
        }

        /* Tampilkan tombol saat admin mode */
        .admin-mode .floating-add-btn {
            display: flex;
        }

        /* ===== EFEK RAIN ELEGAN UNTUK ABOUT PAGE ===== */
        .rain-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            display: none;
            overflow: hidden;
        }

        .rain-drop {
            position: absolute;
            width: 1px;
            height: 80px;
            background: linear-gradient(to bottom, 
                transparent 0%, 
                rgba(0, 255, 255, 0.8) 30%,
                rgba(0, 255, 255, 0.6) 70%,
                transparent 100%);
            animation: rain-fall 2s linear infinite;
            filter: blur(0.5px);
            opacity: 0;
        }

        .rain-drop::before {
            content: '';
            position: absolute;
            top: 0;
            left: -1px;
            width: 3px;
            height: 6px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            filter: blur(1px);
        }

        .rain-drop::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: -1px;
            width: 2px;
            height: 4px;
            background: rgba(0, 255, 255, 0.9);
            border-radius: 50%;
            filter: blur(0.5px);
        }

        @keyframes rain-fall {
            0% {
                transform: translateY(-100px) translateX(-10px);
                opacity: 0;
            }
            10% {
                opacity: 0.8;
            }
            50% {
                opacity: 0.9;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(100vh) translateX(10px);
                opacity: 0;
            }
        }

        /* Efek ripple yang lebih halus */
        .rain-ripple {
            position: absolute;
            width: 8px;
            height: 8px;
            border: 1px solid rgba(0, 255, 255, 0.4);
            border-radius: 50%;
            animation: ripple-elegant 1.5s ease-out;
            opacity: 0;
            box-shadow: 
                0 0 10px rgba(0, 255, 255, 0.3),
                inset 0 0 5px rgba(255, 255, 255, 0.2);
        }

        @keyframes ripple-elegant {
            0% {
                transform: scale(0);
                opacity: 0.6;
                border-width: 1px;
            }
            50% {
                opacity: 0.3;
            }
            100% {
                transform: scale(8);
                opacity: 0;
                border-width: 0.5px;
            }
        }

        /* Efek cahaya dari tetesan hujan */
        .rain-light {
            position: absolute;
            width: 20px;
            height: 20px;
            background: radial-gradient(circle, 
                rgba(0, 255, 255, 0.3) 0%, 
                rgba(0, 255, 255, 0.1) 40%,
                transparent 70%);
            border-radius: 50%;
            filter: blur(5px);
            animation: light-fade 0.5s ease-out;
        }

        @keyframes light-fade {
            0% {
                opacity: 0;
                transform: scale(0);
            }
            30% {
                opacity: 0.6;
                transform: scale(1);
            }
            100% {
                opacity: 0;
                transform: scale(1.5);
            }
        }

        /* ===== EFEK STARFALL ELEGAN UNTUK CHAT ROOM ===== */
        .starfall-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            display: none;
            overflow: hidden;
            background: radial-gradient(ellipse at center, 
                transparent 0%,
                rgba(10, 10, 10, 0.1) 40%,
                rgba(10, 10, 10, 0.3) 100%);
        }

        .star {
            position: absolute;
            border-radius: 50%;
            animation: star-fall-elegant 4s linear infinite;
            opacity: 0;
        }

        .star::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100%;
            height: 100%;
            background: inherit;
            filter: blur(3px);
            opacity: 0.7;
        }

        .star::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 200%;
            height: 200%;
            background: inherit;
            filter: blur(10px);
            opacity: 0.3;
        }

        @keyframes star-fall-elegant {
            0% {
                transform: translateY(-100px) rotate(0deg) scale(0);
                opacity: 0;
            }
            10% {
                opacity: 0.9;
                transform: translateY(0) rotate(0deg) scale(1);
            }
            30% {
                opacity: 1;
            }
            70% {
                opacity: 0.8;
            }
            90% {
                opacity: 0.5;
            }
            100% {
                transform: translateY(100vh) rotate(180deg) scale(0.5);
                opacity: 0;
            }
        }

        /* Efek jejak bintang */
        .star-trail {
            position: absolute;
            width: 100px;
            height: 100px;
            background: linear-gradient(90deg, 
                transparent 0%, 
                rgba(255, 215, 0, 0.1) 30%,
                rgba(255, 215, 0, 0.05) 70%,
                transparent 100%);
            transform-origin: left center;
            animation: trail-fade 1s ease-out;
            opacity: 0;
            filter: blur(2px);
        }

        @keyframes trail-fade {
            0% {
                opacity: 0;
                transform: scaleX(0) rotate(var(--trail-angle));
            }
            30% {
                opacity: 0.6;
            }
            100% {
                opacity: 0;
                transform: scaleX(1) rotate(var(--trail-angle));
            }
        }

        /* Efek burst yang lebih halus */
        .star-burst {
            position: absolute;
            border-radius: 50%;
            animation: burst-elegant 1.2s ease-out forwards;
            opacity: 0;
            box-shadow: 
                0 0 20px currentColor,
                0 0 40px currentColor,
                0 0 60px currentColor;
        }

        @keyframes burst-elegant {
            0% {
                transform: scale(0);
                opacity: 0.9;
                filter: blur(0);
            }
            50% {
                opacity: 1;
                filter: blur(1px);
            }
            100% {
                transform: scale(5);
                opacity: 0;
                filter: blur(3px);
            }
        }

        /* Efek partikel kecil setelah burst */
        .star-particle {
            position: absolute;
            width: 3px;
            height: 3px;
            border-radius: 50%;
            animation: particle-scatter 1s ease-out forwards;
            opacity: 0;
        }

        @keyframes particle-scatter {
            0% {
                transform: translate(0, 0) scale(1);
                opacity: 0.8;
            }
            100% {
                transform: 
                    translate(
                        calc(var(--particle-x) * 50px),
                        calc(var(--particle-y) * 50px)
                    ) scale(0);
                opacity: 0;
            }
        }

        /* ===== BACKGROUND OVERLAY ELEGAN ===== */
        .effect-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            opacity: 0;
            transition: opacity 1s ease;
        }

        .effect-overlay.active {
            opacity: 1;
        }

        /* Background khusus untuk rain effect */
        .rain-overlay {
            background: 
                radial-gradient(circle at 20% 30%, rgba(0, 50, 100, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(0, 100, 150, 0.05) 0%, transparent 50%),
                linear-gradient(135deg, 
                    rgba(10, 20, 40, 0.3) 0%,
                    rgba(15, 30, 60, 0.1) 50%,
                    rgba(20, 40, 80, 0.2) 100%);
        }

        /* Background khusus untuk starfall effect */
        .starfall-overlay {
            background: 
                radial-gradient(circle at 30% 20%, rgba(255, 215, 0, 0.05) 0%, transparent 40%),
                radial-gradient(circle at 70% 80%, rgba(255, 100, 0, 0.03) 0%, transparent 40%),
                linear-gradient(135deg, 
                    rgba(40, 20, 0, 0.2) 0%,
                    rgba(60, 30, 0, 0.1) 50%,
                    rgba(80, 40, 0, 0.15) 100%);
        }

        /* ===== ANIMASI HALUS UNTUK ELEMEN HOVER ===== */
        #aboutPage.rain-active .experience-item:hover {
            transform: translateX(10px) scale(1.02);
            box-shadow: 
                0 20px 50px rgba(0, 255, 255, 0.2),
                0 0 30px rgba(0, 255, 255, 0.1),
                inset 0 0 20px rgba(0, 255, 255, 0.05);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        #aboutPage.rain-active .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: 
                0 15px 30px rgba(0, 255, 255, 0.15),
                0 0 20px rgba(0, 255, 255, 0.1);
            background: linear-gradient(135deg, 
                rgba(0, 255, 255, 0.2) 0%, 
                rgba(0, 200, 255, 0.15) 100%);
        }

        #chatroomPage.starfall-active .message:hover {
            transform: translateX(5px) scale(1.03);
            box-shadow: 
                0 20px 50px rgba(255, 215, 0, 0.25),
                0 0 30px rgba(255, 215, 0, 0.15),
                inset 0 0 20px rgba(255, 255, 255, 0.1);
        }

        #chatroomPage.starfall-active .chatroom-header {
            background: linear-gradient(135deg, 
                rgba(255, 215, 0, 0.8) 0%,
                rgba(255, 200, 0, 0.6) 50%,
                rgba(255, 185, 0, 0.4) 100%);
            animation: golden-shimmer 3s infinite alternate;
            position: relative;
            overflow: hidden;
        }

        #chatroomPage.starfall-active .chatroom-header::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg,
                transparent,
                rgba(255, 255, 255, 0.3),
                transparent);
            animation: header-shine 3s infinite;
        }

        @keyframes header-shine {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        @keyframes golden-shimmer {
            0%, 100% {
                background-position: 0% 50%;
                box-shadow: 
                    0 10px 40px rgba(255, 215, 0, 0.3),
                    inset 0 1px 0 rgba(255, 255, 255, 0.2);
            }
            50% {
                background-position: 100% 50%;
                box-shadow: 
                    0 15px 50px rgba(255, 215, 0, 0.4),
                    inset 0 1px 0 rgba(255, 255, 255, 0.3);
            }
        }

        #chatroomPage.starfall-active .message.user {
            background: linear-gradient(135deg, 
                rgba(255, 215, 0, 0.85) 0%,
                rgba(255, 200, 0, 0.7) 100%);
            animation: golden-pulse 3s infinite;
            position: relative;
            overflow: hidden;
        }

        #chatroomPage.starfall-active .message.user::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg,
                transparent,
                rgba(255, 255, 255, 0.2),
                transparent);
            animation: message-shine 4s infinite;
        }

        @keyframes message-shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        @keyframes golden-pulse {
            0%, 100% {
                box-shadow: 
                    0 10px 40px rgba(255, 215, 0, 0.25),
                    0 0 20px rgba(255, 215, 0, 0.15);
            }
            50% {
                box-shadow: 
                    0 15px 50px rgba(255, 215, 0, 0.35),
                    0 0 30px rgba(255, 215, 0, 0.25);
            }
        }

        /* ===== TOMBOL TOGGLE EFEK ===== */
        .effect-toggle {
            position: fixed;
            bottom: 100px;
            right: 40px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50px;
            padding: 12px 25px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            box-shadow: 0 8px 25px rgba(255, 215, 0, 0.3);
            z-index: 100;
            display: none;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
            z-index: 999;
        }

        .effect-toggle:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 35px rgba(255, 215, 0, 0.4);
        }

        .effect-toggle i {
            font-size: 1.1rem;
        }

        /* Responsif untuk tombol efek */
        @media (max-width: 768px) {
            .effect-toggle {
                bottom: 80px;
                right: 20px;
                padding: 10px 20px;
                font-size: 0.8rem;
            }
        }

        /* Update posisi tombol floating-add-btn dan effect-toggle */
        .floating-add-btn {
            position: fixed;
            top: 100px;
            right: 40px;
        }

        .effect-toggle {
            position: fixed;
            bottom: 100px;
            right: 40px;
        }

        /* Atur posisi untuk mobile */
        @media (max-width: 768px) {
            .floating-add-btn {
                top: auto;
                bottom: 30px;
                right: 20px;
            }
            
            .effect-toggle {
                bottom: 80px;
                right: 20px;
            }
        }

        /* Jika kedua tombol tampil bersamaan (admin mode + efek aktif) */
        .admin-mode .floating-add-btn.active + .effect-toggle {
            bottom: 180px;
        }

        @media (max-width: 768px) {
            .admin-mode .floating-add-btn.active + .effect-toggle {
                bottom: 130px;
            }
        }

        /* Responsif untuk tombol floating */
        @media (max-width: 768px) {
            .floating-add-btn {
                top: auto;
                bottom: 30px;
                right: 20px;
                padding: 12px 20px;
                font-size: 0.85rem;
            }
        }

        /* Body Konten dengan Scroll */
        .content-body {
            padding: 50px;
            min-height: calc(100vh - 140px);
            width: 100%;
        }

        /* Page Container */
        .page {
            display: none;
            animation: fadeInUp 0.6s ease;
            padding-bottom: 100px;
            width: 100%;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .page.active {
            display: block;
        }

        /* ===== HOME PAGE - UPDATED & MORE AESTHETIC ===== */
        .home-hero {
            position: relative;
            padding: 40px 20px;
            background: linear-gradient(135deg, 
                rgba(10, 10, 10, 0.95) 0%, 
                rgba(26, 26, 26, 0.9) 50%,
                rgba(40, 40, 40, 0.8) 100%);
            border-radius: var(--border-radius);
            margin-bottom: 60px;
            overflow: hidden;
            height: 70vh; /* Gunakan viewport height */
            min-height: 500px;
            display: flex;
            align-items: center; /* Pusatkan vertikal */
            justify-content: center; /* Pusatkan horizontal */
            border: 1px solid rgba(255, 215, 0, 0.15);
            box-shadow: 
                0 20px 60px rgba(0, 0, 0, 0.5),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
        }

        .home-hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: var(--gradient-gold);
            z-index: 1;
        }

        .home-hero::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 120%;
            height: 120%;
            background: radial-gradient(
                circle at center,
                rgba(255, 215, 0, 0.05) 0%,
                rgba(255, 215, 0, 0.02) 30%,
                transparent 70%
            );
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            max-width: 900px;
            width: 100%;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center; /* Pusatkan semua item */
            justify-content: center; /* Pusatkan secara vertikal */
        }

        .hero-badge {
            display: inline-block;
            background: var(--gradient-gold);
            color: #000;
            padding: 12px 24px;
            border-radius: 50px;
            font-weight: 700;
            margin-bottom: 25px;
            font-size: 1.1rem;
            box-shadow: 
                0 10px 25px rgba(255, 215, 0, 0.3),
                0 5px 15px rgba(0, 0, 0, 0.2);
            animation: float 6s ease-in-out infinite;
            border: 2px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .hero-badge::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                90deg,
                transparent,
                rgba(255, 255, 255, 0.2),
                transparent
            );
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { left: -100%; }
            100% { left: 100%; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .hero-title {
            font-size: 3.8rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            font-weight: 800;
            line-height: 1.1;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            position: relative;
            display: inline-block;
            text-align: center;
            width: 100%;
        }

        .hero-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 3px;
            background: var(--gradient-gold);
            border-radius: 3px;
        }

        .hero-subtitle {
            font-size: 1.6rem;
            color: var(--secondary);
            margin-bottom: 25px;
            font-weight: 600;
            animation: fadeInUp 0.8s ease 0.3s both;
            text-align: center;
        }

        .hero-description {
            font-size: 1.2rem;
            color: #ddd;
            max-width: 800px;
            margin: 0 auto 30px;
            line-height: 1.8;
            animation: fadeInUp 0.8s ease 0.5s both;
            text-align: center;
        }

        .hero-actions {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            animation: fadeInUp 0.8s ease 0.7s both;
        }

        /* Stats Grid Updated */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 35px;
            margin: 60px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, 
                rgba(30, 30, 30, 0.9) 0%, 
                rgba(26, 26, 26, 0.8) 100%);
            padding: 45px 35px;
            border-radius: var(--border-radius);
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 
                0 20px 40px rgba(0, 0, 0, 0.4),
                inset 0 1px 0 rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .stat-card:hover {
            transform: translateY(-15px) scale(1.03);
            border-color: rgba(255, 215, 0, 0.3);
            box-shadow: 
                0 30px 60px rgba(0, 0, 0, 0.6),
                0 0 30px rgba(255, 215, 0, 0.1);
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-gold);
        }

        .stat-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                135deg,
                transparent,
                rgba(255, 215, 0, 0.03),
                transparent
            );
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .stat-card:hover::after {
            opacity: 1;
        }

        .stat-number {
            font-size: 3.5rem;
            font-weight: 900;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            line-height: 1;
            position: relative;
            display: inline-block;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .stat-number::after {
            content: '+';
            position: absolute;
            top: -10px;
            right: -20px;
            font-size: 2rem;
            color: var(--secondary);
            opacity: 0.7;
        }

        .stat-label {
            color: #ddd;
            font-size: 1.1rem;
            font-weight: 500;
            max-width: 200px;
            margin: 0 auto;
            line-height: 1.5;
            padding: 0 10px;
        }

        /* Quick Links Section */
        .quick-links {
            margin-top: 80px;
            padding-top: 60px;
            border-top: 1px solid rgba(255, 215, 0, 0.1);
        }

        .quick-links h3 {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 40px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 700;
        }

        .links-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .link-card {
            background: linear-gradient(135deg, 
                rgba(30, 30, 30, 0.8) 0%, 
                rgba(26, 26, 26, 0.6) 100%);
            padding: 30px;
            border-radius: var(--border-radius);
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .link-card:hover {
            transform: translateY(-8px);
            border-color: rgba(255, 215, 0, 0.3);
            box-shadow: 
                0 20px 50px rgba(0, 0, 0, 0.4),
                0 0 20px rgba(255, 215, 0, 0.1);
        }

        .link-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: var(--gradient-gold);
        }

        .link-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .link-card h4 {
            color: var(--primary);
            font-size: 1.3rem;
            margin-bottom: 15px;
            font-weight: 700;
        }

        .link-card p {
            color: var(--gray);
            font-size: 0.95rem;
            line-height: 1.5;
        }

        /* Floating particles efek */
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: var(--gradient-gold);
            border-radius: 50%;
            opacity: 0.1;
            animation: floatParticle 15s infinite linear;
        }

        @keyframes floatParticle {
            0%, 100% {
                transform: translate(0, 0);
            }
            25% {
                transform: translate(50px, 50px);
            }
            50% {
                transform: translate(0, 100px);
            }
            75% {
                transform: translate(-50px, 50px);
            }
        }

        /* ===== WORK PAGE - DUPLIKAT DARI ACHIEVEMENTS ===== */
        .work-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 35px;
            margin-top: 30px;
            margin-bottom: 50px;
            width: 100%;
        }

        .work-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 35px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .work-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .work-image-container {
            width: 100%;
            height: 250px;
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 25px;
            background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px dashed rgba(255, 215, 0, 0.2);
            cursor: pointer;
            position: relative;
            transition: var(--transition);
        }

        .admin-mode .work-image-container {
            cursor: pointer;
        }

        .work-image-container:hover {
            border-color: rgba(255, 215, 0, 0.3);
            background: linear-gradient(135deg, #1e1e1e 0%, #2e2e2e 100%);
        }

        .work-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block !important;
            transition: transform 0.3s ease;
        }

        .work-image-container:hover .work-image {
            transform: scale(1.05);
        }

        .work-image-placeholder {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
            font-size: 4rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .work-image-placeholder i {
            display: block;
        }

        .work-upload-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: none;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 1.2rem;
            font-weight: 600;
            text-align: center;
            padding: 20px;
            border-radius: 12px;
        }

        .admin-mode .work-image-container:hover .work-upload-overlay {
            display: flex;
        }

        .work-card h3 {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--primary);
            font-weight: 700;
        }

        .work-card .date {
            color: var(--secondary);
            font-weight: 600;
            margin-bottom: 20px;
            font-size: 1rem;
        }

        .work-card p {
            color: var(--gray);
            line-height: 1.7;
        }

        /* Category Badge untuk Work */
        .category-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--gradient-gold);
            color: #000;
            padding: 8px 20px;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 700;
            z-index: 2;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
        }

        /* ===== DASHBOARD PAGE - UPDATED ===== */
        .dashboard-periods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }

        .period-section {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.9) 0%, rgba(26, 26, 26, 0.7) 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .period-section::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 8px;
            height: 100%;
            background: var(--gradient-gold);
        }

        .period-header {
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid rgba(255, 215, 0, 0.1);
        }

        .period-title {
            font-size: 1.8rem;
            color: var(--primary);
            margin-bottom: 10px;
            font-weight: 700;
        }

        .period-date {
            color: var(--secondary);
            font-size: 1.1rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .period-date i {
            font-size: 1rem;
        }

        .period-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 25px;
        }

        .period-stat {
            text-align: center;
            padding: 25px;
            background: linear-gradient(135deg, rgba(40, 40, 40, 0.8) 0%, rgba(30, 30, 30, 0.6) 100%);
            border-radius: 12px;
            transition: var(--transition);
            border: 1px solid rgba(255, 215, 0, 0.05);
        }

        .period-stat:hover {
            transform: translateY(-5px);
            border-color: rgba(255, 215, 0, 0.2);
        }

        .period-stat-value {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 10px;
            line-height: 1;
        }

        .period-stat-value.staff {
            background: var(--gradient-success);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .period-stat-value.drafter {
            background: var(--gradient-purple);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .period-stat-label {
            color: var(--gray);
            font-size: 0.95rem;
            font-weight: 500;
        }

        /* ===== ABOUT PAGE ===== */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            margin-bottom: 50px;
            min-height: 500px;
            width: 100%;
        }

        .about-text p {
            font-size: 1.15rem;
            margin-bottom: 25px;
            color: var(--gray);
            line-height: 1.8;
        }

        /* Skills */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 40px;
            width: 100%;
        }

        .skill-category {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 35px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .skill-category h3 {
            font-size: 1.4rem;
            margin-bottom: 25px;
            color: var(--primary);
            padding-bottom: 15px;
            border-bottom: 2px solid rgba(255, 215, 0, 0.1);
            font-weight: 700;
        }

        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .skill-item {
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.1) 0%, rgba(255, 215, 0, 0.05) 100%);
            padding: 12px 22px;
            border-radius: 50px;
            font-size: 0.95rem;
            color: var(--primary);
            border: 1px solid rgba(255, 215, 0, 0.2);
            transition: var(--transition);
            font-weight: 500;
        }

        /* Experience */
        .experience-timeline {
            margin-top: 40px;
            width: 100%;
        }

        .experience-item {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 35px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            margin-bottom: 25px;
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .experience-item:hover {
            transform: translateX(10px);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .experience-item::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 5px;
            height: 100%;
            background: var(--gradient-gold);
        }

        .experience-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .experience-title {
            font-size: 1.3rem;
            color: var(--primary);
            font-weight: 700;
        }

        .experience-date {
            color: var(--secondary);
            font-weight: 600;
            font-size: 1rem;
            padding: 8px 16px;
            background: linear-gradient(135deg, rgba(0, 255, 255, 0.1) 0%, rgba(0, 255, 255, 0.05) 100%);
            border-radius: 50px;
            border: 1px solid rgba(0, 255, 255, 0.2);
        }

        .experience-content ul {
            padding-left: 25px;
            color: var(--gray);
        }

        .experience-content li {
            margin-bottom: 12px;
            line-height: 1.6;
        }

        /* ===== ACHIEVEMENTS PAGE ===== */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 35px;
            margin-top: 30px;
            margin-bottom: 50px;
            width: 100%;
        }

        .achievement-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 35px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .achievement-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .achievement-image-container {
            width: 100%;
            height: 250px;
            border-radius: 12px;
            overflow: hidden;
            margin-bottom: 25px;
            background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px dashed rgba(255, 215, 0, 0.2);
            cursor: pointer;
            position: relative;
            transition: var(--transition);
        }

        .admin-mode .achievement-image-container {
            cursor: pointer;
        }

        .achievement-image-container:hover {
            border-color: rgba(255, 215, 0, 0.3);
            background: linear-gradient(135deg, #1e1e1e 0%, #2e2e2e 100%);
        }

        .achievement-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block !important;
            transition: transform 0.3s ease;
        }

        .achievement-image-container:hover .achievement-image {
            transform: scale(1.05);
        }

        .achievement-image-placeholder {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
            font-size: 4rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .achievement-image-placeholder i {
            display: block;
        }

        .achievement-upload-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            display: none;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-size: 1.2rem;
            font-weight: 600;
            text-align: center;
            padding: 20px;
            border-radius: 12px;
        }

        .admin-mode .achievement-image-container:hover .achievement-upload-overlay {
            display: flex;
        }

        .achievement-card h3 {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--primary);
            font-weight: 700;
        }

        .achievement-card .date {
            color: var(--secondary);
            font-weight: 600;
            margin-bottom: 20px;
            font-size: 1rem;
        }

        .achievement-card p {
            color: var(--gray);
            line-height: 1.7;
        }

        /* ===== PROJECTS PAGE ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(550px, 1fr));
            gap: 35px;
            margin-top: 30px;
            margin-bottom: 50px;
            width: 100%;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 8px;
            height: 100%;
            background: var(--gradient-gold);
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .project-card h3 {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            font-weight: 700;
        }

        .project-card h3 i {
            margin-right: 15px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-size: 1.8rem;
        }

        .project-card p {
            color: var(--gray);
            line-height: 1.7;
            margin-bottom: 30px;
            font-size: 1.1rem;
        }

        /* Project Stats */
        .project-stats {
            display: flex;
            justify-content: space-between;
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            padding: 25px;
            border-radius: 12px;
            margin-top: 25px;
            border: 1px solid rgba(255, 215, 0, 0.2);
        }

        .stat {
            text-align: center;
            flex: 1;
            padding: 0 15px;
            position: relative;
        }

        .stat:not(:last-child)::after {
            content: '';
            position: absolute;
            right: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 1px;
            height: 60%;
            background: linear-gradient(to bottom, transparent, rgba(255, 215, 0, 0.2), transparent);
        }

        .stat-value {
            display: block;
            font-size: 2.2rem;
            font-weight: 800;
            margin-bottom: 8px;
            line-height: 1;
        }

        .stat-value.improvement {
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-value.reduction {
            background: linear-gradient(135deg, #ff4757 0%, #ff6b81 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--gray);
            font-weight: 500;
        }

        /* ===== CHATROOM PAGE ===== */
        .chatroom-container {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            overflow: hidden;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
            width: 100%;
            margin: 0 auto;
            height: 70vh;
            display: flex;
            flex-direction: column;
        }

        .chatroom-header {
            background: var(--gradient-gold);
            color: #000;
            padding: 35px;
            text-align: center;
        }

        .chatroom-header h3 {
            font-size: 1.8rem;
            margin-bottom: 10px;
            font-weight: 800;
        }

        .chatroom-messages {
            padding: 35px;
            flex-grow: 1;
            overflow-y: auto;
            background: rgba(20, 20, 20, 0.8);
        }

        .message {
            margin-bottom: 25px;
            padding: 20px;
            background: linear-gradient(135deg, rgba(40, 40, 40, 0.8) 0%, rgba(30, 30, 30, 0.6) 100%);
            border-radius: 20px;
            max-width: 70%;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            transition: var(--transition);
            border: 1px solid rgba(255, 215, 0, 0.1);
        }

        .message:hover {
            transform: translateX(5px);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .message.user {
            margin-left: auto;
            background: var(--gradient-gold);
            color: #000;
        }

        .message-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 12px;
            font-size: 0.9rem;
            opacity: 0.8;
        }

        .message-content {
            font-size: 1.05rem;
            line-height: 1.5;
        }

        .chatroom-input {
            padding: 25px;
            background: rgba(30, 30, 30, 0.8);
            display: flex;
            gap: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
        }

        .chatroom-input input {
            flex: 1;
            padding: 16px 25px;
            background: #0f0f0f;
            border: 2px solid rgba(255, 215, 0, 0.2);
            border-radius: 50px;
            font-size: 1rem;
            transition: var(--transition);
            color: var(--light);
        }

        .chatroom-input input:focus {
            outline: none;
            border-color: var(--primary);
            background: #0a0a0a;
            box-shadow: 0 0 0 3px rgba(255, 215, 0, 0.1);
        }

        .chatroom-input button {
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50px;
            padding: 16px 35px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1rem;
        }

        .chatroom-input button:hover {
            transform: translateY(-3px);
        }

        /* ===== CONTACT PAGE ===== */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            min-height: 500px;
            width: 100%;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
        }

        .contact-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 30px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            text-align: center;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .contact-card:hover {
            transform: translateY(-8px);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .contact-card h3 {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: var(--primary);
            font-weight: 700;
        }

        .contact-card p {
            color: var(--gray);
            font-size: 0.95rem;
            line-height: 1.5;
        }

        .contact-form {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
        }

        .contact-form h3 {
            margin-bottom: 35px;
            color: var(--primary);
            font-size: 1.8rem;
            font-weight: 700;
        }

        .form-group {
            margin-bottom: 25px;
        }

        .form-group label {
            display: block;
            margin-bottom: 12px;
            font-weight: 600;
            color: var(--light);
            font-size: 1rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 16px 20px;
            background: #0f0f0f;
            border: 2px solid rgba(255, 215, 0, 0.2);
            border-radius: 12px;
            font-size: 1rem;
            transition: var(--transition);
            color: var(--light);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            background: #0a0a0a;
            box-shadow: 0 0 0 3px rgba(255, 215, 0, 0.1);
        }

        .submit-btn {
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50px;
            padding: 18px 35px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            width: 100%;
            font-size: 1.1rem;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
        }

        /* ===== EDIT MODE STYLES ===== */
        .admin-mode .editable {
            position: relative;
            border: 2px dashed rgba(255, 215, 0, 0.3);
            padding: 15px;
            margin: 8px 0;
            border-radius: 10px;
            transition: var(--transition);
            background: rgba(255, 215, 0, 0.03);
        }

        .admin-mode .editable:hover {
            background: rgba(255, 215, 0, 0.08);
            border-color: var(--primary);
        }

        .edit-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 8px;
            padding: 8px 15px;
            font-size: 0.85rem;
            cursor: pointer;
            display: none;
            z-index: 5;
            transition: var(--transition);
            font-weight: 700;
        }

        .edit-btn:hover {
            transform: translateY(-2px);
        }

        .admin-mode .edit-btn {
            display: block;
        }

        /* Tombol Delete */
        .delete-btn {
            position: absolute;
            bottom: 10px;
            left: 10px;
            background: linear-gradient(135deg, #ff4757 0%, #ff6b81 100%);
            color: #fff;
            border: none;
            border-radius: 8px;
            padding: 8px 15px;
            font-size: 0.85rem;
            cursor: pointer;
            display: none;
            z-index: 5;
            transition: var(--transition);
            font-weight: 700;
        }

        .delete-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 71, 87, 0.4);
        }

        .admin-mode .delete-btn {
            display: block;
        }

        /* Susunan tombol edit dan delete */
        .editable {
            position: relative;
            padding-bottom: 50px;
        }

        .edit-btn {
            position: absolute;
            bottom: 10px;
            right: 10px;
        }

        .delete-btn {
            position: absolute;
            bottom: 10px;
            left: 10px;
        }

        .add-btn {
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 12px;
            padding: 15px 25px;
            margin: 25px 0;
            cursor: pointer;
            display: none;
            font-weight: 700;
            transition: var(--transition);
            font-size: 1rem;
        }

        .add-btn:hover {
            transform: translateY(-3px);
        }

        .admin-mode .add-btn {
            display: inline-block;
        }

        /* Upload Card untuk Work */
        .upload-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            border: 2px dashed rgba(255, 215, 0, 0.3);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            min-height: 400px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        .upload-card:hover {
            transform: translateY(-5px);
            border-color: rgba(255, 215, 0, 0.5);
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.9) 0%, rgba(26, 26, 26, 0.7) 100%);
        }

        .upload-icon {
            font-size: 4rem;
            margin-bottom: 20px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .upload-text {
            color: var(--primary);
            font-size: 1.5rem;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .upload-subtext {
            color: var(--gray);
            font-size: 1rem;
            max-width: 300px;
        }

        /* ===== MODAL UPLOAD BARU ===== */
        .upload-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(10px);
            z-index: 2001;
            display: none;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
            padding: 20px;
        }

        .upload-modal.active {
            display: flex;
        }

        .upload-modal-content {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.98) 0%, rgba(26, 26, 26, 0.95) 100%);
            border-radius: var(--border-radius);
            padding: 50px;
            width: 90%;
            max-width: 600px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 
                0 40px 100px rgba(255, 215, 0, 0.2),
                inset 0 1px 0 rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 215, 0, 0.3);
            position: relative;
        }

        .upload-modal-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .upload-modal-title {
            font-size: 2rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            font-weight: 800;
        }

        .upload-modal-subtitle {
            color: var(--gray);
            font-size: 1.1rem;
        }

        .upload-form {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .form-row {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
        }

        @media (max-width: 768px) {
            .form-row {
                grid-template-columns: 1fr;
            }
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 12px;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .form-group label i {
            font-size: 0.9rem;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            background: rgba(15, 15, 15, 0.8);
            border: 2px solid rgba(255, 215, 0, 0.2);
            border-radius: 12px;
            padding: 16px 20px;
            color: var(--light);
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(255, 215, 0, 0.1);
            background: rgba(10, 10, 10, 0.9);
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
            font-family: inherit;
        }

        /* Upload Image Area */
        .upload-image-area {
            grid-column: span 2;
            border: 3px dashed rgba(255, 215, 0, 0.3);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
            background: rgba(15, 15, 15, 0.5);
            position: relative;
            overflow: hidden;
            min-height: 250px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        @media (max-width: 768px) {
            .upload-image-area {
                grid-column: span 1;
            }
        }

        .upload-image-area:hover {
            border-color: rgba(255, 215, 0, 0.5);
            background: rgba(15, 15, 15, 0.7);
        }

        .upload-image-area.drag-over {
            border-color: var(--primary);
            background: rgba(255, 215, 0, 0.1);
        }

        .upload-image-icon {
            font-size: 3.5rem;
            margin-bottom: 20px;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .upload-image-text {
            color: var(--primary);
            font-size: 1.3rem;
            margin-bottom: 10px;
            font-weight: 700;
        }

        .upload-image-subtext {
            color: var(--gray);
            font-size: 0.95rem;
            margin-bottom: 20px;
        }

        .upload-image-preview {
            width: 100%;
            max-height: 300px;
            border-radius: 15px;
            overflow: hidden;
            margin-top: 20px;
            display: none;
            border: 2px solid rgba(255, 215, 0, 0.2);
        }

        .upload-image-preview img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .upload-browse-btn {
            background: rgba(255, 215, 0, 0.1);
            color: var(--primary);
            border: 2px solid rgba(255, 215, 0, 0.3);
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .upload-browse-btn:hover {
            background: rgba(255, 215, 0, 0.2);
            transform: translateY(-2px);
        }

        /* Progress Bar untuk Upload */
        .upload-progress-container {
            width: 100%;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            height: 8px;
            margin: 20px 0;
            overflow: hidden;
            display: none;
        }

        .upload-progress-bar {
            height: 100%;
            background: var(--gradient-gold);
            border-radius: 10px;
            width: 0%;
            transition: width 0.3s ease;
        }

        .upload-percentage {
            color: var(--primary);
            font-weight: 700;
            text-align: center;
            font-size: 1.1rem;
            display: none;
            margin-bottom: 10px;
        }

        /* Image Actions */
        .image-actions {
            display: flex;
            gap: 10px;
            margin-top: 15px;
            justify-content: center;
        }

        .image-action-btn {
            background: rgba(30, 30, 30, 0.8);
            color: var(--primary);
            border: 1px solid rgba(255, 215, 0, 0.3);
            padding: 8px 20px;
            border-radius: 8px;
            cursor: pointer;
            transition: var(--transition);
            font-size: 0.9rem;
            font-weight: 600;
        }

        .image-action-btn:hover {
            background: rgba(255, 215, 0, 0.1);
            transform: translateY(-2px);
        }

        /* Modal Buttons */
        .upload-modal-buttons {
            display: flex;
            gap: 20px;
            margin-top: 40px;
        }

        @media (max-width: 768px) {
            .upload-modal-buttons {
                flex-direction: column;
            }
        }

        .upload-modal-btn {
            flex: 1;
            padding: 18px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            font-size: 1rem;
            border: none;
            text-align: center;
        }

        .upload-modal-btn.primary {
            background: var(--gradient-gold);
            color: #000;
        }

        .upload-modal-btn.primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 215, 0, 0.3);
        }

        .upload-modal-btn.secondary {
            background: linear-gradient(135deg, #2a2a2a 0%, #3a3a3a 100%);
            color: var(--light);
            border: 2px solid rgba(255, 215, 0, 0.2);
        }

        .upload-modal-btn.secondary:hover {
            transform: translateY(-3px);
            border-color: var(--primary);
        }

        /* Close button */
        .upload-modal-close {
            position: absolute;
            top: 25px;
            right: 25px;
            background: rgba(255, 215, 0, 0.1);
            color: var(--primary);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            font-size: 1.2rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            z-index: 10;
        }

        .upload-modal-close:hover {
            background: rgba(255, 215, 0, 0.2);
            transform: rotate(90deg);
        }

        /* ===== MODAL UPLOAD FOTO ===== */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(5px);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.95) 0%, rgba(26, 26, 26, 0.98) 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            width: 90%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 30px 80px rgba(255, 215, 0, 0.2);
            border: 1px solid rgba(255, 215, 0, 0.3);
        }

        .modal-title {
            margin-bottom: 25px;
            color: var(--primary);
            text-align: center;
            font-size: 1.5rem;
            font-weight: 700;
        }

        .image-preview {
            width: 100%;
            max-height: 320px;
            border-radius: 12px;
            overflow: hidden;
            margin: 20px 0;
            display: none;
            border: 2px dashed rgba(255, 215, 0, 0.3);
            position: relative;
        }

        .image-preview img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        .modal-buttons {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }

        .modal-btn {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            font-weight: 700;
            transition: var(--transition);
            font-size: 1rem;
        }

        .modal-btn.primary {
            background: var(--gradient-gold);
            color: #000;
        }

        .modal-btn.primary:hover {
            transform: translateY(-3px);
        }

        .modal-btn.secondary {
            background: linear-gradient(135deg, #2a2a2a 0%, #3a3a3a 100%);
            color: var(--light);
            border: 1px solid rgba(255, 215, 0, 0.2);
        }

        .modal-btn.secondary:hover {
            transform: translateY(-3px);
        }

        /* Modal Zoom untuk Gambar */
        .zoom-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            backdrop-filter: blur(10px);
            animation: fadeIn 0.3s ease;
        }

        .zoom-modal.active {
            display: flex;
        }

        .zoom-content {
            position: relative;
            max-width: 90%;
            max-height: 90%;
            animation: zoomIn 0.4s ease;
        }

        @keyframes zoomIn {
            from {
                opacity: 0;
                transform: scale(0.7);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .zoomed-image {
            max-width: 100%;
            max-height: 85vh;
            border-radius: 10px;
            box-shadow: 0 20px 60px rgba(255, 215, 0, 0.2);
            border: 2px solid var(--primary);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .zoomed-image.loaded {
            opacity: 1;
        }

        .close-zoom {
            position: absolute;
            top: -50px;
            right: 0;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            font-size: 1.5rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
            z-index: 10000;
        }

        .close-zoom:hover {
            transform: scale(1.1);
        }

        .zoom-caption {
            text-align: center;
            margin-top: 20px;
            color: var(--primary);
            font-size: 1.2rem;
            font-weight: 600;
        }

        /* Loading Overlay */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 9998;
            backdrop-filter: blur(10px);
            flex-direction: column;
        }

        .loading-overlay.active {
            display: flex;
        }

        .loading-spinner {
            width: 60px;
            height: 60px;
            border: 4px solid rgba(255, 215, 0, 0.3);
            border-radius: 50%;
            border-top: 4px solid var(--primary);
            animation: spin 1s linear infinite;
            margin-bottom: 20px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .loading-text {
            color: var(--primary);
            font-size: 1.2rem;
            font-weight: 600;
        }

        /* Progress Bar untuk Upload */
        .upload-progress {
            width: 80%;
            max-width: 400px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            height: 6px;
            margin: 20px 0;
            overflow: hidden;
            display: none;
        }

        .progress-bar {
            height: 100%;
            background: var(--gradient-gold);
            border-radius: 10px;
            width: 0%;
            transition: width 0.3s ease;
        }

        .upload-percentage-old {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 10px;
            display: none;
        }

        /* ===== NOTIFICATION ===== */
        .notification {
            position: fixed;
            bottom: 40px;
            right: 40px;
            background: var(--gradient-gold);
            color: #000;
            padding: 20px 30px;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            z-index: 1002;
            display: none;
            animation: slideInRight 0.3s ease;
            max-width: 350px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 215, 0, 0.3);
            font-weight: 700;
        }

        @keyframes slideInRight {
            from {
                transform: translateX(100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        /* ===== MOBILE MENU TOGGLE ===== */
        .mobile-menu-toggle {
            display: none;
            position: fixed;
            top: 25px;
            right: 25px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 12px;
            padding: 15px;
            font-size: 1.4rem;
            cursor: pointer;
            z-index: 1004;
            transition: var(--transition);
        }

        /* ===== RESPONSIVE STYLES ===== */
        @media (max-width: 1024px) {
            .sidebar {
                width: 250px;
            }
            
            .main-content {
                margin-left: 250px;
                width: calc(100% - 250px);
            }
            
            .projects-grid {
                grid-template-columns: repeat(auto-fill, minmax(450px, 1fr));
            }
            
            .content-body {
                padding: 30px;
            }
            
            .content-header {
                padding: 25px 30px;
            }
            
            .home-hero {
                padding: 60px 40px;
                min-height: 450px;
                height: 60vh;
            }
            
            .hero-title {
                font-size: 3.2rem;
            }
            
            .chatroom-container {
                height: 65vh;
            }
            
            .dashboard-periods {
                grid-template-columns: 1fr;
            }
            
            .work-grid,
            .achievements-grid {
                grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            }
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 100%;
                max-width: 320px;
                transform: translateX(-100%);
                transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
                position: fixed;
                top: 0;
                left: 0;
                height: 100vh;
                z-index: 1000;
                overflow-y: auto;
            }
            
            .sidebar.active {
                transform: translateX(0);
            }
            
            .main-content {
                margin-left: 0;
                width: 100%;
                height: 100vh;
                position: fixed;
                left: 0;
                right: 0;
            }
            
            .mobile-menu-toggle {
                display: block;
            }
            
            .content-header {
                padding: 20px;
                flex-direction: column;
                align-items: flex-start;
                gap: 20px;
            }
            
            .page-title h2 {
                font-size: 1.8rem;
            }
            
            .content-body {
                padding: 20px;
                min-height: calc(100vh - 120px);
            }
            
            .home-hero {
                padding: 30px 20px;
                height: 65vh;
                min-height: 400px;
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
            
            .hero-subtitle {
                font-size: 1.3rem;
            }
            
            .hero-description {
                font-size: 1.1rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .work-grid,
            .achievements-grid {
                grid-template-columns: 1fr;
            }
            
            .about-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
            
            .stat-card {
                padding: 30px 20px;
            }
            
            .stat-number {
                font-size: 2.8rem;
            }
            
            .contact-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .contact-info {
                grid-template-columns: 1fr;
            }
            
            .chatroom-container {
                height: 60vh;
            }
            
            .message {
                max-width: 85%;
            }
            
            .chatroom-input {
                flex-direction: column;
            }
            
            .zoom-caption {
                font-size: 1rem;
            }
            
            .close-zoom {
                top: -40px;
                right: 10px;
            }
        }

        @media (max-width: 480px) {
            .home-hero {
                padding: 20px 15px;
                height: 60vh;
                min-height: 380px;
            }
            
            .hero-title {
                font-size: 2.2rem;
            }
            
            .hero-badge {
                font-size: 0.9rem;
                padding: 10px 20px;
            }
            
            .hero-subtitle {
                font-size: 1.1rem;
            }
            
            .hero-description {
                font-size: 1rem;
            }
            
            .stats-grid {
                grid-template-columns: 1fr;
            }
            
            .work-image-container,
            .achievement-image-container {
                height: 200px;
            }
            
            .skill-item {
                font-size: 0.9rem;
                padding: 10px 18px;
            }
            
            .content-body {
                padding: 15px;
                min-height: calc(100vh - 110px);
            }
            
            .zoom-caption {
                font-size: 0.9rem;
                margin-top: 10px;
            }
            
            .period-section {
                padding: 25px;
            }
            
            .period-stat {
                padding: 15px;
            }
            
            .period-stat-value {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Mobile Menu Toggle Button -->
    <button class="mobile-menu-toggle" id="mobileMenuToggle">
        <i class="fas fa-bars"></i>
    </button>
    
    <!-- Tombol Tambah Work di Pojok Kanan Atas -->
    <button class="floating-add-btn" id="floatingAddBtn">
        <i class="fas fa-plus-circle"></i> Tambah Work
    </button>

    <!-- Tombol Toggle Efek -->
    <button class="effect-toggle" id="effectToggle">
        <i class="fas fa-magic" id="effectIcon"></i>
        <span id="effectText">Aktifkan Efek</span>
    </button>

    <!-- Container Efek Rain untuk About Page -->
    <div class="rain-container" id="rainContainer"></div>

    <!-- Container Efek Starfall untuk Chat Room -->
    <div class="starfall-container" id="starfallContainer"></div>

    <!-- Overlay untuk efek rain -->
    <div class="effect-overlay rain-overlay" id="rainOverlay" style="display: none;"></div>

    <!-- Overlay untuk efek starfall -->
    <div class="effect-overlay starfall-overlay" id="starfallOverlay" style="display: none;"></div>

    <!-- SIDEBAR ELEGAN (TETAP TANPA SCROLL) -->
    <aside class="sidebar" id="sidebar">
        <div class="sidebar-header">
            <div class="profile-section">
                <div class="profile-img-container" id="profileImgContainer">
                    <div class="profile-img" id="profileImg">
                        <div class="profile-img-placeholder">
                            <i class="fas fa-user-tie" id="profileIcon"></i>
                        </div>
                    </div>
                    <button class="profile-img-upload" id="profileUploadBtn" title="Upload Foto Profile">
                        <i class="fas fa-camera"></i>
                    </button>
                </div>
                <div class="profile-info">
                    <h2>Arya Savariansah</h2>
                    <p>Spesialis Manufaktur</p>
                </div>
            </div>
        </div>
        
        <!-- Menu Navigasi -->
        <ul class="nav-menu">
            <li><a href="#home" class="nav-link active" data-page="home"><i class="fas fa-home"></i> Home</a></li>
            <li><a href="#about" class="nav-link" data-page="about"><i class="fas fa-user"></i> About Me</a></li>
            <li><a href="#work" class="nav-link" data-page="work"><i class="fas fa-briefcase"></i> Work</a></li>
            <li><a href="#achievements" class="nav-link" data-page="achievements"><i class="fas fa-trophy"></i> Achievements</a></li>
            <li><a href="#projects" class="nav-link" data-page="projects"><i class="fas fa-project-diagram"></i> Projects</a></li>
            <li><a href="#dashboard" class="nav-link" data-page="dashboard"><i class="fas fa-chart-line"></i> Dashboard</a></li>
            <li><a href="#chatroom" class="nav-link" data-page="chatroom"><i class="fas fa-comments"></i> Chat Room</a></li>
            <li><a href="#contact" class="nav-link" data-page="contact"><i class="fas fa-envelope"></i> Contact</a></li>
        </ul>
        
        <!-- Admin Panel -->
        <div class="admin-section">
            <button class="admin-toggle" id="adminToggle">
                <i class="fas fa-user-lock"></i> Login Admin
            </button>
            
            <div class="admin-panel" id="adminPanel">
                <h3>Login Admin</h3>
                <input type="password" id="adminPassword" class="admin-input" placeholder="Password Admin">
                <button class="admin-btn" id="adminLogin">Login</button>
                
                <div id="adminControls" style="display: none;">
                    <h3>Edit Mode</h3>
                    <button class="admin-btn" id="toggleEditMode">Aktifkan Edit Mode</button>
                    <button class="admin-btn" id="saveAllData">Simpan Semua Data</button>
                    <button class="admin-btn" id="adminLogout">Logout</button>
                </div>
            </div>
        </div>
        
        <div class="sidebar-footer">
            <p>© 2026 Arya Savariansah. All rights reserved.</p>
        </div>
    </aside>
    
    <!-- KONTEN UTAMA DENGAN SCROLL DI POJOK KANAN -->
    <main class="main-content" id="mainContent">
        <!-- Content Header -->
        <div class="content-header">
            <div class="page-title">
                <h2 id="currentPageTitle">Home</h2>
                <p id="currentPageDesc">Selamat datang di portfolio Arya Savariansah</p>
            </div>
            <div class="edit-status" id="editStatus">
                <i class="fas fa-edit"></i> Edit Mode Aktif
            </div>
        </div>
        
        <!-- Content Body - Pages (SCROLLABLE PENUH) -->
        <div class="content-body" id="contentBody">
            <!-- Home Page - UPDATED -->
            <div class="page active" id="homePage">
                <div class="home-hero">
                    <div class="particles" id="particles"></div>
                    <div class="hero-content">
                        <div class="hero-badge editable">
                            <span id="homeBadge">✨ Lulusan SMK Teknik Permesinan ✨</span>
                            <button class="edit-btn" data-edit="homeBadge">Edit</button>
                        </div>
                        
                        <h1 class="hero-title editable" id="homeTitle">ARYA SAVARIANSAH</h1>
                        <button class="edit-btn" data-edit="homeTitle">Edit</button>
                        
                        <div class="hero-subtitle editable" id="homeSubtitle">
                            <i class="fas fa-star" style="color: var(--primary); margin-right: 10px;"></i>
                            Spesialis Manufaktur & Produksi
                            <i class="fas fa-star" style="color: var(--primary); margin-left: 10px;"></i>
                        </div>
                        <button class="edit-btn" data-edit="homeSubtitle">Edit</button>
                        
                        <p class="hero-description editable" id="homeDescription">
                            Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. 
                            Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, 
                            hingga mechanical drafting.
                        </p>
                        <button class="edit-btn" data-edit="homeDescription">Edit</button>
                        
                        <div class="hero-actions">
                            <button class="upload-btn primary" onclick="changePage('about')" 
                                    style="padding: 15px 35px; font-size: 1rem; background: var(--gradient-gold); color: #000; border: none; border-radius: 50px; font-weight: 700; cursor: pointer; transition: var(--transition);">
                                <i class="fas fa-user"></i> Lihat Profil Lengkap
                            </button>
                        </div>
                    </div>
                </div>
                
                <div class="stats-grid">
                    <div class="stat-card editable">
                        <div class="stat-number" id="stat1Number">15%</div>
                        <div class="stat-label" id="stat1Label">Pengurangan Waktu Setup</div>
                        <button class="edit-btn" data-edit="stat1Number">Edit</button>
                        <button class="edit-btn" data-edit="stat1Label">Edit</button>
                    </div>
                    
                    <div class="stat-card editable">
                        <div class="stat-number" id="stat2Number">60%</div>
                        <div class="stat-label" id="stat2Label">Penurunan Reject Material</div>
                        <button class="edit-btn" data-edit="stat2Number">Edit</button>
                        <button class="edit-btn" data-edit="stat2Label">Edit</button>
                    </div>
                    
                    <div class="stat-card editable">
                        <div class="stat-number" id="stat3Number">20%</div>
                        <div class="stat-label" id="stat3Label">Peningkatan Efisiensi</div>
                        <button class="edit-btn" data-edit="stat3Number">Edit</button>
                        <button class="edit-btn" data-edit="stat3Label">Edit</button>
                    </div>
                    
                    <div class="stat-card editable">
                        <div class="stat-number" id="stat4Number">67%</div>
                        <div class="stat-label" id="stat4Label">Pengurangan Lead Time</div>
                        <button class="edit-btn" data-edit="stat4Number">Edit</button>
                        <button class="edit-btn" data-edit="stat4Label">Edit</button>
                    </div>
                </div>
                
                <div class="quick-links">
                    <h3>Akses Cepat</h3>
                    <div class="links-grid">
                        <div class="link-card" onclick="changePage('work')">
                            <div class="link-icon">
                                <i class="fas fa-briefcase"></i>
                            </div>
                            <h4>Work</h4>
                            <p>Dokumentasi pekerjaan dan proyek yang telah dikerjakan</p>
                        </div>
                        
                        <div class="link-card" onclick="changePage('projects')">
                            <div class="link-icon">
                                <i class="fas fa-project-diagram"></i>
                            </div>
                            <h4>Projects</h4>
                            <p>Proyek dan portofolio pekerjaan terbaik</p>
                        </div>
                        
                        <div class="link-card" onclick="changePage('achievements')">
                            <div class="link-icon">
                                <i class="fas fa-trophy"></i>
                            </div>
                            <h4>Achievements</h4>
                            <p>Sertifikat dan pencapaian profesional</p>
                        </div>
                        
                        <div class="link-card" onclick="changePage('contact')">
                            <div class="link-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <h4>Contact</h4>
                            <p>Hubungi saya untuk kolaborasi dan kerja sama</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- About Me Page -->
            <div class="page" id="aboutPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Tentang Saya</h2>
                
                <div class="about-content">
                    <div>
                        <div class="editable" id="aboutText1">
                            <p>Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. 
                            Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, 
                            hingga mechanical drafting.</p>
                        </div>
                        <button class="edit-btn" data-edit="aboutText1">Edit</button>
                        
                        <div class="editable" id="aboutText2">
                            <p>Memiliki kemampuan dalam meningkatkan efisiensi produksi, menurunkan tingkat reject, 
                            serta mendukung kelancaran proses manufaktur melalui desain teknis dan perencanaan 
                            yang sistematis.</p>
                        </div>
                        <button class="edit-btn" data-edit="aboutText2">Edit</button>
                        
                        <div class="skills-grid">
                            <div class="skill-category editable" id="technicalSkills">
                                <h3>Keahlian Teknis</h3>
                                <div class="skill-items">
                                    <div class="skill-item">AutoCAD</div>
                                    <div class="skill-item">SolidWorks (2D & 3D Drafting)</div>
                                    <div class="skill-item">Membaca & Membuat Gambar Teknik</div>
                                    <div class="skill-item">Bubut, Milling, Molding, Assembly</div>
                                    <div class="skill-item">Production Planning & Stock Monitoring</div>
                                    <div class="skill-item">Quality Control & Problem Solving</div>
                                    <div class="skill-item">Preventive Maintenance & Mold Management</div>
                                    <div class="skill-item">Microsoft Office (Excel, Word, PowerPoint)</div>
                                    <div class="skill-item">Basic ERP / Sistem Monitoring Produksi</div>
                                </div>
                                <button class="add-btn" data-add="technicalSkills">+ Tambah Skill</button>
                            </div>
                            
                            <div class="skill-category editable" id="personalSkills">
                                <h3>Keahlian Personal</h3>
                                <div class="skill-items">
                                    <div class="skill-item">Problem Solving & Berpikir Analitis</div>
                                    <div class="skill-item">Teamwork & Koordinasi Lintas Departemen</div>
                                    <div class="skill-item">Manajemen Waktu & Efisiensi Proses</div>
                                    <div class="skill-item">Detail-Oriented & Teliti dalam pekerjaan</div>
                                    <div class="skill-item">Disiplin & Tanggung Jawab</div>
                                    <div class="skill-item">Proaktif dan Cepat Beradaptasi</div>
                                    <div class="skill-item">Komunikasi Efektif</div>
                                </div>
                                <button class="add-btn" data-add="personalSkills">+ Tambah Skill</button>
                            </div>
                        </div>
                    </div>
                    
                    <div>
                        <h3 style="margin-bottom: 30px; font-size: 1.8rem; color: var(--primary);">Pengalaman Kerja</h3>
                        
                        <div class="experience-timeline">
                            <div class="experience-item editable" id="experience1">
                                <div class="experience-header">
                                    <h3 class="experience-title">Mechanical Drafter Manufacturing</h3>
                                    <div class="experience-date">Jun 2025 - Sekarang</div>
                                </div>
                                <div class="experience-content">
                                    <ul>
                                        <li>Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi</li>
                                        <li>Menyatukan berbagai variasi pengaturan molding menjadi 1 standar variasi, sehingga mempermudah operator dan menekan risiko kesalahan setting</li>
                                        <li>Berhasil mempercepat proses kerja operator bubut dengan membuat drawing detail yang lebih jelas, sehingga mengurangi waktu setup hingga 15% lebih cepat</li>
                                    </ul>
                                </div>
                                <button class="edit-btn" data-edit="experience1">Edit</button>
                                <button class="delete-btn" data-delete="experience1" data-type="experience">Hapus</button>
                            </div>
                            
                            <div class="experience-item editable" id="experience2">
                                <div class="experience-header">
                                    <h3 class="experience-title">Staff Produksi</h3>
                                    <div class="experience-date">Jun 2024 - Jun 2025</div>
                                </div>
                                <div class="experience-content">
                                    <ul>
                                        <li>Menganalisis dan menurunkan tingkat overconsumption material melalui evaluasi data penggunaan bahan, identifikasi penyebab pemborosan, dan koordinasi dengan tim terkait untuk perbaikan proses</li>
                                        <li>Menurunkan non-conformance bahan Div. Produksi dengan cara melakukan monitoring bahan</li>
                                        <li>Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dalam kurun waktu Desember 2024-Maret 2025 dengan cara membuat monitoring Stock WIP dan planning item Produksi</li>
                                        <li>Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)</li>
                                    </ul>
                                </div>
                                <button class="edit-btn" data-edit="experience2">Edit</button>
                                <button class="delete-btn" data-delete="experience2" data-type="experience">Hapus</button>
                            </div>
                        </div>
                        <button class="add-btn" data-add="experience">+ Tambah Pengalaman</button>
                    </div>
                </div>
            </div>
            
            <!-- Work Page - DUPLIKAT DARI ACHIEVEMENTS -->
            <div class="page" id="workPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Work</h2>
                
                <div style="background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%); border-radius: var(--border-radius); padding: 40px; margin-bottom: 40px; border: 1px solid rgba(255, 215, 0, 0.1); box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3); position: relative; overflow: hidden;">
                    <h2 style="color: var(--primary); margin-bottom: 15px; font-size: 1.8rem;">Dokumentasi Pekerjaan</h2>
                    <p style="color: var(--gray); line-height: 1.7; margin-bottom: 15px;">Koleksi foto dokumentasi pekerjaan dan proyek yang telah dikerjakan sebagai Mechanical Drafter dan Staff Produksi.</p>
                    <p style="color: var(--gray); line-height: 1.7;"><strong>Kategori:</strong> Mechanical Drafting, Production Work, Quality Control, Process Improvement</p>
                </div>
                
                <!-- Work Grid -->
                <div class="work-grid" id="workContainer">
                    <!-- Work items akan di-render oleh JavaScript -->
                </div>
                
                <!-- Tombol Add untuk Work -->
                <button class="add-btn" data-add="work" id="addWorkBtn">+ Tambah Work</button>
            </div>
            
            <!-- Achievements Page -->
            <div class="page" id="achievementsPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Pencapaian & Sertifikat</h2>
                
                <div class="achievements-grid" id="achievementsContainer">
                    <!-- Achievement cards akan di-render oleh JavaScript -->
                </div>
                <button class="add-btn" data-add="achievement">+ Tambah Pencapaian</button>
            </div>
            
            <!-- Projects Page -->
            <div class="page" id="projectsPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Proyek & Portofolio</h2>
                
                <div class="projects-grid" id="projectsContainer">
                    <div class="project-card editable" id="project1">
                        <h3><i class="fas fa-drafting-compass"></i> Sistem Pendataan Molding</h3>
                        <p>Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi</p>
                        
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-value">100%</span>
                                <span class="stat-label">Data Manual</span>
                            </div>
                            <div class="stat">
                                <span class="stat-value improvement">↓ 40%</span>
                                <span class="stat-label">Downtime</span>
                            </div>
                            <div class="stat">
                                <span class="stat-value">15%</span>
                                <span class="stat-label">Setup Time ↓</span>
                            </div>
                        </div>
                        <button class="edit-btn" data-edit="project1">Edit</button>
                        <button class="delete-btn" data-delete="project1" data-type="project">Hapus</button>
                    </div>
                    
                    <div class="project-card editable" id="project2">
                        <h3><i class="fas fa-chart-line"></i> Optimasi Produksi WIP</h3>
                        <p>Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dengan monitoring Stock WIP dan planning item Produksi</p>
                        
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-value">2 Ton</span>
                                <span class="stat-label">Sebelum</span>
                            </div>
                            <div class="stat">
                                <span class="stat-value improvement">↓ 63.8%</span>
                                <span class="stat-label">Pengurangan</span>
                            </div>
                            <div class="stat">
                                <span class="stat-value">724.5 kg</span>
                                <span class="stat-label">Sesudah</span>
                            </div>
                        </div>
                        <button class="edit-btn" data-edit="project2">Edit</button>
                        <button class="delete-btn" data-delete="project2" data-type="project">Hapus</button>
                    </div>
                    
                    <div class="project-card editable" id="project3">
                        <h3><i class="fas fa-cogs"></i> Reduksi Reject Mesin Spiral</h3>
                        <p>Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)</p>
                        
                        <div class="project-stats">
                            <div class="stat">
                                <span class="stat-value">8%</span>
                                <span class="stat-label">Sebelum</span>
                            </div>
                            <div class="stat">
                                <span class="stat-value reduction">↓ 62.5%</span>
                                <span class="stat-label">Penurunan</span>
                            </div>
                            <div class="stat">
                                <span class="stat-value">3%</span>
                                <span class="stat-label">Sesudah</span>
                            </div>
                        </div>
                        <button class="edit-btn" data-edit="project3">Edit</button>
                        <button class="delete-btn" data-delete="project3" data-type="project">Hapus</button>
                    </div>
                </div>
                <button class="add-btn" data-add="project">+ Tambah Proyek</button>
            </div>
            
            <!-- Dashboard Page -->
            <div class="page" id="dashboardPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Dashboard Statistik</h2>
                
                <div class="dashboard-periods">
                    <!-- Staff Production Period -->
                    <div class="period-section editable" id="staffPeriod">
                        <div class="period-header">
                            <h2 class="period-title">Staff Production</h2>
                            <div class="period-date">
                                <i class="far fa-calendar"></i> Jun 2024 - Jun 2025
                            </div>
                        </div>
                        
                        <div class="period-stats">
                            <div class="period-stat editable" id="staffStat1">
                                <div class="period-stat-value staff">60%</div>
                                <div class="period-stat-label">Penurunan Reject Material</div>
                                <button class="edit-btn" data-edit="staffStat1">Edit</button>
                            </div>
                            
                            <div class="period-stat editable" id="staffStat2">
                                <div class="period-stat-value staff">63.8%</div>
                                <div class="period-stat-label">Pengurangan WIP Inventory</div>
                                <button class="edit-btn" data-edit="staffStat2">Edit</button>
                            </div>
                            
                            <div class="period-stat editable" id="staffStat3">
                                <div class="period-stat-value staff">62.5%</div>
                                <div class="period-stat-label">Penurunan Reject Mesin Spiral</div>
                                <button class="edit-btn" data-edit="staffStat3">Edit</button>
                            </div>
                            
                            <div class="period-stat editable" id="staffStat4">
                                <div class="period-stat-value staff">90%</div>
                                <div class="period-stat-label">Kesesuaian Dokumen (KPH)</div>
                                <button class="edit-btn" data-edit="staffStat4">Edit</button>
                            </div>
                        </div>
                        <button class="edit-btn" data-edit="staffPeriod">Edit</button>
                    </div>
                    
                    <!-- Drafter Period -->
                    <div class="period-section editable" id="drafterPeriod">
                        <div class="period-header">
                            <h2 class="period-title">Mechanical Drafter</h2>
                            <div class="period-date">
                                <i class="far fa-calendar"></i> Jun 2025 - Sekarang
                            </div>
                        </div>
                        
                        <div class="period-stats">
                            <div class="period-stat editable" id="drafterStat1">
                                <div class="period-stat-value drafter">15%</div>
                                <div class="period-stat-label">Pengurangan Waktu Setup</div>
                                <button class="edit-btn" data-edit="drafterStat1">Edit</button>
                            </div>
                            
                            <div class="period-stat editable" id="drafterStat2">
                                <div class="period-stat-value drafter">40%</div>
                                <div class="period-stat-label">Pengurangan Downtime</div>
                                <button class="edit-btn" data-edit="drafterStat2">Edit</button>
                            </div>
                            
                            <div class="period-stat editable" id="drafterStat3">
                                <div class="period-stat-value drafter">67%</div>
                                <div class="period-stat-label">Pengurangan Lead Time</div>
                                <button class="edit-btn" data-edit="drafterStat3">Edit</button>
                            </div>
                            
                            <div class="period-stat editable" id="drafterStat4">
                                <div class="period-stat-value drafter">100%</div>
                                <div class="period-stat-label">Standarisasi Molding Setting</div>
                                <button class="edit-btn" data-edit="drafterStat4">Edit</button>
                            </div>
                        </div>
                        <button class="edit-btn" data-edit="drafterPeriod">Edit</button>
                    </div>
                </div>
                
                <div class="dashboard-chart editable" id="dashboardChart">
                    <h3>Grafik Perbandingan Performa</h3>
                    <div style="height: 350px; background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%); border-radius: 12px; display: flex; align-items: flex-end; padding: 25px; border: 1px solid rgba(255, 215, 0, 0.1);">
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 180px; width: 50px; background: var(--gradient-success); margin: 0 15px; border-radius: 8px 8px 0 0;"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Staff</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 220px; width: 50px; background: var(--gradient-purple); margin: 0 15px; border-radius: 8px 8px 0 0;"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Drafter</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 280px; width: 50px; background: var(--gradient-gold); margin: 0 15px; border-radius: 8px 8px 0 0;"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Total</div>
                        </div>
                    </div>
                    <button class="edit-btn" data-edit="dashboardChart">Edit</button>
                </div>
            </div>
            
            <!-- Chatroom Page -->
            <div class="page" id="chatroomPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; text-align: center;">Chat Room</h2>
                <p style="text-align: center; margin-bottom: 50px; color: var(--gray); max-width: 800px; margin-left: auto; margin-right: auto; font-size: 1.2rem; line-height: 1.6;">
                    Feel free to share your thoughts, suggestions, questions, or anything else!
                </p>
                
                <div class="chatroom-container">
                    <div class="chatroom-header">
                        <h3>Live Chat Room</h3>
                        <p>Join the conversation with other visitors</p>
                    </div>
                    
                    <div class="chatroom-messages" id="chatMessages">
                        <div class="message">
                            <div class="message-info">
                                <span class="message-user">Vernita Chesnauer</span>
                                <span class="message-time">01/04/2025, 14:00</span>
                            </div>
                            <div class="message-content">
                                Hahnyuga! Love the design of this portfolio!
                            </div>
                        </div>
                        
                        <div class="message">
                            <div class="message-info">
                                <span class="message-user">Rufa Resto Ramadhani</span>
                                <span class="message-time">01/04/2025, 14:37</span>
                            </div>
                            <div class="message-content">
                                Halo mas! Awesome portfolio website!
                            </div>
                        </div>
                    </div>
                    
                    <div class="chatroom-input">
                        <input type="text" id="chatInput" placeholder="Type your message here...">
                        <button id="sendMessage">Send</button>
                    </div>
                </div>
            </div>
            
            <!-- Contact Page -->
            <div class="page" id="contactPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Hubungi Saya</h2>
                <div class="contact-content">
                    <div class="contact-info">
                        <div class="contact-card editable" id="contactEmail">
                            <div class="contact-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <h3>Email</h3>
                            <p>aryasavarinasah@gmail.com</p>
                            <button class="edit-btn" data-edit="contactEmail">Edit</button>
                        </div>
                        
                        <div class="contact-card editable" id="contactPhone">
                            <div class="contact-icon">
                                <i class="fas fa-phone"></i>
                            </div>
                            <h3>Telepon</h3>
                            <p>089520336532</p>
                            <button class="edit-btn" data-edit="contactPhone">Edit</button>
                        </div>
                        
                        <div class="contact-card editable" id="contactLocation">
                            <div class="contact-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <h3>Lokasi</h3>
                            <p>Kosambi, Indonesia</p>
                            <button class="edit-btn" data-edit="contactLocation">Edit</button>
                        </div>
                        
                        <div class="contact-card editable" id="contactLinkedin">
                            <div class="contact-icon">
                                <i class="fab fa-linkedin"></i>
                            </div>
                            <h3>LinkedIn</h3>
                            <p>linkedin.com/in/arya-savariansah</p>
                            <button class="edit-btn" data-edit="contactLinkedin">Edit</button>
                        </div>
                    </div>
                    
                    <div class="contact-form">
                        <h3>Kirim Pesan</h3>
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="name">Nama</label>
                                <input type="text" id="name" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="email">Email</label>
                                <input type="email" id="email" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="message">Pesan</label>
                                <textarea id="message" required></textarea>
                            </div>
                            
                            <button type="submit" class="submit-btn">Kirim Pesan</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </main>
    
    <!-- Modal untuk Upload Foto -->
    <div class="modal" id="imageUploadModal">
        <div class="modal-content">
            <h3 class="modal-title" id="modalTitle">Upload Foto</h3>
            <div class="form-group">
                <input type="file" id="imageInput" accept="image/*" class="admin-input">
            </div>
            <div class="image-preview" id="imagePreview">
                <img id="previewImage" src="" alt="Preview">
            </div>
            <div class="modal-buttons">
                <button class="modal-btn primary" id="saveImageBtn">Simpan Foto</button>
                <button class="modal-btn secondary" id="cancelImageBtn">Batal</button>
                <button class="modal-btn secondary" id="removeImageBtn" style="display: none;">Hapus Foto</button>
            </div>
        </div>
    </div>

    <!-- Modal Upload Work -->
    <div class="modal upload-modal" id="workUploadModal">
        <div class="upload-modal-content">
            <button class="upload-modal-close" id="closeUploadModal">
                <i class="fas fa-times"></i>
            </button>
            
            <div class="upload-modal-header">
                <h2 class="upload-modal-title">Tambah Work Baru</h2>
                <p class="upload-modal-subtitle">Tambahkan dokumentasi pekerjaan Anda</p>
            </div>
            
            <form class="upload-form" id="workUploadForm">
                <div class="form-row">
                    <div class="form-group">
                        <label for="workTitle"><i class="fas fa-heading"></i> Judul Pekerjaan</label>
                        <input type="text" id="workTitle" placeholder="Contoh: Standarisasi Molding Setting" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="workDate"><i class="far fa-calendar"></i> Tanggal</label>
                        <input type="text" id="workDate" placeholder="DD/MM/YYYY" required>
                    </div>
                </div>
                
                <div class="form-row">
                    <div class="form-group">
                        <label for="workCategory"><i class="fas fa-tag"></i> Kategori</label>
                        <select id="workCategory" required>
                            <option value="">Pilih Kategori</option>
                            <option value="Mechanical Drafting">Mechanical Drafting</option>
                            <option value="Production Work">Production Work</option>
                            <option value="Quality Control">Quality Control</option>
                            <option value="Process Improvement">Process Improvement</option>
                            <option value="Maintenance">Maintenance</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="workDescription"><i class="fas fa-align-left"></i> Deskripsi Singkat</label>
                        <input type="text" id="workDescription" placeholder="Jelaskan pekerjaan ini secara singkat" required>
                    </div>
                </div>
                
                <div class="upload-image-area" id="imageDropArea">
                    <div class="upload-image-icon">
                        <i class="fas fa-cloud-upload-alt"></i>
                    </div>
                    <div class="upload-image-text">Upload Foto</div>
                    <div class="upload-image-subtext">Drag & drop gambar atau klik untuk memilih</div>
                    <button type="button" class="upload-browse-btn" id="browseImageBtn">
                        <i class="fas fa-folder-open"></i> Browse Files
                    </button>
                    <input type="file" id="imageFileInput" accept="image/*" style="display: none;">
                    
                    <div class="upload-progress-container" id="uploadProgressContainer">
                        <div class="upload-progress-bar" id="uploadProgressBar"></div>
                    </div>
                    <div class="upload-percentage" id="uploadPercentage">0%</div>
                    
                    <div class="upload-image-preview" id="imagePreviewContainer">
                        <img id="imagePreview" src="" alt="Preview">
                    </div>
                    
                    <div class="image-actions" id="imageActions" style="display: none;">
                        <button type="button" class="image-action-btn" id="changeImageBtn">
                            <i class="fas fa-sync-alt"></i> Ganti Foto
                        </button>
                        <button type="button" class="image-action-btn" id="removeImageBtn">
                            <i class="fas fa-trash-alt"></i> Hapus
                        </button>
                    </div>
                </div>
                
                <div class="upload-modal-buttons">
                    <button type="submit" class="upload-modal-btn primary" id="saveWorkBtn">
                        <i class="fas fa-save"></i> Simpan Work
                    </button>
                    <button type="button" class="upload-modal-btn secondary" id="cancelUploadBtn">
                        <i class="fas fa-times"></i> Batal
                    </button>
                </div>
            </form>
        </div>
    </div>
    
    <!-- Modal Zoom untuk Gambar -->
    <div class="modal zoom-modal" id="zoomModal">
        <button class="close-zoom" id="closeZoom">
            <i class="fas fa-times"></i>
        </button>
        <div class="zoom-content">
            <img id="zoomedImage" class="zoomed-image" src="" alt="Zoomed Image">
            <div class="zoom-caption" id="zoomCaption"></div>
        </div>
    </div>
    
    <!-- Loading Overlay -->
    <div class="loading-overlay" id="loadingOverlay">
        <div class="loading-spinner"></div>
        <div class="loading-text" id="loadingText">Loading...</div>
        <div class="upload-progress" id="uploadProgress">
            <div class="progress-bar" id="progressBar"></div>
        </div>
        <div class="upload-percentage-old" id="uploadPercentageOld">0%</div>
    </div>
    
    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <script>
        // Data aplikasi dengan fitur foto dan Work
        const appData = {
            user: {
                name: "Arya Savariansah",
                title: "Spesialis Manufaktur",
                email: "aryasavarinasah@gmail.com",
                phone: "089520336532",
                location: "Kosambi, Indonesia",
                linkedin: "linkedin.com/in/arya-savariansah",
                profileImage: null
            },
            pages: {
                home: {
                    title: "Home",
                    description: "Selamat datang di portfolio Arya Savariansah",
                    badge: "✨ Lulusan SMK Teknik Permesinan ✨",
                    mainTitle: "ARYA SAVARIANSAH",
                    subtitle: "Spesialis Manufaktur & Produksi",
                    descriptionText: "Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, hingga mechanical drafting.",
                    stats: [
                        { number: "15%", label: "Pengurangan Waktu Setup" },
                        { number: "60%", label: "Penurunan Reject Material" },
                        { number: "20%", label: "Peningkatan Efisiensi" },
                        { number: "67%", label: "Pengurangan Lead Time" }
                    ]
                },
                about: {
                    title: "About Me",
                    description: "Tentang latar belakang dan keahlian saya",
                    sections: [
                        {
                            id: "aboutText1",
                            content: "Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, hingga mechanical drafting."
                        },
                        {
                            id: "aboutText2",
                            content: "Memiliki kemampuan dalam meningkatkan efisiensi produksi, menurunkan tingkat reject, serta mendukung kelancaran proses manufaktur melalui desain teknis dan perencanaan yang sistematis."
                        }
                    ],
                    skills: {
                        technical: [
                            "AutoCAD", "SolidWorks (2D & 3D Drafting)", "Membaca & Membuat Gambar Teknik",
                            "Bubut, Milling, Molding, Assembly", "Production Planning & Stock Monitoring",
                            "Quality Control & Problem Solving", "Preventive Maintenance & Mold Management",
                            "Microsoft Office (Excel, Word, PowerPoint)", "Basic ERP / Sistem Monitoring Produksi"
                        ],
                        personal: [
                            "Problem Solving & Berpikir Analitis", "Teamwork & Koordinasi Lintas Departemen",
                            "Manajemen Waktu & Efisiensi Proses", "Detail-Oriented & Teliti dalam pekerjaan",
                            "Disiplin & Tanggung Jawab", "Proaktif dan Cepat Beradaptasi", "Komunikasi Efektif"
                        ]
                    },
                    experiences: [
                        {
                            id: "experience1",
                            title: "Mechanical Drafter Manufacturing",
                            date: "Jun 2025 - Sekarang",
                            items: [
                                "Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi",
                                "Menyatukan berbagai variasi pengaturan molding menjadi 1 standar variasi, sehingga mempermudah operator dan menekan risiko kesalahan setting",
                                "Berhasil mempercepat proses kerja operator bubut dengan membuat drawing detail yang lebih jelas, sehingga mengurangi waktu setup hingga 15% lebih cepat"
                            ]
                        },
                        {
                            id: "experience2",
                            title: "Staff Produksi",
                            date: "Jun 2024 - Jun 2025",
                            items: [
                                "Menganalisis dan menurunkan tingkat overconsumption material melalui evaluasi data penggunaan bahan, identifikasi penyebab pemborosan, dan koordinasi dengan tim terkait untuk perbaikan proses",
                                "Menurunkan non-conformance bahan Div. Produksi dengan cara melakukan monitoring bahan",
                                "Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dalam kurun waktu Desember 2024-Maret 2025 dengan cara membuat monitoring Stock WIP dan planning item Produksi",
                                "Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)"
                            ]
                        }
                    ]
                },
                work: {
                    title: "Work",
                    description: "Dokumentasi pekerjaan dan proyek",
                    items: [
                        {
                            id: "work1",
                            title: "Standarisasi Molding Setting",
                            date: "15/03/2025",
                            category: "Mechanical Drafting",
                            description: "Menyatukan berbagai variasi pengaturan molding menjadi 1 standar variasi, sehingga mempermudah operator dan menekan risiko kesalahan setting",
                            image: "https://images.unsplash.com/photo-1579226905180-636c76d14d1a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "work2",
                            title: "Monitoring WIP Inventory",
                            date: "20/02/2025",
                            category: "Production Work",
                            description: "Membuat sistem monitoring stock WIP dan planning item produksi untuk meningkatkan productivity penggunaan bahan dari 2 Ton menjadi 724,5 kg",
                            image: "https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "work3",
                            title: "Reduksi Reject Mesin Spiral",
                            date: "10/01/2025",
                            category: "Quality Control",
                            description: "Melakukan TFT (Task Force Team) untuk menurunkan reject dari 8% menjadi 3% pada mesin spiral melalui analisis akar masalah dan perbaikan proses",
                            image: "https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "work4",
                            title: "Optimasi Material Management",
                            date: "05/04/2025",
                            category: "Process Improvement",
                            description: "Pelatihan manajemen material untuk mengurangi overconsumption dan meningkatkan efisiensi penggunaan bahan produksi",
                            image: "https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "work5",
                            title: "Preventive Maintenance System",
                            date: "25/03/2025",
                            category: "Maintenance",
                            description: "Implementasi sistem preventive maintenance berdasarkan lifetime usage molding untuk mengurangi downtime produksi",
                            image: "https://images.unsplash.com/photo-1579226905180-636c76d14d1a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "work6",
                            title: "Production Planning Meeting",
                            date: "12/04/2025",
                            category: "Production Work",
                            description: "Rutinitas meeting perencanaan produksi untuk koordinasi tim dan evaluasi progress pekerjaan",
                            image: "https://images.unsplash.com/photo-1552664730-d307ca884978?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        }
                    ],
                    categories: ["Mechanical Drafting", "Production Work", "Quality Control", "Process Improvement", "Maintenance"]
                },
                achievements: {
                    title: "Achievements",
                    description: "Pencapaian dan sertifikat profesional",
                    items: [
                        {
                            id: "achievement1",
                            title: "Health, Safety, Environment and Quality (HSEQ)",
                            date: "Sertifikasi Profesional",
                            description: "Sertifikasi profesional dalam bidang kesehatan, keselamatan, lingkungan, dan kualitas untuk industri manufaktur",
                            image: "https://images.unsplash.com/photo-1556761175-b413da4baf72?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "achievement2",
                            title: "Introduction to Information Security Course",
                            date: "Sertifikasi Keamanan Informasi",
                            description: "Sertifikasi dasar keamanan informasi untuk memahami prinsip-prinsip keamanan data dalam sistem produksi",
                            image: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "achievement3",
                            title: "Lean Manufacturing Workshop",
                            date: "Workshop 2024",
                            description: "Workshop implementasi lean manufacturing untuk meningkatkan efisiensi dan mengurangi waste dalam proses produksi",
                            image: "https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        },
                        {
                            id: "achievement4",
                            title: "Technical Drawing Excellence Award",
                            date: "Penghargaan Internal 2025",
                            description: "Penghargaan untuk detail dan akurasi gambar teknik yang membantu mempercepat proses setup mesin",
                            image: "https://images.unsplash.com/photo-1579226905180-636c76d14d1a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80"
                        }
                    ]
                },
                projects: {
                    title: "Projects",
                    description: "Proyek dan portofolio pekerjaan",
                    items: [
                        {
                            id: "project1",
                            title: "Sistem Pendataan Molding",
                            description: "Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi",
                            stats: [
                                { value: "100%", label: "Data Manual" },
                                { value: "↓ 40%", label: "Downtime", type: "improvement" },
                                { value: "15%", label: "Setup Time ↓" }
                            ]
                        },
                        {
                            id: "project2",
                            title: "Optimasi Produksi WIP",
                            description: "Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dengan monitoring Stock WIP dan planning item Produksi",
                            stats: [
                                { value: "2 Ton", label: "Sebelum" },
                                { value: "↓ 63.8%", label: "Pengurangan", type: "improvement" },
                                { value: "724.5 kg", label: "Sesudah" }
                            ]
                        },
                        {
                            id: "project3",
                            title: "Reduksi Reject Mesin Spiral",
                            description: "Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)",
                            stats: [
                                { value: "8%", label: "Sebelum" },
                                { value: "↓ 62.5%", label: "Penurunan", type: "reduction" },
                                { value: "3%", label: "Sesudah" }
                            ]
                        }
                    ]
                },
                dashboard: {
                    title: "Dashboard",
                    description: "Statistik dan metrik performa",
                    periods: [
                        {
                            id: "staffPeriod",
                            title: "Staff Production",
                            date: "Jun 2024 - Jun 2025",
                            stats: [
                                { id: "staffStat1", value: "60%", label: "Penurunan Reject Material" },
                                { id: "staffStat2", value: "63.8%", label: "Pengurangan WIP Inventory" },
                                { id: "staffStat3", value: "62.5%", label: "Penurunan Reject Mesin Spiral" },
                                { id: "staffStat4", value: "90%", label: "Kesesuaian Dokumen (KPH)" }
                            ]
                        },
                        {
                            id: "drafterPeriod",
                            title: "Mechanical Drafter",
                            date: "Jun 2025 - Sekarang",
                            stats: [
                                { id: "drafterStat1", value: "15%", label: "Pengurangan Waktu Setup" },
                                { id: "drafterStat2", value: "40%", label: "Pengurangan Downtime" },
                                { id: "drafterStat3", value: "67%", label: "Pengurangan Lead Time" },
                                { id: "drafterStat4", value: "100%", label: "Standarisasi Molding Setting" }
                            ]
                        }
                    ]
                },
                contact: {
                    title: "Contact",
                    description: "Hubungi saya untuk kolaborasi",
                    items: [
                        { id: "contactEmail", type: "email", value: "aryasavarinasah@gmail.com", icon: "fas fa-envelope", label: "Email" },
                        { id: "contactPhone", type: "phone", value: "089520336532", icon: "fas fa-phone", label: "Telepon" },
                        { id: "contactLocation", type: "location", value: "Kosambi, Indonesia", icon: "fas fa-map-marker-alt", label: "Lokasi" },
                        { id: "contactLinkedin", type: "linkedin", value: "linkedin.com/in/arya-savariansah", icon: "fab fa-linkedin", label: "LinkedIn" }
                    ]
                }
            }
        };

        // Konfigurasi Admin
        const ADMIN_PASSWORD = "arya2025";
        let isAdminLoggedIn = false;
        let isEditMode = false;
        let currentPage = "home";
        let currentUploadType = null; // "profile", "achievement", atau "work"
        let currentItemId = null;

        // Variables untuk modal upload Work
        let currentImageFile = null;
        let currentImageUrl = null;

        // Variables untuk efek
        let rainEffectActive = false;
        let starfallEffectActive = false;
        let currentEffectPage = null;

        // DOM Ready
        document.addEventListener('DOMContentLoaded', function() {
            loadFromLocalStorage();
            setupNavigation();
            setupAdminPanel();
            setupChat();
            setupContactForm();
            setupMobileMenu();
            setupImageUploadModal();
            setupWorkUploadModal();
            setupZoomModal();
            setupResponsiveBehavior();
            renderPage(currentPage);
            updateAdminUI();
            setupContentHeight();
            renderProfileImage();
            centerHeroContent(); // Panggil fungsi untuk center konten
            
            // Setup efek
            setupEffects();
            
            // Tambahkan event listener untuk gambar profile (zoom)
            document.getElementById('profileImg').addEventListener('click', function() {
                if (appData.user.profileImage) {
                    openZoom(appData.user.profileImage, 'Profile Picture');
                }
            });
            
            // Setup event listener untuk tombol add Work
            document.getElementById('addWorkBtn').addEventListener('click', function() {
                if (isAdminLoggedIn || isEditMode) {
                    openWorkUploadModal();
                } else {
                    showNotification('Silakan login sebagai admin untuk menambah work', 'error');
                }
            });
            
            // Setup event listener untuk floating add button
            const floatingAddBtn = document.getElementById('floatingAddBtn');
            if (floatingAddBtn) {
                floatingAddBtn.addEventListener('click', function() {
                    if (isAdminLoggedIn || isEditMode) {
                        openWorkUploadModal();
                    } else {
                        showNotification('Silakan login sebagai admin untuk menambah Work', 'error');
                    }
                });
            }
            
            // Buat efek partikel
            createParticles();
            
            // Setup resize untuk center content
            window.addEventListener('resize', centerHeroContent);
        });

        // Fungsi untuk membuat konten hero tepat di tengah
        function centerHeroContent() {
            const homeHero = document.querySelector('.home-hero');
            const heroContent = document.querySelector('.hero-content');
            
            if (homeHero && heroContent) {
                // Reset margin sebelumnya
                heroContent.style.marginTop = '0';
                
                // Hitung tinggi yang tersedia
                const heroHeight = homeHero.offsetHeight;
                const contentHeight = heroContent.offsetHeight;
                
                // Jika konten lebih kecil dari container, center kan secara vertikal
                if (contentHeight < heroHeight) {
                    const topMargin = Math.max(0, (heroHeight - contentHeight) / 2);
                    heroContent.style.marginTop = `${topMargin}px`;
                }
            }
        }

        // Setup content height adjustment
        function setupContentHeight() {
            function adjustContentHeight() {
                const mainContent = document.querySelector('.main-content');
                const contentBody = document.querySelector('.content-body');
                const activePage = document.querySelector('.page.active');
                const contentHeader = document.querySelector('.content-header');
                
                if (mainContent && contentBody && activePage && contentHeader) {
                    const headerHeight = contentHeader.offsetHeight;
                    const windowHeight = window.innerHeight;
                    const pageHeight = activePage.offsetHeight;
                    
                    // Set minimum height untuk content body
                    contentBody.style.minHeight = Math.max(pageHeight, windowHeight - headerHeight) + 'px';
                }
            }
            
            setTimeout(adjustContentHeight, 300);
            window.addEventListener('resize', adjustContentHeight);
            
            const navLinks = document.querySelectorAll('.nav-link');
            navLinks.forEach(link => {
                link.addEventListener('click', function() {
                    setTimeout(adjustContentHeight, 500);
                });
            });
            
            // Initial adjustment
            adjustContentHeight();
        }

        // Setup responsive behavior
        function setupResponsiveBehavior() {
            function handleResize() {
                const sidebar = document.getElementById('sidebar');
                const mobileMenuToggle = document.getElementById('mobileMenuToggle');
                const mainContent = document.getElementById('mainContent');
                const floatingAddBtn = document.getElementById('floatingAddBtn');
                const effectToggle = document.getElementById('effectToggle');
                
                if (window.innerWidth > 768) {
                    sidebar.classList.remove('active');
                    sidebar.style.transform = 'translateX(0)';
                    if (mobileMenuToggle) {
                        mobileMenuToggle.style.display = 'none';
                    }
                    if (mainContent) {
                        mainContent.style.position = 'fixed';
                        mainContent.style.right = '0';
                        mainContent.style.left = 'auto';
                        mainContent.style.width = 'calc(100% - ' + (sidebar.offsetWidth || 280) + 'px)';
                    }
                    // Position floating button
                    if (floatingAddBtn && isAdminLoggedIn && currentPage === 'work') {
                        floatingAddBtn.style.top = '100px';
                        floatingAddBtn.style.right = '40px';
                        floatingAddBtn.style.bottom = 'auto';
                    }
                    // Position effect button
                    if (effectToggle && (currentPage === 'about' || currentPage === 'chatroom')) {
                        effectToggle.style.bottom = '100px';
                        effectToggle.style.right = '40px';
                        effectToggle.style.top = 'auto';
                    }
                } else {
                    if (mobileMenuToggle) {
                        mobileMenuToggle.style.display = 'block';
                    }
                    if (mainContent) {
                        mainContent.style.position = 'fixed';
                        mainContent.style.left = '0';
                        mainContent.style.right = '0';
                        mainContent.style.width = '100%';
                    }
                    // Position floating button untuk mobile
                    if (floatingAddBtn && isAdminLoggedIn && currentPage === 'work') {
                        floatingAddBtn.style.top = 'auto';
                        floatingAddBtn.style.bottom = '30px';
                        floatingAddBtn.style.right = '20px';
                    }
                    // Position effect button untuk mobile
                    if (effectToggle && (currentPage === 'about' || currentPage === 'chatroom')) {
                        effectToggle.style.top = 'auto';
                        effectToggle.style.bottom = '80px';
                        effectToggle.style.right = '20px';
                    }
                }
                
                // Recalculate content height
                setTimeout(setupContentHeight, 100);
                // Center hero content
                setTimeout(centerHeroContent, 100);
            }
            
            window.addEventListener('resize', handleResize);
            handleResize();
        }

        // Setup mobile menu toggle
        function setupMobileMenu() {
            const mobileMenuToggle = document.getElementById('mobileMenuToggle');
            const sidebar = document.getElementById('sidebar');
            
            if (mobileMenuToggle && sidebar) {
                mobileMenuToggle.addEventListener('click', function() {
                    sidebar.classList.toggle('active');
                    
                    if (sidebar.classList.contains('active')) {
                        this.innerHTML = '<i class="fas fa-times"></i>';
                    } else {
                        this.innerHTML = '<i class="fas fa-bars"></i>';
                    }
                });
                
                document.addEventListener('click', function(e) {
                    if (window.innerWidth <= 768) {
                        if (!sidebar.contains(e.target) && 
                            !mobileMenuToggle.contains(e.target) &&
                            sidebar.classList.contains('active')) {
                            sidebar.classList.remove('active');
                            mobileMenuToggle.innerHTML = '<i class="fas fa-bars"></i>';
                        }
                    }
                });
            }
        }

        // Setup efek
        function setupEffects() {
            const effectToggle = document.getElementById('effectToggle');
            
            if (effectToggle) {
                effectToggle.addEventListener('click', function() {
                    toggleEffects();
                });
            }
            
            // Setup untuk halaman About
            const aboutPage = document.getElementById('aboutPage');
            if (aboutPage) {
                aboutPage.addEventListener('mouseenter', function() {
                    if (currentPage === 'about' && !rainEffectActive) {
                        showEffectToggle('Rain Effect', 'fas fa-cloud-rain');
                    }
                });
                
                aboutPage.addEventListener('mouseleave', function() {
                    if (!rainEffectActive) {
                        hideEffectToggle();
                    }
                });
            }
            
            // Setup untuk halaman Chat Room
            const chatroomPage = document.getElementById('chatroomPage');
            if (chatroomPage) {
                chatroomPage.addEventListener('mouseenter', function() {
                    if (currentPage === 'chatroom' && !starfallEffectActive) {
                        showEffectToggle('Starfall Effect', 'fas fa-star');
                    }
                });
                
                chatroomPage.addEventListener('mouseleave', function() {
                    if (!starfallEffectActive) {
                        hideEffectToggle();
                    }
                });
            }
        }

        // Fungsi untuk menampilkan tombol efek
        function showEffectToggle(text, iconClass) {
            const effectToggle = document.getElementById('effectToggle');
            const effectText = document.getElementById('effectText');
            const effectIcon = document.getElementById('effectIcon');
            
            if (effectToggle && effectText && effectIcon) {
                effectText.textContent = text;
                effectIcon.className = iconClass;
                effectToggle.style.display = 'flex';
                currentEffectPage = currentPage;
            }
        }

        // Fungsi untuk menyembunyikan tombol efek
        function hideEffectToggle() {
            const effectToggle = document.getElementById('effectToggle');
            if (effectToggle) {
                effectToggle.style.display = 'none';
                currentEffectPage = null;
            }
        }

        // Fungsi untuk toggle efek
        function toggleEffects() {
            if (currentEffectPage === 'about') {
                toggleRainEffect();
            } else if (currentEffectPage === 'chatroom') {
                toggleStarfallEffect();
            }
        }

        // Fungsi untuk toggle efek rain
        function toggleRainEffect() {
            rainEffectActive = !rainEffectActive;
            const rainContainer = document.getElementById('rainContainer');
            const rainOverlay = document.getElementById('rainOverlay');
            const starfallOverlay = document.getElementById('starfallOverlay');
            const effectToggle = document.getElementById('effectToggle');
            const effectText = document.getElementById('effectText');
            
            if (rainEffectActive) {
                // Matikan efek starfall jika aktif
                if (starfallEffectActive) {
                    toggleStarfallEffect();
                }
                
                // Aktifkan efek rain
                rainContainer.style.display = 'block';
                rainOverlay.style.display = 'block';
                setTimeout(() => {
                    rainOverlay.style.opacity = '1';
                }, 10);
                
                effectText.textContent = 'Matikan Rain Effect';
                
                // Buat efek rain yang lebih elegan
                createElegantRainDrops();
                
                // Tambahkan class khusus untuk about page
                document.getElementById('aboutPage').classList.add('rain-active');
                
                // Ubah warna teks dan ikon untuk feedback visual
                effectToggle.style.background = 'linear-gradient(135deg, #00bcd4 0%, #00ffff 100%)';
                effectToggle.style.color = '#000';
                
                showNotification('Rain Effect diaktifkan! Suasana hujan yang menenangkan.', 'success');
            } else {
                // Matikan efek rain
                rainContainer.style.display = 'none';
                rainOverlay.style.opacity = '0';
                setTimeout(() => {
                    rainOverlay.style.display = 'none';
                }, 1000);
                effectText.textContent = 'Aktifkan Rain Effect';
                
                // Reset tombol effect
                effectToggle.style.background = 'var(--gradient-gold)';
                effectToggle.style.color = '#000';
                
                // Hapus class khusus untuk about page
                document.getElementById('aboutPage').classList.remove('rain-active');
                
                showNotification('Rain Effect dimatikan.', 'info');
                hideEffectToggle();
            }
        }

        // Fungsi untuk membuat rain drops yang lebih elegan
        function createElegantRainDrops() {
            const rainContainer = document.getElementById('rainContainer');
            if (!rainContainer || !rainEffectActive) return;
            
            // Clear existing rain drops
            rainContainer.innerHTML = '';
            
            // Tambahkan background glow
            const backgroundGlow = document.createElement('div');
            backgroundGlow.style.position = 'absolute';
            backgroundGlow.style.top = '0';
            backgroundGlow.style.left = '0';
            backgroundGlow.style.width = '100%';
            backgroundGlow.style.height = '100%';
            backgroundGlow.style.background = 'radial-gradient(circle at center, rgba(0, 100, 200, 0.05) 0%, transparent 70%)';
            backgroundGlow.style.filter = 'blur(20px)';
            rainContainer.appendChild(backgroundGlow);
            
            // Buat 80 rain drops dengan variasi
            for (let i = 0; i < 80; i++) {
                setTimeout(() => {
                    if (!rainEffectActive) return;
                    
                    createSingleRainDrop(i);
                    
                }, i * 30);
            }
            
            // Buat rain drops secara kontinu
            if (rainEffectActive) {
                setTimeout(createElegantRainDrops, 5000);
            }
        }

        // Fungsi untuk membuat single rain drop elegan
        function createSingleRainDrop(index) {
            const rainContainer = document.getElementById('rainContainer');
            
            const rainDrop = document.createElement('div');
            rainDrop.className = 'rain-drop';
            
            // Random position
            const left = 10 + Math.random() * 80;
            rainDrop.style.left = `${left}%`;
            
            // Random animation delay
            const delay = Math.random() * 3;
            rainDrop.style.animationDelay = `${delay}s`;
            
            // Random animation duration
            const duration = 1.5 + Math.random() * 1;
            rainDrop.style.animationDuration = `${duration}s`;
            
            // Random opacity
            const opacity = 0.5 + Math.random() * 0.5;
            rainDrop.style.opacity = opacity;
            
            // Random color variation
            const colors = [
                'rgba(0, 255, 255, 0.8)',
                'rgba(0, 200, 255, 0.7)',
                'rgba(0, 150, 255, 0.6)',
                'rgba(100, 200, 255, 0.7)'
            ];
            const randomColor = colors[Math.floor(Math.random() * colors.length)];
            rainDrop.style.background = `linear-gradient(to bottom, 
                transparent 0%, 
                ${randomColor} 30%,
                rgba(0, 255, 255, 0.5) 70%,
                transparent 100%)`;
            
            rainContainer.appendChild(rainDrop);
            
            // Buat efek ripple saat rain drop "jatuh"
            setTimeout(() => {
                if (rainEffectActive) {
                    createElegantRipple(left, 90 + Math.random() * 10);
                    
                    // Tambahkan efek cahaya kecil
                    createRainLight(left, 90 + Math.random() * 10, randomColor);
                }
            }, duration * 1000 - 500);
        }

        // Fungsi untuk membuat efek ripple yang elegan
        function createElegantRipple(left, top) {
            if (!rainEffectActive) return;
            
            const rainContainer = document.getElementById('rainContainer');
            const ripple = document.createElement('div');
            ripple.className = 'rain-ripple';
            
            ripple.style.left = `${left}%`;
            ripple.style.top = `${top}%`;
            
            // Random size
            const size = 4 + Math.random() * 8;
            ripple.style.width = `${size}px`;
            ripple.style.height = `${size}px`;
            
            // Random color variation
            const colors = ['rgba(0, 255, 255, 0.4)', 'rgba(0, 200, 255, 0.3)', 'rgba(100, 220, 255, 0.35)'];
            const randomColor = colors[Math.floor(Math.random() * colors.length)];
            ripple.style.borderColor = randomColor;
            
            // Random animation duration
            const duration = 0.8 + Math.random() * 0.7;
            ripple.style.animationDuration = `${duration}s`;
            
            rainContainer.appendChild(ripple);
            
            // Hapus ripple setelah animasi selesai
            setTimeout(() => {
                if (ripple.parentNode) {
                    ripple.parentNode.removeChild(ripple);
                }
            }, duration * 1000);
        }

        // Fungsi untuk membuat efek cahaya rain
        function createRainLight(left, top, color) {
            if (!rainEffectActive) return;
            
            const rainContainer = document.getElementById('rainContainer');
            const light = document.createElement('div');
            light.className = 'rain-light';
            
            light.style.left = `${left}%`;
            light.style.top = `${top}%`;
            
            // Extract base color
            light.style.background = `radial-gradient(circle, 
                ${color.replace('0.8', '0.3').replace('0.7', '0.25').replace('0.6', '0.2')} 0%, 
                rgba(0, 255, 255, 0.1) 40%,
                transparent 70%)`;
            
            rainContainer.appendChild(light);
            
            // Hapus light setelah animasi selesai
            setTimeout(() => {
                if (light.parentNode) {
                    light.parentNode.removeChild(light);
                }
            }, 500);
        }

        // Fungsi untuk toggle efek starfall yang lebih elegan
        function toggleStarfallEffect() {
            starfallEffectActive = !starfallEffectActive;
            const starfallContainer = document.getElementById('starfallContainer');
            const starfallOverlay = document.getElementById('starfallOverlay');
            const rainOverlay = document.getElementById('rainOverlay');
            const effectToggle = document.getElementById('effectToggle');
            const effectText = document.getElementById('effectText');
            
            if (starfallEffectActive) {
                // Matikan efek rain jika aktif
                if (rainEffectActive) {
                    toggleRainEffect();
                }
                
                // Aktifkan efek starfall
                starfallContainer.style.display = 'block';
                starfallOverlay.style.display = 'block';
                setTimeout(() => {
                    starfallOverlay.style.opacity = '1';
                }, 10);
                
                effectText.textContent = 'Matikan Starfall Effect';
                
                // Buat efek starfall yang lebih elegan
                createElegantStars();
                
                // Tambahkan class khusus untuk chatroom
                document.getElementById('chatroomPage').classList.add('starfall-active');
                
                // Ubah warna tombol
                effectToggle.style.background = 'linear-gradient(135deg, #ff9500 0%, #ffcc00 100%)';
                effectToggle.style.color = '#000';
                
                showNotification('Starfall Effect diaktifkan! Galaksi bintang yang memukau.', 'success');
            } else {
                // Matikan efek starfall
                starfallContainer.style.display = 'none';
                starfallOverlay.style.opacity = '0';
                setTimeout(() => {
                    starfallOverlay.style.display = 'none';
                }, 1000);
                effectText.textContent = 'Aktifkan Starfall Effect';
                
                // Reset tombol effect
                effectToggle.style.background = 'var(--gradient-gold)';
                effectToggle.style.color = '#000';
                
                // Hapus class khusus untuk chatroom
                document.getElementById('chatroomPage').classList.remove('starfall-active');
                
                showNotification('Starfall Effect dimatikan.', 'info');
                hideEffectToggle();
            }
        }

        // Fungsi untuk membuat stars yang lebih elegan
        function createElegantStars() {
            const starfallContainer = document.getElementById('starfallContainer');
            if (!starfallContainer || !starfallEffectActive) return;
            
            // Clear existing stars
            starfallContainer.innerHTML = '';
            
            // Tambahkan background nebula
            const nebula = document.createElement('div');
            nebula.style.position = 'absolute';
            nebula.style.top = '0';
            nebula.style.left = '0';
            nebula.style.width = '100%';
            nebula.style.height = '100%';
            nebula.style.background = `
                radial-gradient(circle at 30% 20%, rgba(255, 215, 0, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 70% 80%, rgba(255, 100, 0, 0.02) 0%, transparent 50%),
                radial-gradient(circle at 50% 50%, rgba(200, 150, 0, 0.01) 0%, transparent 50%)
            `;
            nebula.style.filter = 'blur(15px)';
            starfallContainer.appendChild(nebula);
            
            // Buat 40 stars dengan variasi
            for (let i = 0; i < 40; i++) {
                setTimeout(() => {
                    if (!starfallEffectActive) return;
                    
                    createSingleStar(i);
                    
                }, i * 100);
            }
            
            // Buat stars secara kontinu
            if (starfallEffectActive) {
                setTimeout(createElegantStars, 6000);
            }
        }

        // Fungsi untuk membuat single star elegan
        function createSingleStar(index) {
            const starfallContainer = document.getElementById('starfallContainer');
            
            const star = document.createElement('div');
            star.className = 'star';
            
            // Random position
            const left = Math.random() * 100;
            star.style.left = `${left}%`;
            
            // Random size
            const size = 2 + Math.random() * 6;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            
            // Random animation delay
            const delay = Math.random() * 5;
            star.style.animationDelay = `${delay}s`;
            
            // Random animation duration
            const duration = 3 + Math.random() * 4;
            star.style.animationDuration = `${duration}s`;
            
            // Random gradient color
            const gradients = [
                'radial-gradient(circle, rgba(255, 215, 0, 0.9) 0%, rgba(255, 200, 0, 0.7) 100%)',
                'radial-gradient(circle, rgba(255, 100, 0, 0.8) 0%, rgba(255, 150, 0, 0.6) 100%)',
                'radial-gradient(circle, rgba(255, 255, 200, 0.9) 0%, rgba(255, 255, 150, 0.7) 100%)',
                'radial-gradient(circle, rgba(200, 255, 255, 0.8) 0%, rgba(150, 255, 255, 0.6) 100%)'
            ];
            const randomGradient = gradients[Math.floor(Math.random() * gradients.length)];
            star.style.background = randomGradient;
            
            // Random opacity
            const opacity = 0.6 + Math.random() * 0.4;
            star.style.opacity = opacity;
            
            // Random rotation
            const rotate = Math.random() * 360;
            star.style.setProperty('--star-rotation', `${rotate}deg`);
            
            starfallContainer.appendChild(star);
            
            // Buat efek trail
            createStarTrail(left, 0, randomGradient);
            
            // Buat efek burst saat star "jatuh"
            setTimeout(() => {
                if (starfallEffectActive) {
                    const top = 90 + Math.random() * 10;
                    createElegantStarBurst(left, top, randomGradient);
                    
                    // Hapus star setelah burst
                    setTimeout(() => {
                        if (star.parentNode) {
                            star.parentNode.removeChild(star);
                        }
                    }, 500);
                }
            }, duration * 1000 - 1000);
        }

        // Fungsi untuk membuat efek trail bintang
        function createStarTrail(left, top, gradient) {
            if (!starfallEffectActive) return;
            
            const starfallContainer = document.getElementById('starfallContainer');
            const trail = document.createElement('div');
            trail.className = 'star-trail';
            
            trail.style.left = `${left}%`;
            trail.style.top = `${top}%`;
            
            // Random angle
            const angle = -30 + Math.random() * 60;
            trail.style.setProperty('--trail-angle', `${angle}deg`);
            
            // Random length
            const length = 50 + Math.random() * 100;
            trail.style.width = `${length}px`;
            
            // Color based on gradient
            let trailColor = 'rgba(255, 215, 0, 0.1)';
            if (gradient.includes('255, 100, 0')) trailColor = 'rgba(255, 100, 0, 0.08)';
            if (gradient.includes('255, 255, 200')) trailColor = 'rgba(255, 255, 200, 0.1)';
            if (gradient.includes('200, 255, 255')) trailColor = 'rgba(200, 255, 255, 0.08)';
            
            trail.style.background = `linear-gradient(90deg, 
                transparent 0%, 
                ${trailColor} 30%,
                rgba(255, 215, 0, 0.05) 70%,
                transparent 100%)`;
            
            starfallContainer.appendChild(trail);
            
            // Hapus trail setelah animasi selesai
            setTimeout(() => {
                if (trail.parentNode) {
                    trail.parentNode.removeChild(trail);
                }
            }, 1000);
        }

        // Fungsi untuk membuat efek burst yang elegan
        function createElegantStarBurst(left, top, gradient) {
            if (!starfallEffectActive) return;
            
            const starfallContainer = document.getElementById('starfallContainer');
            
            // Buat burst utama
            const burst = document.createElement('div');
            burst.className = 'star-burst';
            
            burst.style.left = `${left}%`;
            burst.style.top = `${top}%`;
            
            // Extract color dari gradient
            let burstColor = '#ffd700';
            if (gradient.includes('255, 100, 0')) burstColor = '#ff6400';
            else if (gradient.includes('255, 255, 200')) burstColor = '#ffffc8';
            else if (gradient.includes('200, 255, 255')) burstColor = '#c8ffff';
            
            burst.style.color = burstColor;
            burst.style.background = `radial-gradient(circle, ${burstColor} 0%, transparent 70%)`;
            
            // Random size
            const size = 10 + Math.random() * 20;
            burst.style.width = `${size}px`;
            burst.style.height = `${size}px`;
            
            starfallContainer.appendChild(burst);
            
            // Buat partikel kecil
            for (let i = 0; i < 12; i++) {
                setTimeout(() => {
                    const particle = document.createElement('div');
                    particle.className = 'star-particle';
                    
                    particle.style.left = `${left}%`;
                    particle.style.top = `${top}%`;
                    
                    // Random angle untuk partikel
                    const angle = (i * 30) + Math.random() * 15;
                    const rad = angle * (Math.PI / 180);
                    const x = Math.cos(rad);
                    const y = Math.sin(rad);
                    
                    particle.style.setProperty('--particle-x', x);
                    particle.style.setProperty('--particle-y', y);
                    
                    particle.style.background = burstColor;
                    particle.style.boxShadow = `0 0 5px ${burstColor}`;
                    
                    starfallContainer.appendChild(particle);
                    
                    // Hapus partikel setelah animasi
                    setTimeout(() => {
                        if (particle.parentNode) {
                            particle.parentNode.removeChild(particle);
                        }
                    }, 1000);
                }, i * 30);
            }
            
            // Hapus burst setelah animasi selesai
            setTimeout(() => {
                if (burst.parentNode) {
                    burst.parentNode.removeChild(burst);
                }
            }, 1200);
        }

        // Setup modal zoom
        function setupZoomModal() {
            const zoomModal = document.getElementById('zoomModal');
            const closeZoom = document.getElementById('closeZoom');
            
            // Event listener untuk close zoom
            closeZoom.addEventListener('click', function() {
                zoomModal.classList.remove('active');
                document.body.style.overflow = 'auto';
            });
            
            // Close saat klik di luar gambar
            zoomModal.addEventListener('click', function(e) {
                if (e.target === zoomModal) {
                    zoomModal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            });
            
            // Close dengan ESC key
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape' && zoomModal.classList.contains('active')) {
                    zoomModal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            });
        }

        // Fungsi universal untuk membuka zoom
        function openZoom(imageSrc, caption = '') {
            if (!imageSrc) return;
            
            const zoomModal = document.getElementById('zoomModal');
            const zoomedImage = document.getElementById('zoomedImage');
            const zoomCaption = document.getElementById('zoomCaption');
            
            showLoading('Memuat gambar...');
            
            // Preload gambar
            const img = new Image();
            img.onload = function() {
                zoomedImage.src = imageSrc;
                zoomCaption.textContent = caption;
                zoomedImage.classList.add('loaded');
                
                setTimeout(() => {
                    zoomModal.classList.add('active');
                    hideLoading();
                    document.body.style.overflow = 'hidden';
                }, 300);
            };
            img.onerror = function() {
                hideLoading();
                showNotification('Gagal memuat gambar', 'error');
            };
            img.src = imageSrc;
        }

        // Setup Work Upload Modal
        function setupWorkUploadModal() {
            const modal = document.getElementById('workUploadModal');
            const closeBtn = document.getElementById('closeUploadModal');
            const cancelBtn = document.getElementById('cancelUploadBtn');
            const browseBtn = document.getElementById('browseImageBtn');
            const fileInput = document.getElementById('imageFileInput');
            const dropArea = document.getElementById('imageDropArea');
            const imagePreview = document.getElementById('imagePreview');
            const previewContainer = document.getElementById('imagePreviewContainer');
            const imageActions = document.getElementById('imageActions');
            const changeImageBtn = document.getElementById('changeImageBtn');
            const removeImageBtn = document.getElementById('removeImageBtn');
            const form = document.getElementById('workUploadForm');
            const saveBtn = document.getElementById('saveWorkBtn');
            const progressContainer = document.getElementById('uploadProgressContainer');
            const progressBar = document.getElementById('uploadProgressBar');
            const percentage = document.getElementById('uploadPercentage');

            // Open modal
            window.openWorkUploadModal = function(editItemId = null) {
                if (!isAdminLoggedIn && !isEditMode) {
                    showNotification('Silakan login sebagai admin untuk menambah work', 'error');
                    return;
                }
                
                resetUploadForm();
                
                // Jika edit mode, isi form dengan data yang ada
                if (editItemId) {
                    const item = appData.pages.work.items.find(i => i.id === editItemId);
                    if (item) {
                        document.getElementById('workTitle').value = item.title;
                        document.getElementById('workDate').value = item.date;
                        document.getElementById('workCategory').value = item.category;
                        document.getElementById('workDescription').value = item.description;
                        
                        if (item.image) {
                            currentImageUrl = item.image;
                            imagePreview.src = item.image;
                            previewContainer.style.display = 'block';
                            imageActions.style.display = 'flex';
                        }
                        
                        // Ubah teks tombol
                        saveBtn.innerHTML = '<i class="fas fa-save"></i> Update Work';
                        saveBtn.dataset.editId = editItemId;
                        
                        // Update modal title
                        document.querySelector('.upload-modal-title').textContent = 'Edit Work';
                        document.querySelector('.upload-modal-subtitle').textContent = 'Edit dokumentasi pekerjaan';
                    }
                } else {
                    // Reset untuk mode add
                    saveBtn.innerHTML = '<i class="fas fa-save"></i> Simpan Work';
                    delete saveBtn.dataset.editId;
                    
                    // Reset modal title
                    document.querySelector('.upload-modal-title').textContent = 'Tambah Work Baru';
                    document.querySelector('.upload-modal-subtitle').textContent = 'Tambahkan dokumentasi pekerjaan Anda';
                }
                
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
                
                // Fokus ke input pertama
                setTimeout(() => {
                    document.getElementById('workTitle').focus();
                }, 100);
            };

            // Close modal
            function closeUploadModal() {
                modal.classList.remove('active');
                document.body.style.overflow = 'auto';
                resetUploadForm();
            }

            // Close button event
            closeBtn.addEventListener('click', closeUploadModal);
            cancelBtn.addEventListener('click', closeUploadModal);

            // Close on outside click
            modal.addEventListener('click', function(e) {
                if (e.target === modal) {
                    closeUploadModal();
                }
            });

            // Close on ESC key
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape' && modal.classList.contains('active')) {
                    closeUploadModal();
                }
            });

            // Browse button event
            browseBtn.addEventListener('click', function() {
                fileInput.click();
            });

            // File input change event
            fileInput.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    handleImageFile(file);
                }
            });

            // Drag and drop events
            ['dragenter', 'dragover', 'dragleave', 'drop'].forEach(eventName => {
                dropArea.addEventListener(eventName, preventDefaults, false);
            });

            function preventDefaults(e) {
                e.preventDefault();
                e.stopPropagation();
            }

            ['dragenter', 'dragover'].forEach(eventName => {
                dropArea.addEventListener(eventName, highlight, false);
            });

            ['dragleave', 'drop'].forEach(eventName => {
                dropArea.addEventListener(eventName, unhighlight, false);
            });

            function highlight() {
                dropArea.classList.add('drag-over');
            }

            function unhighlight() {
                dropArea.classList.remove('drag-over');
            }

            // Drop event
            dropArea.addEventListener('drop', function(e) {
                const dt = e.dataTransfer;
                const files = dt.files;
                
                if (files.length > 0) {
                    const file = files[0];
                    if (file.type.match('image.*')) {
                        handleImageFile(file);
                    } else {
                        showNotification('Hanya file gambar yang diperbolehkan', 'error');
                    }
                }
            });

            // Handle image file - OPTIMIZED
            function handleImageFile(file) {
                // Validasi file
                if (file.size > 10 * 1024 * 1024) {
                    showNotification('Ukuran file terlalu besar. Maksimal 10MB.', 'error');
                    return;
                }

                if (!file.type.match('image.*')) {
                    showNotification('Hanya file gambar yang diperbolehkan.', 'error');
                    return;
                }

                currentImageFile = file;
                
                // Tampilkan progress bar sebentar untuk feedback visual
                showProgress();
                updateProgress(30);
                
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    // Langsung ke 100% setelah file dibaca
                    updateProgress(100);
                    
                    currentImageUrl = e.target.result;
                    imagePreview.src = currentImageUrl;
                    previewContainer.style.display = 'block';
                    imageActions.style.display = 'flex';
                    
                    // Sembunyikan progress bar setelah 300ms
                    setTimeout(() => {
                        hideProgress();
                    }, 300);
                    
                    showNotification('Gambar berhasil diupload!', 'success');
                };
                
                reader.onerror = function() {
                    hideProgress();
                    showNotification('Gagal membaca file gambar', 'error');
                };
                
                reader.readAsDataURL(file);
            }

            // Change image button
            changeImageBtn.addEventListener('click', function() {
                fileInput.click();
            });

            // Remove image button
            removeImageBtn.addEventListener('click', function() {
                currentImageFile = null;
                currentImageUrl = null;
                previewContainer.style.display = 'none';
                imageActions.style.display = 'none';
                fileInput.value = '';
                showNotification('Gambar berhasil dihapus', 'info');
            });

            // Form submit - OPTIMIZED untuk loading cepat
            form.addEventListener('submit', function(e) {
                e.preventDefault();
                
                if (!isAdminLoggedIn && !isEditMode) {
                    showNotification('Silakan login sebagai admin untuk menambah work', 'error');
                    return;
                }
                
                const title = document.getElementById('workTitle').value.trim();
                const date = document.getElementById('workDate').value.trim();
                const category = document.getElementById('workCategory').value;
                const description = document.getElementById('workDescription').value.trim();
                
                if (!title || !date || !category || !description) {
                    showNotification('Harap isi semua field yang wajib diisi', 'error');
                    return;
                }
                
                // Validasi format tanggal
                const dateRegex = /^\d{2}\/\d{2}\/\d{4}$/;
                if (!dateRegex.test(date)) {
                    showNotification('Format tanggal harus DD/MM/YYYY', 'error');
                    return;
                }
                
                // Tampilkan loading singkat
                showLoading('Menyimpan Work...');
                
                // Simpan TANPA DELAY BERLEBIHAN - langsung proses
                setTimeout(() => {
                    const editId = saveBtn.dataset.editId;
                    
                    if (editId) {
                        // Edit mode
                        const item = appData.pages.work.items.find(i => i.id === editId);
                        if (item) {
                            item.title = title;
                            item.date = date;
                            item.category = category;
                            item.description = description;
                            if (currentImageUrl) item.image = currentImageUrl;
                            
                            renderWorkPage();
                            saveToLocalStorage();
                            closeUploadModal();
                            hideLoading();
                            
                            showNotification('Work berhasil diperbarui!', 'success');
                        }
                    } else {
                        // Add mode - gunakan timestamp untuk ID yang unik
                        const newId = 'work_' + Date.now();
                        const newItem = {
                            id: newId,
                            title: title,
                            date: date,
                            category: category,
                            description: description,
                            image: currentImageUrl
                        };
                        
                        appData.pages.work.items.unshift(newItem); // Tambah di awal array
                        
                        renderWorkPage();
                        saveToLocalStorage();
                        closeUploadModal();
                        hideLoading();
                        
                        // Scroll ke halaman work untuk melihat item baru
                        const workPage = document.getElementById('workPage');
                        if (workPage) {
                            workPage.scrollIntoView({ behavior: 'smooth' });
                        }
                        
                        showNotification('Work berhasil ditambahkan!', 'success');
                    }
                }, 500); // Delay minimal hanya 500ms (bukan 1000ms)
            });

            // Show progress bar
            function showProgress() {
                progressContainer.style.display = 'block';
                percentage.style.display = 'block';
                updateProgress(0);
            }

            // Hide progress bar
            function hideProgress() {
                progressContainer.style.display = 'none';
                percentage.style.display = 'none';
                updateProgress(0);
            }

            // Update progress
            function updateProgress(value) {
                progressBar.style.width = value + '%';
                percentage.textContent = Math.round(value) + '%';
            }
        }

        // Reset upload form
        function resetUploadForm() {
            const form = document.getElementById('workUploadForm');
            const imagePreview = document.getElementById('imagePreview');
            const previewContainer = document.getElementById('imagePreviewContainer');
            const imageActions = document.getElementById('imageActions');
            const fileInput = document.getElementById('imageFileInput');
            const progressContainer = document.getElementById('uploadProgressContainer');
            const percentage = document.getElementById('uploadPercentage');
            
            if (form) form.reset();
            if (imagePreview) imagePreview.src = '';
            if (previewContainer) previewContainer.style.display = 'none';
            if (imageActions) imageActions.style.display = 'none';
            if (fileInput) fileInput.value = '';
            if (progressContainer) progressContainer.style.display = 'none';
            if (percentage) percentage.style.display = 'none';
            
            currentImageFile = null;
            currentImageUrl = null;
        }

        // Setup image upload modal
        function setupImageUploadModal() {
            const profileUploadBtn = document.getElementById('profileUploadBtn');
            const imageInput = document.getElementById('imageInput');
            const imagePreview = document.getElementById('imagePreview');
            const previewImage = document.getElementById('previewImage');
            const saveImageBtn = document.getElementById('saveImageBtn');
            const cancelImageBtn = document.getElementById('cancelImageBtn');
            const removeImageBtn = document.getElementById('removeImageBtn');
            const modal = document.getElementById('imageUploadModal');
            
            // Event listener untuk upload foto profile
            if (profileUploadBtn) {
                profileUploadBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    if (isAdminLoggedIn || isEditMode) {
                        openImageUploadModal('profile');
                    } else {
                        // Jika bukan admin, zoom gambar profile jika ada
                        if (appData.user.profileImage) {
                            openZoom(appData.user.profileImage, 'Profile Picture');
                        }
                    }
                });
            }
            
            // Event listener untuk file input change
            imageInput.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    // Validasi file
                    if (file.size > 5 * 1024 * 1024) {
                        showNotification('Ukuran file terlalu besar. Maksimal 5MB.', 'error');
                        return;
                    }
                    
                    if (!file.type.match('image.*')) {
                        showNotification('Hanya file gambar yang diperbolehkan.', 'error');
                        return;
                    }
                    
                    // Simulasi upload dengan progress
                    simulateUploadWithProgress(file, previewImage, imagePreview);
                }
            });
            
            // Event listener untuk save button
            saveImageBtn.addEventListener('click', function() {
                if (previewImage.src) {
                    showLoading('Menyimpan gambar...');
                    showProgress();
                    
                    // Simulasi proses save dengan progress
                    let progress = 0;
                    const interval = setInterval(() => {
                        progress += 10;
                        updateProgress(progress);
                        
                        if (progress >= 100) {
                            clearInterval(interval);
                            
                            // Save data
                            if (currentUploadType === 'profile') {
                                appData.user.profileImage = previewImage.src;
                                renderProfileImage();
                                showNotification('Foto profile berhasil diupload!', 'success');
                            } else if (currentUploadType === 'achievement' && currentItemId) {
                                const achievement = appData.pages.achievements.items.find(a => a.id === currentItemId);
                                if (achievement) {
                                    achievement.image = previewImage.src;
                                    renderAchievementsPage();
                                    showNotification('Foto achievement berhasil diupload!', 'success');
                                }
                            } else if (currentUploadType === 'work' && currentItemId) {
                                const work = appData.pages.work.items.find(d => d.id === currentItemId);
                                if (work) {
                                    work.image = previewImage.src;
                                    renderWorkPage();
                                    showNotification('Foto Work berhasil diupload!', 'success');
                                }
                            }
                            
                            setTimeout(() => {
                                modal.classList.remove('active');
                                resetUploadModal();
                                hideLoading();
                            }, 300);
                        }
                    }, 100);
                }
            });
            
            // Event listener untuk cancel button
            cancelImageBtn.addEventListener('click', function() {
                modal.classList.remove('active');
                resetUploadModal();
            });
            
            // Event listener untuk remove button
            removeImageBtn.addEventListener('click', function() {
                showLoading('Menghapus gambar...');
                
                setTimeout(() => {
                    if (currentUploadType === 'profile') {
                        appData.user.profileImage = null;
                        renderProfileImage();
                        showNotification('Foto profile berhasil dihapus!', 'success');
                    } else if (currentUploadType === 'achievement' && currentItemId) {
                        const achievement = appData.pages.achievements.items.find(a => a.id === currentItemId);
                        if (achievement) {
                            achievement.image = null;
                            renderAchievementsPage();
                            showNotification('Foto achievement berhasil dihapus!', 'success');
                        }
                    } else if (currentUploadType === 'work' && currentItemId) {
                        const work = appData.pages.work.items.find(d => d.id === currentItemId);
                        if (work) {
                            work.image = null;
                            renderWorkPage();
                            showNotification('Foto Work berhasil dihapus!', 'success');
                        }
                    }
                    
                    modal.classList.remove('active');
                    resetUploadModal();
                    hideLoading();
                }, 500);
            });
            
            // Event listener untuk klik di luar modal
            modal.addEventListener('click', function(e) {
                if (e.target === modal) {
                    modal.classList.remove('active');
                    resetUploadModal();
                }
            });
        }

        // Fungsi untuk simulasi upload dengan progress bar
        function simulateUploadWithProgress(file, previewImage, imagePreview) {
            showLoading('Mengupload gambar...');
            showProgress();
            
            let progress = 0;
            const interval = setInterval(() => {
                progress += 20;
                updateProgress(progress);
                
                if (progress >= 100) {
                    clearInterval(interval);
                    
                    // Baca file sebagai Data URL
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        previewImage.src = event.target.result;
                        imagePreview.style.display = 'block';
                        removeImageBtn.style.display = 'inline-block';
                        hideLoading();
                        showNotification('Gambar berhasil diupload!', 'success');
                    };
                    reader.readAsDataURL(file);
                }
            }, 100);
        }

        // Reset upload modal
        function resetUploadModal() {
            const imageInput = document.getElementById('imageInput');
            const imagePreview = document.getElementById('imagePreview');
            const previewImage = document.getElementById('previewImage');
            const removeImageBtn = document.getElementById('removeImageBtn');
            
            imageInput.value = '';
            imagePreview.style.display = 'none';
            previewImage.src = '';
            removeImageBtn.style.display = 'none';
            currentUploadType = null;
            currentItemId = null;
        }

        // Open image upload modal
        function openImageUploadModal(type, itemId = null) {
            // PERIKSA APAKAH USER ADALAH ADMIN
            if (!isAdminLoggedIn && !isEditMode) {
                showNotification('Silakan login sebagai admin untuk mengupload foto', 'error');
                return;
            }
            
            currentUploadType = type;
            currentItemId = itemId;
            
            const modal = document.getElementById('imageUploadModal');
            const modalTitle = document.getElementById('modalTitle');
            const removeImageBtn = document.getElementById('removeImageBtn');
            const previewImage = document.getElementById('previewImage');
            const imagePreview = document.getElementById('imagePreview');
            
            let currentImage = null;
            let itemTitle = '';
            
            if (type === 'profile') {
                modalTitle.textContent = 'Upload Foto Profile';
                currentImage = appData.user.profileImage;
                itemTitle = 'Profile Picture';
            } else if (type === 'achievement' && itemId) {
                const achievement = appData.pages.achievements.items.find(a => a.id === itemId);
                if (achievement) {
                    modalTitle.textContent = `Upload Foto untuk: ${achievement.title}`;
                    currentImage = achievement.image;
                    itemTitle = achievement.title;
                }
            } else if (type === 'work' && itemId) {
                const work = appData.pages.work.items.find(d => d.id === itemId);
                if (work) {
                    modalTitle.textContent = `Upload Foto untuk: ${work.title}`;
                    currentImage = work.image;
                    itemTitle = work.title;
                }
            }
            
            if (currentImage) {
                previewImage.src = currentImage;
                imagePreview.style.display = 'block';
                removeImageBtn.style.display = 'inline-block';
            } else {
                imagePreview.style.display = 'none';
                removeImageBtn.style.display = 'none';
            }
            
            modal.classList.add('active');
        }

        // Tambahkan fungsi particles untuk home page
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            if (!particlesContainer) return;
            
            particlesContainer.innerHTML = '';
            
            for (let i = 0; i < 15; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                // Random size and position
                const size = Math.random() * 4 + 2;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${Math.random() * 100}%`;
                particle.style.top = `${Math.random() * 100}%`;
                
                // Random animation delay
                particle.style.animationDelay = `${Math.random() * 10}s`;
                particle.style.animationDuration = `${Math.random() * 10 + 10}s`;
                
                particlesContainer.appendChild(particle);
            }
        }

        // Render profile image
        function renderProfileImage() {
            const profileImg = document.getElementById('profileImg');
            const profileIcon = document.getElementById('profileIcon');
            
            if (appData.user.profileImage) {
                profileImg.style.background = 'none';
                profileImg.innerHTML = `<img src="${appData.user.profileImage}" alt="Profile" style="width: 100%; height: 100%; object-fit: cover;">`;
                profileIcon.style.display = 'none';
            } else {
                profileImg.style.background = 'var(--gradient-gold)';
                profileImg.innerHTML = `<div class="profile-img-placeholder"><i class="fas fa-user-tie" id="profileIcon"></i></div>`;
            }
        }

        // Load data dari localStorage
        function loadFromLocalStorage() {
            const savedData = localStorage.getItem('portfolioData');
            if (savedData) {
                try {
                    const data = JSON.parse(savedData);
                    Object.assign(appData, data);
                } catch (e) {
                    console.error("Error loading data from localStorage:", e);
                }
            }
        }

        // Save data ke localStorage
        function saveToLocalStorage() {
            localStorage.setItem('portfolioData', JSON.stringify(appData));
            showNotification('Data berhasil disimpan!', 'success');
        }

        // Setup navigation
        function setupNavigation() {
            const navLinks = document.querySelectorAll('.nav-link');
            
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const pageId = this.getAttribute('data-page');
                    
                    navLinks.forEach(l => l.classList.remove('active'));
                    this.classList.add('active');
                    
                    changePage(pageId);
                    
                    if (window.innerWidth <= 768) {
                        document.getElementById('sidebar').classList.remove('active');
                        document.getElementById('mobileMenuToggle').innerHTML = '<i class="fas fa-bars"></i>';
                    }
                });
            });
        }

        // Change page
        function changePage(pageId) {
            // Matikan semua efek saat berpindah halaman
            if (rainEffectActive) {
                toggleRainEffect();
            }
            if (starfallEffectActive) {
                toggleStarfallEffect();
            }
            hideEffectToggle();
            
            document.querySelectorAll('.page').forEach(page => {
                if (page.classList.contains('active')) {
                    page.style.opacity = '0';
                    page.style.transform = 'translateY(30px)';
                    setTimeout(() => {
                        page.classList.remove('active');
                        page.style.opacity = '';
                        page.style.transform = '';
                    }, 300);
                }
            });
            
            setTimeout(() => {
                const pageElement = document.getElementById(pageId + 'Page');
                if (pageElement) {
                    pageElement.style.opacity = '0';
                    pageElement.style.transform = 'translateY(30px)';
                    pageElement.classList.add('active');
                    
                    setTimeout(() => {
                        pageElement.style.opacity = '1';
                        pageElement.style.transform = 'translateY(0)';
                    }, 50);
                    
                    currentPage = pageId;
                    
                    const pageData = appData.pages[pageId];
                    if (pageData) {
                        document.getElementById('currentPageTitle').textContent = pageData.title;
                        document.getElementById('currentPageDesc').textContent = pageData.description;
                    }
                    
                    renderPage(pageId);
                    document.querySelector('.main-content').scrollTop = 0;
                    setupContentHeight();
                    
                    // Update floating button visibility
                    updateAdminUI();
                    
                    // Buat partikel baru untuk home page
                    if (pageId === 'home') {
                        createParticles();
                        setTimeout(centerHeroContent, 100); // Center konten setelah halaman home dimuat
                    }
                    
                    // Setup efek untuk halaman tertentu
                    if (pageId === 'about' || pageId === 'chatroom') {
                        setTimeout(() => {
                            showEffectToggle(
                                pageId === 'about' ? 'Rain Effect' : 'Starfall Effect',
                                pageId === 'about' ? 'fas fa-cloud-rain' : 'fas fa-star'
                            );
                        }, 500);
                    }
                }
            }, 300);
        }

        // Render page content
        function renderPage(pageId) {
            const pageData = appData.pages[pageId];
            if (!pageData) return;
            
            switch(pageId) {
                case 'home':
                    renderHomePage();
                    break;
                case 'about':
                    renderAboutPage();
                    break;
                case 'work':
                    renderWorkPage();
                    break;
                case 'achievements':
                    renderAchievementsPage();
                    break;
                case 'projects':
                    renderProjectsPage();
                    break;
                case 'dashboard':
                    renderDashboardPage();
                    break;
                case 'contact':
                    renderContactPage();
                    break;
            }
        }

        // Render home page
        function renderHomePage() {
            const pageData = appData.pages.home;
            
            document.getElementById('homeBadge').textContent = pageData.badge;
            document.getElementById('homeTitle').textContent = pageData.mainTitle;
            document.getElementById('homeSubtitle').textContent = pageData.subtitle;
            document.getElementById('homeDescription').textContent = pageData.descriptionText;
            
            pageData.stats.forEach((stat, index) => {
                const statNum = document.getElementById(`stat${index + 1}Number`);
                const statLabel = document.getElementById(`stat${index + 1}Label`);
                
                if (statNum) statNum.textContent = stat.number;
                if (statLabel) statLabel.textContent = stat.label;
            });
        }

        // Render about page
        function renderAboutPage() {
            const pageData = appData.pages.about;
            
            pageData.sections.forEach(section => {
                const element = document.getElementById(section.id);
                if (element) {
                    element.innerHTML = `<p>${section.content}</p>`;
                }
            });
            
            renderSkills();
            renderExperiences();
        }

        // Render skills
        function renderSkills() {
            const pageData = appData.pages.about;
            
            const techSkillsContainer = document.querySelector('#technicalSkills .skill-items');
            if (techSkillsContainer) {
                techSkillsContainer.innerHTML = pageData.skills.technical.map(skill => 
                    `<div class="skill-item">${skill}</div>`
                ).join('');
            }
            
            const personalSkillsContainer = document.querySelector('#personalSkills .skill-items');
            if (personalSkillsContainer) {
                personalSkillsContainer.innerHTML = pageData.skills.personal.map(skill => 
                    `<div class="skill-item">${skill}</div>`
                ).join('');
            }
        }

        // Render experiences
        function renderExperiences() {
            const pageData = appData.pages.about;
            const timeline = document.querySelector('.experience-timeline');
            
            if (!timeline) return;
            
            const existingExperiences = timeline.querySelectorAll('.experience-item');
            for (let i = 2; i < existingExperiences.length; i++) {
                existingExperiences[i].remove();
            }
            
            pageData.experiences.forEach((exp, index) => {
                let expElement = document.getElementById(exp.id);
                
                if (!expElement && index >= 2) {
                    expElement = document.createElement('div');
                    expElement.className = 'experience-item editable';
                    expElement.id = exp.id;
                    expElement.innerHTML = `
                        <div class="experience-header">
                            <h3 class="experience-title">${exp.title}</h3>
                            <div class="experience-date">${exp.date}</div>
                        </div>
                        <div class="experience-content">
                            <ul>
                                ${exp.items.map(item => `<li>${item}</li>`).join('')}
                            </ul>
                        </div>
                        <button class="edit-btn" data-edit="${exp.id}">Edit</button>
                        <button class="delete-btn" data-delete="${exp.id}" data-type="experience">Hapus</button>
                    `;
                    
                    const addButton = timeline.querySelector('[data-add="experience"]');
                    if (addButton) {
                        timeline.insertBefore(expElement, addButton);
                    } else {
                        timeline.appendChild(expElement);
                    }
                    
                    // Setup event listeners untuk edit dan delete
                    setupExperienceEventListeners(expElement, exp.id);
                } else if (expElement) {
                    expElement.querySelector('.experience-title').textContent = exp.title;
                    expElement.querySelector('.experience-date').textContent = exp.date;
                    expElement.querySelector('.experience-content ul').innerHTML = 
                        exp.items.map(item => `<li>${item}</li>`).join('');
                }
            });
        }

        // Setup event listeners untuk experience
        function setupExperienceEventListeners(element, experienceId) {
            const editBtn = element.querySelector('.edit-btn');
            const deleteBtn = element.querySelector('.delete-btn');
            
            if (editBtn) {
                editBtn.addEventListener('click', function() {
                    editExperience(experienceId);
                });
            }
            
            if (deleteBtn) {
                deleteBtn.addEventListener('click', function() {
                    deleteExperience(experienceId);
                });
            }
        }

        // Render Work page - OPTIMIZED
        function renderWorkPage() {
            const pageData = appData.pages.work;
            const container = document.getElementById('workContainer');
            
            if (!container) return;
            
            // Clear container dengan cara yang lebih efisien
            container.innerHTML = '';
            
            // Sort items by date (newest first) - lebih efisien
            const sortedItems = [...pageData.items].sort((a, b) => {
                // Convert DD/MM/YYYY to timestamp untuk sorting
                const convertToTimestamp = (dateStr) => {
                    const [day, month, year] = dateStr.split('/').map(Number);
                    return new Date(year, month - 1, day).getTime();
                };
                
                const timeA = convertToTimestamp(a.date) || 0;
                const timeB = convertToTimestamp(b.date) || 0;
                return timeB - timeA;
            });
            
            // Render items dengan batch untuk performa lebih baik
            sortedItems.forEach((item, index) => {
                const workElement = createWorkCard(item);
                container.appendChild(workElement);
                
                // Setup event listeners untuk card ini saja
                setupWorkCardEventListeners(workElement, item.id);
            });
            
            // Show/hide tombol add berdasarkan admin mode
            const addBtn = document.getElementById('addWorkBtn');
            if (addBtn) {
                addBtn.style.display = (isAdminLoggedIn || isEditMode) ? 'inline-block' : 'none';
            }
        }

        // Fungsi untuk membuat card Work
        function createWorkCard(item) {
            const workElement = document.createElement('div');
            workElement.className = 'work-card editable';
            workElement.id = item.id;
            workElement.dataset.id = item.id;
            
            let imageHTML = '';
            if (item.image && item.image.trim() !== '') {
                imageHTML = `
                    <div class="work-image-container">
                        <img src="${item.image}" alt="${item.title}" class="work-image">
                        <div class="work-upload-overlay">
                            <div>
                                <i class="fas fa-camera" style="font-size: 2rem; margin-bottom: 10px;"></i><br>
                                ${isAdminLoggedIn || isEditMode ? 'Klik untuk ganti foto' : 'Klik untuk zoom'}
                            </div>
                        </div>
                        <div class="category-badge">${item.category || 'Work'}</div>
                    </div>
                `;
            } else {
                imageHTML = `
                    <div class="work-image-container">
                        <div class="work-image-placeholder">
                            <i class="fas fa-camera"></i>
                        </div>
                        <div class="work-upload-overlay">
                            <div>
                                <i class="fas fa-camera" style="font-size: 2rem; margin-bottom: 10px;"></i><br>
                                ${isAdminLoggedIn || isEditMode ? 'Klik untuk upload foto' : 'No image available'}
                            </div>
                        </div>
                        <div class="category-badge">${item.category || 'Work'}</div>
                    </div>
                `;
            }
            
            workElement.innerHTML = `
                ${imageHTML}
                <h3>${item.title}</h3>
                <div class="date">
                    <i class="far fa-calendar"></i> ${item.date}
                </div>
                <p>${item.description}</p>
                ${isAdminLoggedIn || isEditMode ? `
                    <button class="edit-btn" data-edit="${item.id}">Edit</button>
                    <button class="delete-btn" data-delete="${item.id}" data-type="work">Hapus</button>
                ` : ''}
            `;
            
            return workElement;
        }

        // Fungsi untuk setup event listeners per card (lebih efisien)
        function setupWorkCardEventListeners(element, itemId) {
            // Edit button
            const editBtn = element.querySelector('.edit-btn');
            if (editBtn) {
                editBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    editWorkItem(itemId);
                });
            }
            
            // Delete button
            const deleteBtn = element.querySelector('.delete-btn');
            if (deleteBtn) {
                deleteBtn.addEventListener('click', function(e) {
                    e.stopPropagation();
                    deleteWorkItem(itemId);
                });
            }
            
            // Image container untuk upload/zoom
            const imageContainer = element.querySelector('.work-image-container');
            if (imageContainer) {
                imageContainer.addEventListener('click', function(e) {
                    // Jika klik pada gambar, zoom
                    if (e.target.classList.contains('work-image')) {
                        const title = element.querySelector('h3').textContent;
                        openZoom(e.target.src, title);
                        return;
                    }
                    
                    if (isAdminLoggedIn || isEditMode) {
                        editWorkImage(itemId);
                    } else {
                        // Jika bukan admin, coba zoom jika ada gambar
                        const img = this.querySelector('.work-image');
                        if (img && img.src) {
                            const title = element.querySelector('h3').textContent;
                            openZoom(img.src, title);
                        }
                    }
                });
            }
        }

        // Edit Work image
        window.editWorkImage = function(itemId) {
            if (!isAdminLoggedIn && !isEditMode) {
                showNotification('Silakan login sebagai admin untuk mengedit foto', 'error');
                return;
            }
            
            openImageUploadModal('work', itemId);
        };

        // Edit Work item
        window.editWorkItem = function(itemId) {
            if (!isAdminLoggedIn && !isEditMode) {
                showNotification('Silakan login sebagai admin untuk mengedit pekerjaan', 'error');
                return;
            }
            
            openWorkUploadModal(itemId);
        };

        // Hapus Work item - OPTIMIZED
        function deleteWorkItem(itemId) {
            if (!confirm('Apakah Anda yakin ingin menghapus pekerjaan ini?')) {
                return;
            }
            
            showLoading('Menghapus...');
            
            // Langsung hapus tanpa delay berlebihan
            const index = appData.pages.work.items.findIndex(item => item.id === itemId);
            if (index !== -1) {
                appData.pages.work.items.splice(index, 1);
                renderWorkPage();
                saveToLocalStorage();
                hideLoading();
                showNotification('Pekerjaan berhasil dihapus!', 'success');
            } else {
                hideLoading();
            }
        }

        // Render achievements page
        function renderAchievementsPage() {
            const pageData = appData.pages.achievements;
            const container = document.getElementById('achievementsContainer');
            
            if (!container) return;
            
            container.innerHTML = '';
            
            pageData.items.forEach((item) => {
                const achievementElement = document.createElement('div');
                achievementElement.className = 'achievement-card editable';
                achievementElement.id = item.id;
                
                let imageHTML = '';
                if (item.image) {
                    imageHTML = `
                        <div class="achievement-image-container" data-upload="${item.id}">
                            <img src="${item.image}" alt="${item.title}" class="achievement-image" 
                                 onclick="openZoom('${item.image}', '${item.title}')">
                            <div class="achievement-upload-overlay">
                                <div>
                                    <i class="fas fa-camera" style="font-size: 2rem; margin-bottom: 10px;"></i><br>
                                    ${isAdminLoggedIn || isEditMode ? 'Klik untuk ganti foto' : 'Klik untuk zoom'}
                                </div>
                            </div>
                        </div>
                    `;
                } else {
                    imageHTML = `
                        <div class="achievement-image-container" data-upload="${item.id}">
                            <div class="achievement-image-placeholder">
                                <i class="fas fa-trophy"></i>
                            </div>
                            <div class="achievement-upload-overlay">
                                <div>
                                    <i class="fas fa-camera" style="font-size: 2rem; margin-bottom: 10px;"></i><br>
                                    ${isAdminLoggedIn || isEditMode ? 'Klik untuk upload foto' : 'No image available'}
                                </div>
                            </div>
                        </div>
                    `;
                }
                
                achievementElement.innerHTML = `
                    ${imageHTML}
                    <h3>${item.title}</h3>
                    <div class="date">${item.date}</div>
                    <p>${item.description}</p>
                    <button class="edit-btn" data-edit="${item.id}">Edit</button>
                    <button class="delete-btn" data-delete="${item.id}" data-type="achievement">Hapus</button>
                `;
                
                container.appendChild(achievementElement);
            });
            
            // Setup event listeners untuk upload foto achievements
            document.querySelectorAll('.achievement-image-container').forEach(container => {
                container.addEventListener('click', function(e) {
                    // Jika klik langsung pada gambar, biarkan fungsi zoom yang menangani
                    if (e.target.classList.contains('achievement-image')) {
                        return;
                    }
                    
                    if (isAdminLoggedIn || isEditMode) {
                        const achievementId = this.getAttribute('data-upload');
                        openImageUploadModal('achievement', achievementId);
                    } else {
                        // Jika bukan admin, coba zoom jika ada gambar
                        const img = this.querySelector('.achievement-image');
                        if (img && img.src) {
                            const title = this.closest('.achievement-card').querySelector('h3').textContent;
                            openZoom(img.src, title);
                        }
                    }
                });
            });
            
            // Setup event listener untuk tombol delete
            document.querySelectorAll('.delete-btn[data-type="achievement"]').forEach(btn => {
                btn.addEventListener('click', function() {
                    const elementId = this.getAttribute('data-delete');
                    deleteAchievement(elementId);
                });
            });
        }

        // Edit achievement
        function editAchievement(achievementId) {
            const achievement = appData.pages.achievements.items.find(item => item.id === achievementId);
            if (!achievement) return;
            
            const newTitle = prompt('Edit judul pencapaian:', achievement.title);
            if (newTitle === null) return;
            
            const newDate = prompt('Edit tanggal:', achievement.date);
            if (newDate === null) return;
            
            const newDescription = prompt('Edit deskripsi:', achievement.description);
            if (newDescription === null) return;
            
            achievement.title = newTitle;
            achievement.date = newDate;
            achievement.description = newDescription;
            
            renderAchievementsPage();
            showNotification('Pencapaian berhasil diperbarui!', 'success');
        }

        // Fungsi untuk menghapus achievement
        function deleteAchievement(achievementId) {
            if (!confirm('Apakah Anda yakin ingin menghapus pencapaian ini?')) {
                return;
            }
            
            showLoading('Menghapus pencapaian...');
            
            // Simulasi delay untuk efek loading
            setTimeout(() => {
                const index = appData.pages.achievements.items.findIndex(item => item.id === achievementId);
                if (index !== -1) {
                    appData.pages.achievements.items.splice(index, 1);
                    renderAchievementsPage();
                    saveToLocalStorage();
                    showNotification('Pencapaian berhasil dihapus!', 'success');
                }
                hideLoading();
            }, 500);
        }

        // Add achievement
        function addAchievement() {
            const newTitle = prompt('Masukkan judul pencapaian baru:');
            if (!newTitle) return;
            
            const newDate = prompt('Masukkan tanggal:');
            if (!newDate) return;
            
            const newDescription = prompt('Masukkan deskripsi:');
            if (!newDescription) return;
            
            const newId = 'achievement' + (appData.pages.achievements.items.length + 1);
            const newAchievement = {
                id: newId,
                title: newTitle,
                date: newDate,
                description: newDescription,
                image: null
            };
            
            appData.pages.achievements.items.push(newAchievement);
            renderAchievementsPage();
            saveToLocalStorage();
            showNotification('Pencapaian berhasil ditambahkan!', 'success');
        }

        // Render projects page
        function renderProjectsPage() {
            const pageData = appData.pages.projects;
            const container = document.getElementById('projectsContainer');
            
            if (!container) return;
            
            container.innerHTML = '';
            
            pageData.items.forEach((item) => {
                const projectElement = document.createElement('div');
                projectElement.className = 'project-card editable';
                projectElement.id = item.id;
                
                let statsHTML = '';
                if (item.stats) {
                    statsHTML = `
                        <div class="project-stats">
                            ${item.stats.map(stat => `
                                <div class="stat">
                                    <span class="stat-value ${stat.type || ''}">${stat.value}</span>
                                    <span class="stat-label">${stat.label}</span>
                                </div>
                            `).join('')}
                        </div>
                    `;
                }
                
                projectElement.innerHTML = `
                    <h3><i class="fas fa-project-diagram"></i> ${item.title}</h3>
                    <p>${item.description}</p>
                    ${statsHTML}
                    <button class="edit-btn" data-edit="${item.id}">Edit</button>
                    <button class="delete-btn" data-delete="${item.id}" data-type="project">Hapus</button>
                `;
                
                container.appendChild(projectElement);
            });
            
            // Setup event listener untuk tombol delete
            document.querySelectorAll('.delete-btn[data-type="project"]').forEach(btn => {
                btn.addEventListener('click', function() {
                    const elementId = this.getAttribute('data-delete');
                    deleteProject(elementId);
                });
            });
        }

        // Edit project
        function editProject(projectId) {
            const project = appData.pages.projects.items.find(item => item.id === projectId);
            if (!project) return;
            
            const newTitle = prompt('Edit judul proyek:', project.title);
            if (newTitle === null) return;
            
            const newDescription = prompt('Edit deskripsi:', project.description);
            if (newDescription === null) return;
            
            project.title = newTitle;
            project.description = newDescription;
            
            renderProjectsPage();
            showNotification('Proyek berhasil diperbarui!', 'success');
        }

        // Fungsi untuk menghapus project
        function deleteProject(projectId) {
            if (!confirm('Apakah Anda yakin ingin menghapus proyek ini?')) {
                return;
            }
            
            showLoading('Menghapus proyek...');
            
            setTimeout(() => {
                const index = appData.pages.projects.items.findIndex(item => item.id === projectId);
                if (index !== -1) {
                    appData.pages.projects.items.splice(index, 1);
                    renderProjectsPage();
                    saveToLocalStorage();
                    showNotification('Proyek berhasil dihapus!', 'success');
                }
                hideLoading();
            }, 500);
        }

        // Add project
        function addProject() {
            const newTitle = prompt('Masukkan judul proyek baru:');
            if (!newTitle) return;
            
            const newDescription = prompt('Masukkan deskripsi:');
            if (!newDescription) return;
            
            const newId = 'project' + (appData.pages.projects.items.length + 1);
            
            // Tanya statistik baru
            const stat1Value = prompt('Masukkan nilai statistik 1 (misal: 2 Ton):', '0%');
            const stat1Label = prompt('Masukkan label statistik 1:', 'Sebelum');
            
            const stat2Value = prompt('Masukkan nilai statistik 2 (misal: ↓ 0%):', '↓ 0%');
            const stat2Label = prompt('Masukkan label statistik 2:', 'Perubahan');
            
            const stat3Value = prompt('Masukkan nilai statistik 3 (misal: 0%):', '0%');
            const stat3Label = prompt('Masukkan label statistik 3:', 'Sesudah');
            
            const newProject = {
                id: newId,
                title: newTitle,
                description: newDescription,
                stats: [
                    { value: stat1Value, label: stat1Label },
                    { value: stat2Value, label: stat2Label, type: "improvement" },
                    { value: stat3Value, label: stat3Label }
                ]
            };
            
            appData.pages.projects.items.push(newProject);
            renderProjectsPage();
            saveToLocalStorage();
            showNotification('Proyek berhasil ditambahkan!', 'success');
        }

        // Render dashboard page
        function renderDashboardPage() {
            const pageData = appData.pages.dashboard;
            
            // Render periods
            pageData.periods.forEach(period => {
                const periodElement = document.getElementById(period.id);
                if (periodElement) {
                    periodElement.querySelector('.period-title').textContent = period.title;
                    periodElement.querySelector('.period-date').innerHTML = `<i class="far fa-calendar"></i> ${period.date}`;
                    
                    // Render stats
                    period.stats.forEach(stat => {
                        const statElement = document.getElementById(stat.id);
                        if (statElement) {
                            const valueElement = statElement.querySelector('.period-stat-value');
                            const labelElement = statElement.querySelector('.period-stat-label');
                            
                            if (valueElement) valueElement.textContent = stat.value;
                            if (labelElement) labelElement.textContent = stat.label;
                            
                            // Add appropriate class based on period
                            if (period.id === 'staffPeriod') {
                                valueElement.classList.add('staff');
                                valueElement.classList.remove('drafter');
                            } else if (period.id === 'drafterPeriod') {
                                valueElement.classList.add('drafter');
                                valueElement.classList.remove('staff');
                            }
                        }
                    });
                }
            });
        }

        // Fungsi untuk menghapus experience
        function deleteExperience(experienceId) {
            if (!confirm('Apakah Anda yakin ingin menghapus pengalaman ini?')) {
                return;
            }
            
            showLoading('Menghapus pengalaman...');
            
            setTimeout(() => {
                const index = appData.pages.about.experiences.findIndex(exp => exp.id === experienceId);
                if (index !== -1) {
                    appData.pages.about.experiences.splice(index, 1);
                    renderExperiences();
                    saveToLocalStorage();
                    showNotification('Pengalaman berhasil dihapus!', 'success');
                }
                hideLoading();
            }, 500);
        }

        // Edit experience
        function editExperience(experienceId) {
            const experience = appData.pages.about.experiences.find(exp => exp.id === experienceId);
            if (!experience) return;
            
            const newTitle = prompt('Edit judul pengalaman:', experience.title);
            if (newTitle === null) return;
            
            const newDate = prompt('Edit periode:', experience.date);
            if (newDate === null) return;
            
            const currentItems = experience.items.join('\n');
            const newItemsText = prompt('Edit poin-poin (satu per baris):', currentItems);
            if (newItemsText === null) return;
            
            experience.title = newTitle;
            experience.date = newDate;
            experience.items = newItemsText.split('\n').filter(item => item.trim() !== '');
            
            renderExperiences();
            showNotification('Pengalaman berhasil diperbarui!', 'success');
        }

        // Add experience
        function addExperience() {
            const newTitle = prompt('Masukkan judul pengalaman baru:');
            if (!newTitle) return;
            
            const newDate = prompt('Masukkan periode:');
            if (!newDate) return;
            
            const itemsText = prompt('Masukkan poin-poin (satu per baris):');
            if (!itemsText) return;
            
            const newId = 'experience' + (appData.pages.about.experiences.length + 1);
            const newExperience = {
                id: newId,
                title: newTitle,
                date: newDate,
                items: itemsText.split('\n').filter(item => item.trim() !== '')
            };
            
            appData.pages.about.experiences.push(newExperience);
            renderExperiences();
            showNotification('Pengalaman berhasil ditambahkan!', 'success');
        }

        // Render contact page
        function renderContactPage() {
            const pageData = appData.pages.contact;
            
            pageData.items.forEach(item => {
                const element = document.getElementById(item.id);
                if (element) {
                    element.querySelector('p').textContent = item.value;
                }
            });
        }

        // Setup admin panel
        function setupAdminPanel() {
            const adminToggle = document.getElementById('adminToggle');
            const adminPanel = document.getElementById('adminPanel');
            const adminLogin = document.getElementById('adminLogin');
            const adminLogout = document.getElementById('adminLogout');
            const toggleEditMode = document.getElementById('toggleEditMode');
            const saveAllData = document.getElementById('saveAllData');
            
            adminToggle.addEventListener('click', function(e) {
                e.stopPropagation();
                adminPanel.classList.toggle('active');
            });
            
            document.addEventListener('click', function(e) {
                if (!e.target.closest('.admin-panel') && !e.target.closest('.admin-toggle')) {
                    adminPanel.classList.remove('active');
                }
            });
            
            adminLogin.addEventListener('click', function() {
                const password = document.getElementById('adminPassword').value;
                
                if (password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    document.getElementById('adminControls').style.display = 'block';
                    document.getElementById('adminPassword').value = '';
                    showNotification('Login admin berhasil!', 'success');
                    updateAdminUI();
                    adminPanel.classList.remove('active');
                    
                    if (window.innerWidth <= 768) {
                        document.getElementById('sidebar').classList.remove('active');
                        document.getElementById('mobileMenuToggle').innerHTML = '<i class="fas fa-bars"></i>';
                    }
                } else {
                    showNotification('Password salah!', 'error');
                }
            });
            
            adminLogout.addEventListener('click', function() {
                isAdminLoggedIn = false;
                isEditMode = false;
                document.getElementById('adminControls').style.display = 'none';
                document.body.classList.remove('admin-mode');
                document.getElementById('editStatus').style.display = 'none';
                showNotification('Logout berhasil', 'info');
                updateAdminUI();
            });
            
            toggleEditMode.addEventListener('click', function() {
                if (!isAdminLoggedIn) {
                    showNotification('Silakan login sebagai admin terlebih dahulu', 'error');
                    return;
                }
                
                isEditMode = !isEditMode;
                document.body.classList.toggle('admin-mode', isEditMode);
                document.getElementById('editStatus').style.display = isEditMode ? 'block' : 'none';
                toggleEditMode.textContent = isEditMode ? 'Nonaktifkan Edit Mode' : 'Aktifkan Edit Mode';
                
                if (isEditMode) {
                    setupEditMode();
                } else {
                    // Re-render halaman untuk menghilangkan mode edit
                    renderPage(currentPage);
                }
            });
            
            saveAllData.addEventListener('click', function() {
                if (!isAdminLoggedIn) {
                    showNotification('Silakan login sebagai admin terlebih dahulu', 'error');
                    return;
                }
                
                showLoading('Menyimpan data...');
                
                setTimeout(() => {
                    saveToLocalStorage();
                    hideLoading();
                }, 500);
            });
        }

        // Setup edit mode
        function setupEditMode() {
            document.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const elementId = this.getAttribute('data-edit');
                    const element = document.getElementById(elementId);
                    
                    if (element) {
                        if (element.classList.contains('skill-category')) {
                            editSkills(elementId);
                        } else if (element.classList.contains('experience-item')) {
                            editExperience(elementId);
                        } else if (element.classList.contains('achievement-card')) {
                            editAchievement(elementId);
                        } else if (element.classList.contains('project-card')) {
                            editProject(elementId);
                        } else if (element.classList.contains('dashboard-card') || 
                                   element.classList.contains('stat-card') || 
                                   element.id.startsWith('dashboardStat') || 
                                   element.id.startsWith('stat') ||
                                   element.id.startsWith('staffStat') ||
                                   element.id.startsWith('drafterStat')) {
                            editStat(elementId);
                        } else if (element.classList.contains('contact-card')) {
                            editContact(elementId);
                        } else if (element.classList.contains('period-section')) {
                            editPeriod(elementId);
                        } else if (element.classList.contains('work-card')) {
                            editWorkItem(elementId);
                        } else {
                            editText(elementId);
                        }
                    }
                });
            });
            
            document.querySelectorAll('.add-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const type = this.getAttribute('data-add');
                    
                    switch(type) {
                        case 'technicalSkills':
                        case 'personalSkills':
                            addSkill(type);
                            break;
                        case 'experience':
                            addExperience();
                            break;
                        case 'achievement':
                            addAchievement();
                            break;
                        case 'project':
                            addProject();
                            break;
                        case 'work':
                            openWorkUploadModal();
                            break;
                    }
                });
            });
        }

        // Edit text element
        function editText(elementId) {
            const element = document.getElementById(elementId);
            if (!element) return;
            
            const currentText = element.textContent;
            const newText = prompt('Edit teks:', currentText);
            
            if (newText !== null && newText !== currentText) {
                element.textContent = newText;
                
                if (elementId.startsWith('stat')) {
                    const statIndex = parseInt(elementId.replace('stat', '').replace('Number', '').replace('Label', '')) - 1;
                    if (elementId.includes('Number')) {
                        appData.pages.home.stats[statIndex].number = newText;
                    } else {
                        appData.pages.home.stats[statIndex].label = newText;
                    }
                } else if (elementId === 'homeBadge') {
                    appData.pages.home.badge = newText;
                } else if (elementId === 'homeTitle') {
                    appData.pages.home.mainTitle = newText;
                } else if (elementId === 'homeSubtitle') {
                    appData.pages.home.subtitle = newText;
                } else if (elementId === 'homeDescription') {
                    appData.pages.home.descriptionText = newText;
                } else if (elementId === 'aboutText1') {
                    appData.pages.about.sections[0].content = newText;
                } else if (elementId === 'aboutText2') {
                    appData.pages.about.sections[1].content = newText;
                }
                
                showNotification('Teks berhasil diperbarui!', 'success');
            }
        }

        // Edit period (dashboard)
        function editPeriod(periodId) {
            const period = appData.pages.dashboard.periods.find(p => p.id === periodId);
            if (!period) return;
            
            const newTitle = prompt('Edit judul periode:', period.title);
            if (newTitle === null) return;
            
            const newDate = prompt('Edit rentang tanggal:', period.date);
            if (newDate === null) return;
            
            period.title = newTitle;
            period.date = newDate;
            
            renderDashboardPage();
            showNotification('Periode berhasil diperbarui!', 'success');
        }

        // Edit skills
        function editSkills(elementId) {
            const element = document.getElementById(elementId);
            if (!element) return;
            
            const isTechnical = elementId === 'technicalSkills';
            const currentSkills = isTechnical ? 
                appData.pages.about.skills.technical : 
                appData.pages.about.skills.personal;
            
            const skillsText = currentSkills.join('\n');
            const newSkillsText = prompt('Edit skill (satu per baris):', skillsText);
            
            if (newSkillsText !== null && newSkillsText !== skillsText) {
                const newSkills = newSkillsText.split('\n').filter(skill => skill.trim() !== '');
                
                if (isTechnical) {
                    appData.pages.about.skills.technical = newSkills;
                } else {
                    appData.pages.about.skills.personal = newSkills;
                }
                
                renderSkills();
                showNotification('Skill berhasil diperbarui!', 'success');
            }
        }

        // Add skill
        function addSkill(type) {
            const isTechnical = type === 'technicalSkills';
            const newSkill = prompt('Masukkan skill baru:');
            
            if (newSkill && newSkill.trim() !== '') {
                if (isTechnical) {
                    appData.pages.about.skills.technical.push(newSkill.trim());
                } else {
                    appData.pages.about.skills.personal.push(newSkill.trim());
                }
                
                renderSkills();
                showNotification('Skill berhasil ditambahkan!', 'success');
            }
        }

        // Edit stat
        function editStat(statId) {
            const element = document.getElementById(statId);
            if (!element) return;
            
            let numberElement, labelElement;
            
            if (element.classList.contains('dashboard-card') || 
                element.classList.contains('stat-card') ||
                element.classList.contains('period-stat')) {
                
                if (element.classList.contains('period-stat')) {
                    numberElement = element.querySelector('.period-stat-value');
                    labelElement = element.querySelector('.period-stat-label');
                } else if (element.classList.contains('dashboard-card')) {
                    numberElement = element.querySelector('.dashboard-number');
                    labelElement = element.querySelector('.dashboard-label');
                } else if (element.classList.contains('stat-card')) {
                    numberElement = element.querySelector('.stat-number');
                    labelElement = element.querySelector('.stat-label');
                }
            }
            
            if (!numberElement || !labelElement) return;
            
            const currentNumber = numberElement.textContent;
            const currentLabel = labelElement.textContent;
            
            const newNumber = prompt('Edit angka:', currentNumber);
            if (newNumber === null) return;
            
            const newLabel = prompt('Edit label:', currentLabel);
            if (newLabel === null) return;
            
            numberElement.textContent = newNumber;
            labelElement.textContent = newLabel;
            
            // Update data based on element type
            if (statId.startsWith('dashboardStat')) {
                const stat = appData.pages.dashboard.stats.find(s => s.id === statId);
                if (stat) {
                    stat.number = newNumber;
                    stat.label = newLabel;
                }
            } else if (statId.startsWith('stat')) {
                const statIndex = parseInt(statId.replace('stat', '').replace('Number', '').replace('Label', '')) - 1;
                if (statId.includes('Number')) {
                    appData.pages.home.stats[statIndex].number = newNumber;
                } else {
                    appData.pages.home.stats[statIndex].label = newLabel;
                }
            } else if (statId.startsWith('staffStat') || statId.startsWith('drafterStat')) {
                // Find the period that contains this stat
                const period = appData.pages.dashboard.periods.find(p => 
                    p.stats.some(s => s.id === statId)
                );
                if (period) {
                    const stat = period.stats.find(s => s.id === statId);
                    if (stat) {
                        stat.value = newNumber;
                        stat.label = newLabel;
                    }
                }
            }
            
            showNotification('Statistik berhasil diperbarui!', 'success');
        }

        // Edit contact
        function editContact(contactId) {
            const contact = appData.pages.contact.items.find(item => item.id === contactId);
            if (!contact) return;
            
            const currentValue = contact.value;
            const newValue = prompt(`Edit ${contact.label}:`, currentValue);
            
            if (newValue !== null && newValue !== currentValue) {
                contact.value = newValue;
                
                const contactElement = document.getElementById(contactId);
                if (contactElement) {
                    contactElement.querySelector('p').textContent = newValue;
                }
                
                showNotification('Kontak berhasil diperbarui!', 'success');
            }
        }

        // Setup chat
        function setupChat() {
            const sendButton = document.getElementById('sendMessage');
            const chatInput = document.getElementById('chatInput');
            
            if (sendButton && chatInput) {
                sendButton.addEventListener('click', sendMessage);
                chatInput.addEventListener('keypress', function(e) {
                    if (e.key === 'Enter') {
                        sendMessage();
                    }
                });
            }
        }

        // Send message
        function sendMessage() {
            const chatInput = document.getElementById('chatInput');
            const message = chatInput.value.trim();
            
            if (message) {
                const chatMessages = document.getElementById('chatMessages');
                const now = new Date();
                const timeString = `${now.getDate()}/${now.getMonth()+1}/${now.getFullYear()}, ${now.getHours()}:${now.getMinutes().toString().padStart(2, '0')}`;
                
                const messageDiv = document.createElement('div');
                messageDiv.className = 'message user';
                messageDiv.innerHTML = `
                    <div class="message-info">
                        <span class="message-user">You</span>
                        <span class="message-time">${timeString}</span>
                    </div>
                    <div class="message-content">${message}</div>
                `;
                
                chatMessages.appendChild(messageDiv);
                chatInput.value = '';
                
                chatMessages.scrollTop = chatMessages.scrollHeight;
                
                setTimeout(() => {
                    const replies = [
                        "Thanks for your message!",
                        "That's interesting, tell me more!",
                        "I appreciate your feedback!",
                        "Great point! Let's discuss this further."
                    ];
                    
                    const randomReply = replies[Math.floor(Math.random() * replies.length)];
                    
                    const replyDiv = document.createElement('div');
                    replyDiv.className = 'message';
                    replyDiv.innerHTML = `
                        <div class="message-info">
                            <span class="message-user">Arya Savariansah</span>
                            <span class="message-time">${timeString}</span>
                        </div>
                        <div class="message-content">${randomReply}</div>
                    `;
                    
                    chatMessages.appendChild(replyDiv);
                    chatMessages.scrollTop = chatMessages.scrollHeight;
                }, 1000);
            }
        }

        // Setup contact form
        function setupContactForm() {
            const contactForm = document.getElementById('contactForm');
            
            if (contactForm) {
                contactForm.addEventListener('submit', function(e) {
                    e.preventDefault();
                    
                    const name = document.getElementById('name').value;
                    const email = document.getElementById('email').value;
                    const message = document.getElementById('message').value;
                    
                    showLoading('Mengirim pesan...');
                    
                    setTimeout(() => {
                        alert(`Thank you ${name}! Your message has been sent successfully. I'll get back to you at ${email} soon.`);
                        contactForm.reset();
                        hideLoading();
                    }, 1000);
                });
            }
        }

        // Update admin UI
        function updateAdminUI() {
            const adminToggle = document.getElementById('adminToggle');
            const floatingAddBtn = document.getElementById('floatingAddBtn');
            
            if (isAdminLoggedIn) {
                adminToggle.innerHTML = '<i class="fas fa-user-check"></i> Admin Mode';
                adminToggle.style.background = 'var(--gradient-gold)';
                adminToggle.style.color = '#000';
                document.body.classList.add('admin-mode');
                
                // Tampilkan floating button hanya di halaman Work
                if (currentPage === 'work') {
                    floatingAddBtn.style.display = 'flex';
                } else {
                    floatingAddBtn.style.display = 'none';
                }
            } else {
                adminToggle.innerHTML = '<i class="fas fa-user-lock"></i> Login Admin';
                adminToggle.style.background = 'linear-gradient(135deg, #1e1e1e 0%, #2a2a2a 100%)';
                adminToggle.style.color = 'var(--primary)';
                document.body.classList.remove('admin-mode');
                floatingAddBtn.style.display = 'none';
            }
            
            // Update edit status
            document.getElementById('editStatus').style.display = isEditMode ? 'block' : 'none';
        }

        // Fungsi untuk menampilkan loading
        function showLoading(text = 'Loading...') {
            const loadingOverlay = document.getElementById('loadingOverlay');
            const loadingText = document.getElementById('loadingText');
            
            loadingText.textContent = text;
            loadingOverlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        // Fungsi untuk menyembunyikan loading
        function hideLoading() {
            const loadingOverlay = document.getElementById('loadingOverlay');
            loadingOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
            
            // Reset progress bar
            hideProgress();
        }

        // Fungsi untuk menampilkan progress bar
        function showProgress() {
            document.getElementById('uploadProgress').style.display = 'block';
            document.getElementById('uploadPercentageOld').style.display = 'block';
        }

        // Fungsi untuk menyembunyikan progress bar
        function hideProgress() {
            document.getElementById('uploadProgress').style.display = 'none';
            document.getElementById('uploadPercentageOld').style.display = 'none';
            document.getElementById('progressBar').style.width = '0%';
            document.getElementById('uploadPercentageOld').textContent = '0%';
        }

        // Fungsi untuk update progress bar
        function updateProgress(percentage) {
            document.getElementById('progressBar').style.width = percentage + '%';
            document.getElementById('uploadPercentageOld').textContent = Math.round(percentage) + '%';
        }

        // Show notification
        function showNotification(message, type = 'info') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            
            if (type === 'success') {
                notification.style.background = 'var(--gradient-gold)';
                notification.style.color = '#000';
            } else if (type === 'error') {
                notification.style.background = 'linear-gradient(135deg, #ff4757 0%, #ff6b81 100%)';
                notification.style.color = '#fff';
            } else if (type === 'warning') {
                notification.style.background = 'linear-gradient(135deg, #ffa502 0%, #ffb142 100%)';
                notification.style.color = '#000';
            } else {
                notification.style.background = 'var(--gradient-gold)';
                notification.style.color = '#000';
            }
            
            notification.style.display = 'block';
            
            setTimeout(() => {
                notification.style.display = 'none';
            }, 3000);
        }
    </script>
</body>
</html>
