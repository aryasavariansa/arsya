<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arya Savariansah - Portfolio Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Montserrat:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        /* ============================================
           RESET & VARIABLES CSS - PERBAIKAN BROWSER COMPATIBILITY
        ============================================ */
        :root {
            /* Primary Colors - Gold Theme */
            --primary: #ffd700;
            --primary-dark: #ffcc00;
            --primary-light: #fff8e1;
            --secondary: #00ffff;
            --secondary-dark: #00bcd4;
            
            /* Status Colors */
            --danger: #ff4757;
            --danger-light: #ff6b81;
            --success: #2ed573;
            --success-light: #7bed9f;
            --warning: #ffa502;
            --warning-light: #ffb142;
            
            /* Dark Theme Colors */
            --dark: #0a0a0a;
            --dark-light: #1a1a1a;
            --dark-lighter: #2a2a2a;
            --dark-lightest: #3a3a3a;
            
            /* Light Colors */
            --light: #ffffff;
            --light-gray: #f5f5f5;
            --gray: #8a8a8a;
            --gray-light: #b0b0b0;
            --gray-dark: #5a5a5a;
            
            /* Layout Variables */
            --sidebar-width: 280px;
            --border-radius: 16px;
            --border-radius-sm: 12px;
            --border-radius-lg: 20px;
            --box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
            --box-shadow-lg: 0 20px 60px rgba(0, 0, 0, 0.4);
            --box-shadow-sm: 0 5px 20px rgba(0, 0, 0, 0.2);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --transition-fast: all 0.2s ease;
            --transition-slow: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            
            /* Gradients */
            --gradient-gold: linear-gradient(135deg, #ffd700 0%, #ffed4e 100%);
            --gradient-gold-dark: linear-gradient(135deg, #ffcc00 0%, #ffdb4d 100%);
            --gradient-cyan: linear-gradient(135deg, #00ffff 0%, #00bcd4 100%);
            --gradient-dark: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            --gradient-dark-light: linear-gradient(135deg, #2a2a2a 0%, #3a3a3a 100%);
            --gradient-success: linear-gradient(135deg, #2ed573 0%, #7bed9f 100%);
            --gradient-purple: linear-gradient(135deg, #a855f7 0%, #c084fc 100%);
            --gradient-danger: linear-gradient(135deg, #ff4757 0%, #ff6b81 100%);
            
            /* Font Variables */
            --font-primary: 'Poppins', 'Segoe UI', system-ui, -apple-system, sans-serif;
            --font-secondary: 'Montserrat', 'Segoe UI', system-ui, -apple-system, sans-serif;
            
            /* Z-index Layers */
            --z-sidebar: 100;
            --z-main: 1;
            --z-modal: 2000;
            --z-notification: 2001;
            --z-loader: 2002;
            --z-floating: 999;
        }

        /* ============================================
           RESET STYLES - FIX BROWSER INCONSISTENCIES
        ============================================ */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-box-sizing: border-box;
            -moz-box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            -webkit-text-size-adjust: 100%;
            -moz-text-size-adjust: 100%;
            -ms-text-size-adjust: 100%;
        }

        body {
            font-family: var(--font-primary);
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            line-height: 1.6;
        }

        /* Fix for mobile tap highlight */
        a, button, input, textarea {
            -webkit-tap-highlight-color: transparent;
            tap-highlight-color: transparent;
        }

        /* Remove default button styles */
        button {
            background: none;
            border: none;
            font: inherit;
            cursor: pointer;
            outline: none;
        }

        /* Images */
        img {
            max-width: 100%;
            height: auto;
            display: block;
        }

        /* Lists */
        ul, ol {
            list-style: none;
        }

        /* Links */
        a {
            text-decoration: none;
            color: inherit;
        }

        /* Inputs */
        input, textarea, select {
            font-family: inherit;
            font-size: inherit;
            color: inherit;
        }

        /* ============================================
           LAYOUT STYLES - FIXED SIDEBAR + SCROLLABLE MAIN
        ============================================ */
        .app-container {
            display: flex;
            min-height: 100vh;
            position: relative;
        }

        /* ===== SIDEBAR - TETAP DI KIRI ===== */
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
            z-index: var(--z-sidebar);
            overflow-y: auto;
            transition: var(--transition);
            border-right: 1px solid rgba(255, 215, 0, 0.1);
            -webkit-overflow-scrolling: touch;
        }

        /* Scrollbar styling untuk sidebar */
        .sidebar::-webkit-scrollbar {
            width: 6px;
        }

        .sidebar::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }

        .sidebar::-webkit-scrollbar-thumb {
            background: rgba(255, 215, 0, 0.3);
            border-radius: 10px;
        }

        .sidebar::-webkit-scrollbar-thumb:hover {
            background: rgba(255, 215, 0, 0.5);
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
            flex-shrink: 0;
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
        }

        .profile-img-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: var(--gradient-gold);
            border-radius: 50%;
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
            font-family: var(--font-secondary);
        }

        .profile-info p {
            font-size: 0.9rem;
            color: var(--primary);
            font-weight: 500;
        }

        /* Navigation Menu */
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
            border-left: 3px solid transparent;
        }

        .nav-menu a:hover {
            color: var(--light);
            background: linear-gradient(90deg, rgba(255, 215, 0, 0.1), transparent);
            border-left-color: var(--primary);
            transform: translateX(5px);
        }

        .nav-menu a.active {
            color: var(--primary);
            background: linear-gradient(90deg, rgba(255, 215, 0, 0.1), transparent);
            border-left-color: var(--primary);
        }

        .nav-menu a i {
            width: 24px;
            margin-right: 15px;
            font-size: 1.2rem;
            text-align: center;
        }

        /* Admin Section */
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
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.2);
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
            position: relative;
            overflow: hidden;
        }

        .admin-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }

        .admin-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: var(--transition-slow);
        }

        .admin-btn:hover::after {
            left: 100%;
        }

        .sidebar-footer {
            padding: 25px 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: var(--gray);
            font-size: 0.85rem;
            text-align: center;
            flex-shrink: 0;
        }

        /* ===== MAIN CONTENT AREA - SCROLLABLE ===== */
        .main-content {
            flex: 1;
            margin-left: var(--sidebar-width);
            min-height: 100vh;
            overflow-y: auto;
            background: linear-gradient(135deg, rgba(10, 10, 10, 0.95) 0%, rgba(26, 26, 26, 0.98) 100%);
            position: relative;
            z-index: var(--z-main);
        }

        /* Modern Scrollbar Styling */
        .main-content::-webkit-scrollbar {
            width: 12px;
        }

        .main-content::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            margin: 5px;
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

        /* Firefox scrollbar */
        .main-content {
            scrollbar-width: thin;
            scrollbar-color: var(--primary) rgba(255, 255, 255, 0.1);
        }

        /* Content Header */
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
            -webkit-backdrop-filter: blur(10px);
            box-shadow: 0 5px 30px rgba(0, 0, 0, 0.5);
        }

        .page-title h2 {
            font-size: 2.2rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            font-weight: 800;
            font-family: var(--font-secondary);
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
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% {
                box-shadow: 0 0 0 0 rgba(255, 215, 0, 0.4);
            }
            50% {
                box-shadow: 0 0 0 10px rgba(255, 215, 0, 0);
            }
        }

        /* ===== FLOATING BUTTONS ===== */
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
            z-index: var(--z-floating);
            display: none;
            align-items: center;
            gap: 10px;
            font-size: 0.95rem;
            border: 2px solid rgba(255, 255, 255, 0.1);
        }

        .floating-add-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.4);
        }

        .floating-add-btn i {
            font-size: 1.1rem;
        }

        .admin-mode .floating-add-btn {
            display: flex;
        }

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
            z-index: var(--z-floating);
            display: none;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
            border: 2px solid rgba(255, 255, 255, 0.1);
        }

        .effect-toggle:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 12px 35px rgba(255, 215, 0, 0.4);
        }

        .effect-toggle i {
            font-size: 1.1rem;
        }

        /* ===== CONTENT BODY ===== */
        .content-body {
            padding: 50px;
            min-height: calc(100vh - 140px);
        }

        .page {
            display: none;
            animation: fadeInUp 0.6s ease;
            padding-bottom: 100px;
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

        /* ===== HOME PAGE - IMPROVED DESIGN ===== */
        .home-hero {
            position: relative;
            padding: 80px 40px;
            background: linear-gradient(135deg, 
                rgba(10, 10, 10, 0.95) 0%, 
                rgba(26, 26, 26, 0.9) 50%,
                rgba(40, 40, 40, 0.8) 100%);
            border-radius: var(--border-radius-lg);
            margin-bottom: 60px;
            overflow: hidden;
            min-height: 500px;
            display: flex;
            align-items: center;
            justify-content: center;
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
            background-clip: text;
            margin-bottom: 15px;
            font-weight: 800;
            line-height: 1.1;
            text-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            position: relative;
            display: inline-block;
            font-family: var(--font-secondary);
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
        }

        .hero-description {
            font-size: 1.2rem;
            color: #ddd;
            max-width: 800px;
            margin: 0 auto 30px;
            line-height: 1.8;
            animation: fadeInUp 0.8s ease 0.5s both;
        }

        .hero-actions {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
            animation: fadeInUp 0.8s ease 0.7s both;
        }

        .hero-btn {
            padding: 15px 35px;
            font-size: 1rem;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 50px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 10px 25px rgba(255, 215, 0, 0.3);
        }

        .hero-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(255, 215, 0, 0.4);
        }

        .hero-btn.secondary {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            color: var(--primary);
            border: 2px solid rgba(255, 215, 0, 0.3);
        }

        .hero-btn.secondary:hover {
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.1) 0%, rgba(255, 215, 0, 0.05) 100%);
        }

        /* Stats Grid */
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

        .stat-number {
            font-size: 3.5rem;
            font-weight: 900;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
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

        /* Quick Links */
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
            background-clip: text;
            font-weight: 700;
            font-family: var(--font-secondary);
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
            background-clip: text;
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

        /* ===== ABOUT PAGE ===== */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            margin-bottom: 50px;
        }

        @media (max-width: 992px) {
            .about-content {
                grid-template-columns: 1fr;
            }
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
        }

        @media (max-width: 768px) {
            .skills-grid {
                grid-template-columns: 1fr;
            }
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

        .skill-item:hover {
            transform: translateY(-3px);
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.2) 0%, rgba(255, 215, 0, 0.1) 100%);
        }

        /* Experience */
        .experience-timeline {
            margin-top: 40px;
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
            position: relative;
            padding-left: 10px;
        }

        .experience-content li::before {
            content: '▸';
            color: var(--primary);
            position: absolute;
            left: -15px;
        }

        /* ===== WORK PAGE ===== */
        .work-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 35px;
            margin-top: 30px;
            margin-bottom: 50px;
        }

        @media (max-width: 768px) {
            .work-grid {
                grid-template-columns: 1fr;
            }
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

        .work-image-container:hover {
            border-color: rgba(255, 215, 0, 0.3);
            background: linear-gradient(135deg, #1e1e1e 0%, #2e2e2e 100%);
        }

        .work-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
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
            background-clip: text;
        }

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
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .work-card p {
            color: var(--gray);
            line-height: 1.7;
        }

        /* ===== ACHIEVEMENTS PAGE ===== */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 35px;
            margin-top: 30px;
            margin-bottom: 50px;
        }

        @media (max-width: 768px) {
            .achievements-grid {
                grid-template-columns: 1fr;
            }
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

        .achievement-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .achievement-image-container:hover .achievement-image {
            transform: scale(1.05);
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
        }

        @media (max-width: 768px) {
            .projects-grid {
                grid-template-columns: 1fr;
            }
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
            background-clip: text;
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

        @media (max-width: 576px) {
            .project-stats {
                flex-direction: column;
                gap: 20px;
            }
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

        @media (max-width: 576px) {
            .stat:not(:last-child)::after {
                display: none;
            }
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
            background-clip: text;
        }

        .stat-value.reduction {
            background: var(--gradient-danger);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--gray);
            font-weight: 500;
        }

        /* ===== DASHBOARD PAGE ===== */
        .dashboard-periods {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }

        @media (max-width: 768px) {
            .dashboard-periods {
                grid-template-columns: 1fr;
            }
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
            background-clip: text;
        }

        .period-stat-value.drafter {
            background: var(--gradient-purple);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .period-stat-label {
            color: var(--gray);
            font-size: 0.95rem;
            font-weight: 500;
        }

        /* ===== CHATROOM PAGE ===== */
        .chatroom-container {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            overflow: hidden;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
            height: 70vh;
            display: flex;
            flex-direction: column;
        }

        @media (max-width: 768px) {
            .chatroom-container {
                height: 60vh;
            }
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
            font-family: var(--font-secondary);
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

        @media (max-width: 576px) {
            .chatroom-input {
                flex-direction: column;
            }
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
        }

        @media (max-width: 992px) {
            .contact-content {
                grid-template-columns: 1fr;
            }
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
        }

        @media (max-width: 768px) {
            .contact-info {
                grid-template-columns: 1fr;
            }
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
            background-clip: text;
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

        .edit-btn, .delete-btn, .add-btn {
            position: relative;
            z-index: 5;
            transition: var(--transition);
            font-weight: 700;
            border-radius: 8px;
            padding: 8px 15px;
            font-size: 0.85rem;
            cursor: pointer;
            display: none;
            margin: 5px;
            border: 2px solid transparent;
        }

        .edit-btn {
            background: var(--gradient-gold);
            color: #000;
            border-color: rgba(255, 215, 0, 0.3);
        }

        .edit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }

        .delete-btn {
            background: var(--gradient-danger);
            color: #fff;
            border-color: rgba(255, 71, 87, 0.3);
        }

        .delete-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 71, 87, 0.4);
        }

        .add-btn {
            background: var(--gradient-success);
            color: #fff;
            border-color: rgba(46, 213, 115, 0.3);
            padding: 15px 25px;
            margin: 25px 0;
            font-size: 1rem;
        }

        .add-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(46, 213, 115, 0.4);
        }

        .admin-mode .edit-btn,
        .admin-mode .delete-btn,
        .admin-mode .add-btn {
            display: inline-block;
        }

        /* ===== MODAL STYLES ===== */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            z-index: var(--z-modal);
            display: none;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .modal-content {
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

        .modal-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .modal-title {
            font-size: 2rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 15px;
            font-weight: 800;
            font-family: var(--font-secondary);
        }

        .modal-subtitle {
            color: var(--gray);
            font-size: 1.1rem;
        }

        .modal-close {
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

        .modal-close:hover {
            background: rgba(255, 215, 0, 0.2);
            transform: rotate(90deg);
        }

        /* ===== LOADING OVERLAY ===== */
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
            z-index: var(--z-loader);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
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
            z-index: var(--z-notification);
            display: none;
            animation: slideInRight 0.3s ease;
            max-width: 350px;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
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
            z-index: calc(var(--z-sidebar) + 1);
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(255, 215, 0, 0.3);
        }

        .mobile-menu-toggle:hover {
            transform: scale(1.1);
        }

        /* ===== RESPONSIVE STYLES ===== */
        @media (max-width: 1200px) {
            .sidebar {
                width: 250px;
            }
            
            .main-content {
                margin-left: 250px;
            }
            
            .content-body {
                padding: 30px;
            }
            
            .hero-title {
                font-size: 3.2rem;
            }
        }

        @media (max-width: 992px) {
            .hero-title {
                font-size: 2.8rem;
            }
            
            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            .sidebar {
                width: 100%;
                max-width: 320px;
                transform: translateX(-100%);
                transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            }
            
            .sidebar.active {
                transform: translateX(0);
            }
            
            .main-content {
                margin-left: 0;
                width: 100%;
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
            }
            
            .home-hero {
                padding: 40px 20px;
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
            
            .stats-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
            
            .work-grid,
            .achievements-grid {
                grid-template-columns: 1fr;
            }
            
            .dashboard-periods {
                grid-template-columns: 1fr;
            }
            
            .contact-info {
                grid-template-columns: 1fr;
            }
            
            .floating-add-btn {
                top: auto;
                bottom: 30px;
                right: 20px;
                padding: 12px 20px;
                font-size: 0.85rem;
            }
            
            .effect-toggle {
                bottom: 80px;
                right: 20px;
                padding: 10px 20px;
                font-size: 0.8rem;
            }
        }

        @media (max-width: 576px) {
            .home-hero {
                padding: 30px 15px;
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
            
            .hero-actions {
                flex-direction: column;
                gap: 15px;
            }
            
            .hero-btn {
                width: 100%;
                justify-content: center;
            }
            
            .work-image-container,
            .achievement-image-container {
                height: 200px;
            }
            
            .modal-content {
                padding: 30px 20px;
            }
            
            .modal-title {
                font-size: 1.5rem;
            }
        }

        /* ===== PRINT STYLES ===== */
        @media print {
            .sidebar,
            .floating-add-btn,
            .effect-toggle,
            .mobile-menu-toggle,
            .admin-section,
            .edit-btn,
            .delete-btn,
            .add-btn {
                display: none !important;
            }
            
            .main-content {
                margin-left: 0;
                width: 100%;
            }
            
            .content-header {
                position: static;
                box-shadow: none;
                border-bottom: 2px solid #000;
            }
            
            .page {
                page-break-inside: avoid;
            }
            
            body {
                background: #fff !important;
                color: #000 !important;
            }
            
            .hero-title {
                -webkit-text-fill-color: #000 !important;
                background: none !important;
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

    <div class="app-container">
        <!-- SIDEBAR ELEGAN (TETAP DI KIRI) -->
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
                        <button class="admin-btn" id="resetDataBtn">Reset/Import Data</button>
                    </div>
                </div>
            </div>
            
            <div class="sidebar-footer">
                <p>© 2026 Arya Savariansah. All rights reserved.</p>
            </div>
        </aside>
        
        <!-- KONTEN UTAMA DENGAN SCROLL -->
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
            
            <!-- Content Body - Pages -->
            <div class="content-body" id="contentBody">
                <!-- Home Page -->
                <div class="page active" id="homePage">
                    <div class="home-hero">
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
                                <button class="hero-btn" onclick="changePage('about')">
                                    <i class="fas fa-user"></i> Lihat Profil Lengkap
                                </button>
                                <button class="hero-btn secondary" onclick="changePage('contact')">
                                    <i class="fas fa-envelope"></i> Hubungi Saya
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
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Tentang Saya</h2>
                    
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
                
                <!-- Work Page -->
                <div class="page" id="workPage">
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Work</h2>
                    
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
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Pencapaian & Sertifikat</h2>
                    
                    <div class="achievements-grid" id="achievementsContainer">
                        <!-- Achievement cards akan di-render oleh JavaScript -->
                    </div>
                    <button class="add-btn" data-add="achievement">+ Tambah Pencapaian</button>
                </div>
                
                <!-- Projects Page -->
                <div class="page" id="projectsPage">
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Proyek & Portofolio</h2>
                    
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
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Dashboard Statistik</h2>
                    
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
                </div>
                
                <!-- Chatroom Page -->
                <div class="page" id="chatroomPage">
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; text-align: center;">Chat Room</h2>
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
                    <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">Hubungi Saya</h2>
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
    </div>
    
    <!-- Modal untuk Upload Foto -->
    <div class="modal" id="imageUploadModal">
        <div class="modal-content">
            <button class="modal-close" id="closeImageModal">
                <i class="fas fa-times"></i>
            </button>
            
            <div class="modal-header">
                <h2 class="modal-title" id="modalTitle">Upload Foto</h2>
                <p class="modal-subtitle">Pilih foto yang ingin diupload</p>
            </div>
            
            <div class="form-group">
                <input type="file" id="imageInput" accept="image/*" class="admin-input">
            </div>
            
            <div class="image-preview" id="imagePreview">
                <img id="previewImage" src="" alt="Preview">
            </div>
            
            <div class="modal-buttons" style="display: flex; gap: 15px; margin-top: 30px;">
                <button class="admin-btn" id="saveImageBtn">Simpan Foto</button>
                <button class="admin-btn" style="background: var(--gradient-dark);" id="cancelImageBtn">Batal</button>
                <button class="admin-btn" style="background: var(--gradient-danger); display: none;" id="removeImageBtn">Hapus Foto</button>
            </div>
        </div>
    </div>

    <!-- Modal Upload Work -->
    <div class="modal" id="workUploadModal">
        <div class="modal-content">
            <button class="modal-close" id="closeWorkModal">
                <i class="fas fa-times"></i>
            </button>
            
            <div class="modal-header">
                <h2 class="modal-title">Tambah Work Baru</h2>
                <p class="modal-subtitle">Tambahkan dokumentasi pekerjaan Anda</p>
            </div>
            
            <form id="workUploadForm">
                <div class="form-group">
                    <label for="workTitle">Judul Pekerjaan</label>
                    <input type="text" id="workTitle" class="admin-input" placeholder="Contoh: Standarisasi Molding Setting" required>
                </div>
                
                <div class="form-group">
                    <label for="workDate">Tanggal</label>
                    <input type="text" id="workDate" class="admin-input" placeholder="DD/MM/YYYY" required>
                </div>
                
                <div class="form-group">
                    <label for="workCategory">Kategori</label>
                    <select id="workCategory" class="admin-input" required>
                        <option value="">Pilih Kategori</option>
                        <option value="Mechanical Drafting">Mechanical Drafting</option>
                        <option value="Production Work">Production Work</option>
                        <option value="Quality Control">Quality Control</option>
                        <option value="Process Improvement">Process Improvement</option>
                        <option value="Maintenance">Maintenance</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="workDescription">Deskripsi Singkat</label>
                    <textarea id="workDescription" class="admin-input" placeholder="Jelaskan pekerjaan ini secara singkat" required></textarea>
                </div>
                
                <div class="form-group">
                    <label>Foto Pekerjaan</label>
                    <input type="file" id="workImageInput" accept="image/*" class="admin-input">
                    <div class="image-preview" id="workImagePreview" style="margin-top: 10px;">
                        <img id="workPreviewImage" src="" alt="Preview">
                    </div>
                </div>
                
                <div class="modal-buttons" style="display: flex; gap: 15px; margin-top: 30px;">
                    <button type="submit" class="admin-btn" id="saveWorkBtn">Simpan Work</button>
                    <button type="button" class="admin-btn" style="background: var(--gradient-dark);" id="cancelWorkBtn">Batal</button>
                </div>
            </form>
        </div>
    </div>
    
    <!-- Loading Overlay -->
    <div class="loading-overlay" id="loadingOverlay">
        <div class="loading-spinner"></div>
        <div class="loading-text" id="loadingText">Loading...</div>
    </div>
    
    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <script>
        // ============================================
        // DATA APLIKASI & KONFIGURASI
        // ============================================
        let appData = {
            user: {
                name: "Arya Savariansah",
                title: "Spesialis Manufaktur",
                email: "aryasavarinasah@gmail.com",
                phone: "089520336532",
                location: "Kosambi, Indonesia",
                linkedin: "linkedin.com/in/arya-savariansah",
                profileImage: null,
                profileImageKey: null
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
                    items: [],
                    categories: ["Mechanical Drafting", "Production Work", "Quality Control", "Process Improvement", "Maintenance"]
                },
                achievements: {
                    title: "Achievements",
                    description: "Pencapaian dan sertifikat profesional",
                    items: []
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
        let currentUploadType = null;
        let currentItemId = null;
        let currentImageFile = null;
        let currentImageUrl = null;

        // Variables untuk efek
        let rainEffectActive = false;
        let starfallEffectActive = false;
        let currentEffectPage = null;

        // ============================================
        // FUNGSI UTILITAS
        // ============================================

        // Load data dari localStorage
        function loadFromLocalStorage() {
            const savedData = localStorage.getItem('portfolioData');
            if (savedData) {
                try {
                    const data = JSON.parse(savedData);
                    
                    // Merge dengan data default
                    appData = { ...appData, ...data };
                    
                    // Ensure arrays exist
                    if (!appData.pages.work.items) appData.pages.work.items = [];
                    if (!appData.pages.achievements.items) appData.pages.achievements.items = [];
                    
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

        // Upload gambar ke localStorage
        function uploadImageToStorage(file, type, itemId = null) {
            return new Promise((resolve, reject) => {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    const base64Image = e.target.result;
                    const imageKey = `${type}_${itemId || 'profile'}_${Date.now()}`;
                    
                    // Simpan di localStorage
                    localStorage.setItem(imageKey, base64Image);
                    
                    resolve({
                        key: imageKey,
                        dataUrl: base64Image
                    });
                };
                
                reader.onerror = function() {
                    reject('Gagal membaca file gambar');
                };
                
                reader.readAsDataURL(file);
            });
        }

        // Hapus gambar dari storage
        function removeImageFromStorage(key) {
            localStorage.removeItem(key);
        }

        // ============================================
        // FUNGSI INISIALISASI
        // ============================================

        document.addEventListener('DOMContentLoaded', function() {
            loadFromLocalStorage();
            setupNavigation();
            setupAdminPanel();
            setupChat();
            setupContactForm();
            setupMobileMenu();
            setupModals();
            setupEffects();
            renderPage(currentPage);
            updateAdminUI();
            setupResponsiveBehavior();
            
            // Setup event listeners
            document.getElementById('addWorkBtn').addEventListener('click', openWorkUploadModal);
            document.getElementById('floatingAddBtn').addEventListener('click', openWorkUploadModal);
            
            // Profile image click
            document.getElementById('profileImg').addEventListener('click', function() {
                if (appData.user.profileImage) {
                    openImagePreview(appData.user.profileImage, 'Profile Picture');
                }
            });
            
            // Initial render
            renderProfileImage();
            
            // Setup cleanup interval
            setInterval(cleanupUnusedImages, 60000);
        });

        // Setup modals
        function setupModals() {
            // Image Upload Modal
            const imageModal = document.getElementById('imageUploadModal');
            const imageInput = document.getElementById('imageInput');
            const previewImage = document.getElementById('previewImage');
            const imagePreview = document.getElementById('imagePreview');
            const saveImageBtn = document.getElementById('saveImageBtn');
            const cancelImageBtn = document.getElementById('cancelImageBtn');
            const removeImageBtn = document.getElementById('removeImageBtn');
            const closeImageModal = document.getElementById('closeImageModal');
            
            // Profile upload button
            document.getElementById('profileUploadBtn').addEventListener('click', function(e) {
                e.stopPropagation();
                if (isAdminLoggedIn || isEditMode) {
                    openImageUploadModal('profile');
                }
            });
            
            // Image input change
            imageInput.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    if (file.size > 5 * 1024 * 1024) {
                        showNotification('Ukuran file terlalu besar. Maksimal 5MB.', 'error');
                        return;
                    }
                    
                    if (!file.type.match('image.*')) {
                        showNotification('Hanya file gambar yang diperbolehkan.', 'error');
                        return;
                    }
                    
                    currentImageFile = file;
                    const reader = new FileReader();
                    
                    reader.onload = function(event) {
                        currentImageUrl = event.target.result;
                        previewImage.src = currentImageUrl;
                        imagePreview.style.display = 'block';
                        removeImageBtn.style.display = 'inline-block';
                    };
                    
                    reader.readAsDataURL(file);
                }
            });
            
            // Save image
            saveImageBtn.addEventListener('click', async function() {
                if (!currentImageFile && !currentImageUrl) {
                    showNotification('Silakan pilih gambar terlebih dahulu', 'error');
                    return;
                }
                
                showLoading('Mengupload gambar...');
                
                try {
                    let finalImageUrl = currentImageUrl;
                    let finalImageKey = null;
                    
                    if (currentImageFile) {
                        const uploadResult = await uploadImageToStorage(
                            currentImageFile, 
                            currentUploadType, 
                            currentItemId || 'profile'
                        );
                        
                        finalImageUrl = uploadResult.dataUrl;
                        finalImageKey = uploadResult.key;
                    }
                    
                    if (currentUploadType === 'profile') {
                        // Hapus gambar lama jika ada
                        if (appData.user.profileImageKey) {
                            removeImageFromStorage(appData.user.profileImageKey);
                        }
                        
                        appData.user.profileImage = finalImageUrl;
                        appData.user.profileImageKey = finalImageKey;
                        renderProfileImage();
                        showNotification('Foto profile berhasil diupload!', 'success');
                        
                    } else if (currentUploadType === 'achievement' && currentItemId) {
                        const achievement = appData.pages.achievements.items.find(a => a.id === currentItemId);
                        if (achievement) {
                            if (achievement.imageKey) {
                                removeImageFromStorage(achievement.imageKey);
                            }
                            
                            achievement.image = finalImageUrl;
                            achievement.imageKey = finalImageKey;
                            renderAchievementsPage();
                            showNotification('Foto achievement berhasil diupload!', 'success');
                        }
                    } else if (currentUploadType === 'work' && currentItemId) {
                        const work = appData.pages.work.items.find(d => d.id === currentItemId);
                        if (work) {
                            if (work.imageKey) {
                                removeImageFromStorage(work.imageKey);
                            }
                            
                            work.image = finalImageUrl;
                            work.imageKey = finalImageKey;
                            renderWorkPage();
                            showNotification('Foto Work berhasil diupload!', 'success');
                        }
                    }
                    
                    saveToLocalStorage();
                    hideLoading();
                    closeModal(imageModal);
                    resetImageModal();
                    
                } catch (error) {
                    hideLoading();
                    showNotification('Gagal mengupload gambar: ' + error, 'error');
                }
            });
            
            // Remove image
            removeImageBtn.addEventListener('click', function() {
                if (confirm('Apakah Anda yakin ingin menghapus gambar ini?')) {
                    showLoading('Menghapus gambar...');
                    
                    setTimeout(() => {
                        if (currentUploadType === 'profile') {
                            if (appData.user.profileImageKey) {
                                removeImageFromStorage(appData.user.profileImageKey);
                            }
                            appData.user.profileImage = null;
                            appData.user.profileImageKey = null;
                            renderProfileImage();
                            showNotification('Foto profile berhasil dihapus!', 'success');
                        } else if (currentUploadType === 'achievement' && currentItemId) {
                            const achievement = appData.pages.achievements.items.find(a => a.id === currentItemId);
                            if (achievement) {
                                if (achievement.imageKey) {
                                    removeImageFromStorage(achievement.imageKey);
                                }
                                achievement.image = null;
                                achievement.imageKey = null;
                                renderAchievementsPage();
                                showNotification('Foto achievement berhasil dihapus!', 'success');
                            }
                        } else if (currentUploadType === 'work' && currentItemId) {
                            const work = appData.pages.work.items.find(d => d.id === currentItemId);
                            if (work) {
                                if (work.imageKey) {
                                    removeImageFromStorage(work.imageKey);
                                }
                                work.image = null;
                                work.imageKey = null;
                                renderWorkPage();
                                showNotification('Foto Work berhasil dihapus!', 'success');
                            }
                        }
                        
                        saveToLocalStorage();
                        hideLoading();
                        closeModal(imageModal);
                        resetImageModal();
                    }, 500);
                }
            });
            
            // Cancel/Close buttons
            cancelImageBtn.addEventListener('click', function() {
                closeModal(imageModal);
                resetImageModal();
            });
            
            closeImageModal.addEventListener('click', function() {
                closeModal(imageModal);
                resetImageModal();
            });
            
            // Work Upload Modal
            const workModal = document.getElementById('workUploadModal');
            const workForm = document.getElementById('workUploadForm');
            const workImageInput = document.getElementById('workImageInput');
            const workPreviewImage = document.getElementById('workPreviewImage');
            const workImagePreview = document.getElementById('workImagePreview');
            const saveWorkBtn = document.getElementById('saveWorkBtn');
            const cancelWorkBtn = document.getElementById('cancelWorkBtn');
            const closeWorkModal = document.getElementById('closeWorkModal');
            
            let editingWorkId = null;
            
            // Open work modal
            window.openWorkUploadModal = function(editId = null) {
                if (!isAdminLoggedIn && !isEditMode) {
                    showNotification('Silakan login sebagai admin untuk menambah work', 'error');
                    return;
                }
                
                resetWorkModal();
                
                if (editId) {
                    editingWorkId = editId;
                    const work = appData.pages.work.items.find(w => w.id === editId);
                    if (work) {
                        document.getElementById('workTitle').value = work.title;
                        document.getElementById('workDate').value = work.date;
                        document.getElementById('workCategory').value = work.category;
                        document.getElementById('workDescription').value = work.description;
                        
                        if (work.image) {
                            workPreviewImage.src = work.image;
                            workImagePreview.style.display = 'block';
                        }
                        
                        saveWorkBtn.textContent = 'Update Work';
                        document.querySelector('#workUploadModal .modal-title').textContent = 'Edit Work';
                    }
                } else {
                    editingWorkId = null;
                    saveWorkBtn.textContent = 'Simpan Work';
                    document.querySelector('#workUploadModal .modal-title').textContent = 'Tambah Work Baru';
                }
                
                openModal(workModal);
            };
            
            // Work image input
            workImageInput.addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    if (file.size > 5 * 1024 * 1024) {
                        showNotification('Ukuran file terlalu besar. Maksimal 5MB.', 'error');
                        return;
                    }
                    
                    if (!file.type.match('image.*')) {
                        showNotification('Hanya file gambar yang diperbolehkan.', 'error');
                        return;
                    }
                    
                    currentImageFile = file;
                    const reader = new FileReader();
                    
                    reader.onload = function(event) {
                        currentImageUrl = event.target.result;
                        workPreviewImage.src = currentImageUrl;
                        workImagePreview.style.display = 'block';
                    };
                    
                    reader.readAsDataURL(file);
                }
            });
            
            // Work form submit
            workForm.addEventListener('submit', async function(e) {
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
                
                const dateRegex = /^\d{2}\/\d{2}\/\d{4}$/;
                if (!dateRegex.test(date)) {
                    showNotification('Format tanggal harus DD/MM/YYYY', 'error');
                    return;
                }
                
                showLoading(editingWorkId ? 'Memperbarui Work...' : 'Menyimpan Work...');
                
                try {
                    let finalImageUrl = currentImageUrl;
                    let finalImageKey = null;
                    
                    if (currentImageFile) {
                        const uploadResult = await uploadImageToStorage(
                            currentImageFile, 
                            'work', 
                            editingWorkId || `work_${Date.now()}`
                        );
                        
                        finalImageUrl = uploadResult.dataUrl;
                        finalImageKey = uploadResult.key;
                    }
                    
                    if (editingWorkId) {
                        // Update existing work
                        const work = appData.pages.work.items.find(w => w.id === editingWorkId);
                        if (work) {
                            // Hapus gambar lama jika diganti
                            if (currentImageFile && work.imageKey) {
                                removeImageFromStorage(work.imageKey);
                            }
                            
                            work.title = title;
                            work.date = date;
                            work.category = category;
                            work.description = description;
                            if (currentImageFile) {
                                work.image = finalImageUrl;
                                work.imageKey = finalImageKey;
                            }
                        }
                    } else {
                        // Add new work
                        const newId = 'work_' + Date.now();
                        const newWork = {
                            id: newId,
                            title: title,
                            date: date,
                            category: category,
                            description: description,
                            image: finalImageUrl,
                            imageKey: finalImageKey
                        };
                        
                        appData.pages.work.items.unshift(newWork);
                    }
                    
                    renderWorkPage();
                    saveToLocalStorage();
                    hideLoading();
                    closeModal(workModal);
                    resetWorkModal();
                    
                    showNotification(
                        editingWorkId ? 'Work berhasil diperbarui!' : 'Work berhasil ditambahkan!',
                        'success'
                    );
                    
                } catch (error) {
                    hideLoading();
                    showNotification('Gagal mengupload gambar: ' + error, 'error');
                }
            });
            
            // Cancel/Close work modal
            cancelWorkBtn.addEventListener('click', function() {
                closeModal(workModal);
                resetWorkModal();
            });
            
            closeWorkModal.addEventListener('click', function() {
                closeModal(workModal);
                resetWorkModal();
            });
            
            // Close modal on outside click
            document.querySelectorAll('.modal').forEach(modal => {
                modal.addEventListener('click', function(e) {
                    if (e.target === modal) {
                        closeModal(modal);
                        if (modal === imageModal) resetImageModal();
                        if (modal === workModal) resetWorkModal();
                    }
                });
            });
            
            // Close modal on ESC key
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape') {
                    document.querySelectorAll('.modal.active').forEach(modal => {
                        closeModal(modal);
                        if (modal === imageModal) resetImageModal();
                        if (modal === workModal) resetWorkModal();
                    });
                }
            });
        }

        // Modal helper functions
        function openModal(modal) {
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal(modal) {
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        function resetImageModal() {
            document.getElementById('imageInput').value = '';
            document.getElementById('previewImage').src = '';
            document.getElementById('imagePreview').style.display = 'none';
            document.getElementById('removeImageBtn').style.display = 'none';
            currentUploadType = null;
            currentItemId = null;
            currentImageFile = null;
            currentImageUrl = null;
        }

        function resetWorkModal() {
            document.getElementById('workUploadForm').reset();
            document.getElementById('workPreviewImage').src = '';
            document.getElementById('workImagePreview').style.display = 'none';
            currentImageFile = null;
            currentImageUrl = null;
            editingWorkId = null;
        }

        // Open image upload modal
        function openImageUploadModal(type, itemId = null) {
            currentUploadType = type;
            currentItemId = itemId;
            
            const modal = document.getElementById('imageUploadModal');
            const modalTitle = document.getElementById('modalTitle');
            const removeImageBtn = document.getElementById('removeImageBtn');
            const previewImage = document.getElementById('previewImage');
            const imagePreview = document.getElementById('imagePreview');
            
            let currentImage = null;
            
            if (type === 'profile') {
                modalTitle.textContent = 'Upload Foto Profile';
                currentImage = appData.user.profileImage;
            } else if (type === 'achievement' && itemId) {
                const achievement = appData.pages.achievements.items.find(a => a.id === itemId);
                if (achievement) {
                    modalTitle.textContent = `Upload Foto untuk: ${achievement.title}`;
                    currentImage = achievement.image;
                }
            } else if (type === 'work' && itemId) {
                const work = appData.pages.work.items.find(d => d.id === itemId);
                if (work) {
                    modalTitle.textContent = `Upload Foto untuk: ${work.title}`;
                    currentImage = work.image;
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
            
            openModal(modal);
        }

        // Open image preview
        function openImagePreview(imageSrc, caption = '') {
            // Simple image preview (bisa dikembangkan jadi modal zoom)
            const newWindow = window.open();
            newWindow.document.write(`
                <html>
                    <head>
                        <title>${caption}</title>
                        <style>
                            body { margin: 0; padding: 20px; background: #000; display: flex; justify-content: center; align-items: center; min-height: 100vh; }
                            img { max-width: 90vw; max-height: 90vh; border: 2px solid #ffd700; border-radius: 10px; }
                        </style>
                    </head>
                    <body>
                        <img src="${imageSrc}" alt="${caption}">
                    </body>
                </html>
            `);
        }

        // Setup responsive behavior
        function setupResponsiveBehavior() {
            function handleResize() {
                const sidebar = document.getElementById('sidebar');
                const mobileMenuToggle = document.getElementById('mobileMenuToggle');
                const mainContent = document.getElementById('mainContent');
                
                if (window.innerWidth <= 768) {
                    mobileMenuToggle.style.display = 'block';
                    mainContent.style.marginLeft = '0';
                } else {
                    mobileMenuToggle.style.display = 'none';
                    sidebar.classList.remove('active');
                    mainContent.style.marginLeft = sidebar.offsetWidth + 'px';
                }
            }
            
            window.addEventListener('resize', handleResize);
            handleResize();
        }

        // Setup mobile menu
        function setupMobileMenu() {
            const mobileMenuToggle = document.getElementById('mobileMenuToggle');
            const sidebar = document.getElementById('sidebar');
            
            mobileMenuToggle.addEventListener('click', function() {
                sidebar.classList.toggle('active');
                this.innerHTML = sidebar.classList.contains('active') 
                    ? '<i class="fas fa-times"></i>' 
                    : '<i class="fas fa-bars"></i>';
            });
            
            // Close sidebar when clicking outside on mobile
            document.addEventListener('click', function(e) {
                if (window.innerWidth <= 768 && 
                    !sidebar.contains(e.target) && 
                    !mobileMenuToggle.contains(e.target) &&
                    sidebar.classList.contains('active')) {
                    sidebar.classList.remove('active');
                    mobileMenuToggle.innerHTML = '<i class="fas fa-bars"></i>';
                }
            });
        }

        // ============================================
        // FUNGSI NAVIGASI & RENDER HALAMAN
        // ============================================

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
                    
                    // Close sidebar on mobile
                    if (window.innerWidth <= 768) {
                        document.getElementById('sidebar').classList.remove('active');
                        document.getElementById('mobileMenuToggle').innerHTML = '<i class="fas fa-bars"></i>';
                    }
                });
            });
        }

        // Change page
        function changePage(pageId) {
            // Reset efek jika ada
            if (rainEffectActive) toggleRainEffect();
            if (starfallEffectActive) toggleStarfallEffect();
            hideEffectToggle();
            
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
                page.style.animation = 'none';
                setTimeout(() => {
                    page.style.animation = '';
                }, 10);
            });
            
            // Show selected page
            const pageElement = document.getElementById(pageId + 'Page');
            if (pageElement) {
                pageElement.classList.add('active');
                currentPage = pageId;
                
                // Update page title and description
                const pageData = appData.pages[pageId];
                if (pageData) {
                    document.getElementById('currentPageTitle').textContent = pageData.title;
                    document.getElementById('currentPageDesc').textContent = pageData.description;
                }
                
                // Render page content
                renderPage(pageId);
                
                // Scroll to top
                document.querySelector('.main-content').scrollTop = 0;
                
                // Update admin UI
                updateAdminUI();
                
                // Show effect toggle for specific pages
                if (pageId === 'about' || pageId === 'chatroom') {
                    setTimeout(() => {
                        showEffectToggle(
                            pageId === 'about' ? 'Rain Effect' : 'Starfall Effect',
                            pageId === 'about' ? 'fas fa-cloud-rain' : 'fas fa-star'
                        );
                    }, 500);
                }
            }
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
            
            // Clear existing experiences (keep the first two)
            const existingExperiences = timeline.querySelectorAll('.experience-item');
            for (let i = 2; i < existingExperiences.length; i++) {
                existingExperiences[i].remove();
            }
            
            // Render experiences
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
                } else if (expElement) {
                    expElement.querySelector('.experience-title').textContent = exp.title;
                    expElement.querySelector('.experience-date').textContent = exp.date;
                    expElement.querySelector('.experience-content ul').innerHTML = 
                        exp.items.map(item => `<li>${item}</li>`).join('');
                }
            });
            
            // Setup event listeners
            setupEditModeListeners();
        }

        // Render work page
        function renderWorkPage() {
            const pageData = appData.pages.work;
            const container = document.getElementById('workContainer');
            
            if (!container) return;
            
            container.innerHTML = '';
            
            // Sort by date (newest first)
            const sortedItems = [...pageData.items].sort((a, b) => {
                const convertToTimestamp = (dateStr) => {
                    const [day, month, year] = dateStr.split('/').map(Number);
                    return new Date(year, month - 1, day).getTime();
                };
                
                const timeA = convertToTimestamp(a.date) || 0;
                const timeB = convertToTimestamp(b.date) || 0;
                return timeB - timeA;
            });
            
            sortedItems.forEach((item) => {
                const workElement = document.createElement('div');
                workElement.className = 'work-card editable';
                workElement.id = item.id;
                
                let imageHTML = '';
                if (item.image) {
                    imageHTML = `
                        <div class="work-image-container" onclick="openImagePreview('${item.image}', '${item.title}')">
                            <img src="${item.image}" alt="${item.title}" class="work-image">
                            <div class="category-badge">${item.category}</div>
                        </div>
                    `;
                } else {
                    imageHTML = `
                        <div class="work-image-container" onclick="editWorkImage('${item.id}')">
                            <div class="work-image-placeholder">
                                <i class="fas fa-camera"></i>
                            </div>
                            <div class="category-badge">${item.category}</div>
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
                    ${(isAdminLoggedIn || isEditMode) ? `
                        <button class="edit-btn" onclick="editWork('${item.id}')">Edit</button>
                        <button class="delete-btn" onclick="deleteWork('${item.id}')">Hapus</button>
                    ` : ''}
                `;
                
                container.appendChild(workElement);
            });
            
            // Show/hide add button
            const addBtn = document.getElementById('addWorkBtn');
            if (addBtn) {
                addBtn.style.display = (isAdminLoggedIn || isEditMode) ? 'inline-block' : 'none';
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
                        <div class="achievement-image-container" onclick="openImagePreview('${item.image}', '${item.title}')">
                            <img src="${item.image}" alt="${item.title}" class="achievement-image">
                        </div>
                    `;
                } else {
                    imageHTML = `
                        <div class="achievement-image-container" onclick="editAchievementImage('${item.id}')">
                            <div class="achievement-image-placeholder">
                                <i class="fas fa-trophy"></i>
                            </div>
                        </div>
                    `;
                }
                
                achievementElement.innerHTML = `
                    ${imageHTML}
                    <h3>${item.title}</h3>
                    <div class="date">${item.date}</div>
                    <p>${item.description}</p>
                    ${(isAdminLoggedIn || isEditMode) ? `
                        <button class="edit-btn" onclick="editAchievement('${item.id}')">Edit</button>
                        <button class="delete-btn" onclick="deleteAchievement('${item.id}')">Hapus</button>
                    ` : ''}
                `;
                
                container.appendChild(achievementElement);
            });
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
                    ${(isAdminLoggedIn || isEditMode) ? `
                        <button class="edit-btn" onclick="editProject('${item.id}')">Edit</button>
                        <button class="delete-btn" onclick="deleteProject('${item.id}')">Hapus</button>
                    ` : ''}
                `;
                
                container.appendChild(projectElement);
            });
        }

        // Render dashboard page
        function renderDashboardPage() {
            const pageData = appData.pages.dashboard;
            
            pageData.periods.forEach(period => {
                const periodElement = document.getElementById(period.id);
                if (periodElement) {
                    periodElement.querySelector('.period-title').textContent = period.title;
                    periodElement.querySelector('.period-date').innerHTML = `<i class="far fa-calendar"></i> ${period.date}`;
                    
                    period.stats.forEach(stat => {
                        const statElement = document.getElementById(stat.id);
                        if (statElement) {
                            const valueElement = statElement.querySelector('.period-stat-value');
                            const labelElement = statElement.querySelector('.period-stat-label');
                            
                            if (valueElement) valueElement.textContent = stat.value;
                            if (labelElement) labelElement.textContent = stat.label;
                            
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

        // ============================================
        // FUNGSI EDIT & DELETE
        // ============================================

        // Setup edit mode listeners
        function setupEditModeListeners() {
            // Edit buttons
            document.querySelectorAll('.edit-btn').forEach(btn => {
                if (!btn.onclick) {
                    btn.addEventListener('click', function() {
                        const elementId = this.getAttribute('data-edit');
                        editElement(elementId);
                    });
                }
            });
            
            // Delete buttons
            document.querySelectorAll('.delete-btn').forEach(btn => {
                if (!btn.onclick) {
                    btn.addEventListener('click', function() {
                        const elementId = this.getAttribute('data-delete');
                        const type = this.getAttribute('data-type');
                        deleteElement(elementId, type);
                    });
                }
            });
            
            // Add buttons
            document.querySelectorAll('.add-btn').forEach(btn => {
                if (!btn.onclick) {
                    btn.addEventListener('click', function() {
                        const type = this.getAttribute('data-add');
                        addElement(type);
                    });
                }
            });
        }

        // Edit element
        function editElement(elementId) {
            const element = document.getElementById(elementId);
            if (!element) return;
            
            // Handle different element types
            if (element.classList.contains('skill-category')) {
                editSkills(elementId);
            } else if (element.classList.contains('experience-item')) {
                editExperience(elementId);
            } else if (elementId.startsWith('stat')) {
                editStat(elementId);
            } else if (element.classList.contains('contact-card')) {
                editContact(elementId);
            } else if (element.classList.contains('period-section')) {
                editPeriod(elementId);
            } else {
                editText(elementId);
            }
        }

        // Edit text
        function editText(elementId) {
            const element = document.getElementById(elementId);
            if (!element) return;
            
            const currentText = element.textContent;
            const newText = prompt('Edit teks:', currentText);
            
            if (newText !== null && newText !== currentText) {
                element.textContent = newText;
                
                // Update data structure based on element ID
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
                
                saveToLocalStorage();
                showNotification('Teks berhasil diperbarui!', 'success');
            }
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
                saveToLocalStorage();
                showNotification('Skill berhasil diperbarui!', 'success');
            }
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
            saveToLocalStorage();
            showNotification('Pengalaman berhasil diperbarui!', 'success');
        }

        // Edit stat
        function editStat(statId) {
            const element = document.getElementById(statId);
            if (!element) return;
            
            let numberElement, labelElement;
            
            if (element.classList.contains('period-stat')) {
                numberElement = element.querySelector('.period-stat-value');
                labelElement = element.querySelector('.period-stat-label');
            } else if (element.classList.contains('stat-card')) {
                numberElement = element.querySelector('.stat-number');
                labelElement = element.querySelector('.stat-label');
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
            
            // Update data structure
            if (statId.startsWith('staffStat') || statId.startsWith('drafterStat')) {
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
            
            saveToLocalStorage();
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
                
                saveToLocalStorage();
                showNotification('Kontak berhasil diperbarui!', 'success');
            }
        }

        // Edit period
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
            saveToLocalStorage();
            showNotification('Periode berhasil diperbarui!', 'success');
        }

        // Delete element
        function deleteElement(elementId, type) {
            if (!confirm('Apakah Anda yakin ingin menghapus ini?')) {
                return;
            }
            
            showLoading('Menghapus...');
            
            setTimeout(() => {
                switch(type) {
                    case 'experience':
                        const expIndex = appData.pages.about.experiences.findIndex(exp => exp.id === elementId);
                        if (expIndex !== -1) {
                            appData.pages.about.experiences.splice(expIndex, 1);
                            renderExperiences();
                        }
                        break;
                        
                    case 'project':
                        const projIndex = appData.pages.projects.items.findIndex(p => p.id === elementId);
                        if (projIndex !== -1) {
                            appData.pages.projects.items.splice(projIndex, 1);
                            renderProjectsPage();
                        }
                        break;
                }
                
                saveToLocalStorage();
                hideLoading();
                showNotification('Berhasil dihapus!', 'success');
            }, 500);
        }

        // Add element
        function addElement(type) {
            switch(type) {
                case 'technicalSkills':
                case 'personalSkills':
                    const newSkill = prompt('Masukkan skill baru:');
                    if (newSkill && newSkill.trim() !== '') {
                        const isTechnical = type === 'technicalSkills';
                        if (isTechnical) {
                            appData.pages.about.skills.technical.push(newSkill.trim());
                        } else {
                            appData.pages.about.skills.personal.push(newSkill.trim());
                        }
                        renderSkills();
                        saveToLocalStorage();
                        showNotification('Skill berhasil ditambahkan!', 'success');
                    }
                    break;
                    
                case 'experience':
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
                    saveToLocalStorage();
                    showNotification('Pengalaman berhasil ditambahkan!', 'success');
                    break;
                    
                case 'achievement':
                    const achTitle = prompt('Masukkan judul pencapaian:');
                    if (!achTitle) return;
                    
                    const achDate = prompt('Masukkan tanggal:');
                    if (!achDate) return;
                    
                    const achDesc = prompt('Masukkan deskripsi:');
                    if (!achDesc) return;
                    
                    const achId = 'achievement' + (appData.pages.achievements.items.length + 1);
                    const newAchievement = {
                        id: achId,
                        title: achTitle,
                        date: achDate,
                        description: achDesc,
                        image: null,
                        imageKey: null
                    };
                    
                    appData.pages.achievements.items.push(newAchievement);
                    renderAchievementsPage();
                    saveToLocalStorage();
                    showNotification('Pencapaian berhasil ditambahkan!', 'success');
                    break;
                    
                case 'project':
                    const projTitle = prompt('Masukkan judul proyek:');
                    if (!projTitle) return;
                    
                    const projDesc = prompt('Masukkan deskripsi:');
                    if (!projDesc) return;
                    
                    const projId = 'project' + (appData.pages.projects.items.length + 1);
                    const newProject = {
                        id: projId,
                        title: projTitle,
                        description: projDesc,
                        stats: [
                            { value: "0%", label: "Statistik 1" },
                            { value: "↓ 0%", label: "Statistik 2", type: "improvement" },
                            { value: "0%", label: "Statistik 3" }
                        ]
                    };
                    
                    appData.pages.projects.items.push(newProject);
                    renderProjectsPage();
                    saveToLocalStorage();
                    showNotification('Proyek berhasil ditambahkan!', 'success');
                    break;
            }
        }

        // Work specific functions
        function editWork(workId) {
            openWorkUploadModal(workId);
        }

        function deleteWork(workId) {
            if (!confirm('Apakah Anda yakin ingin menghapus pekerjaan ini?')) {
                return;
            }
            
            showLoading('Menghapus...');
            
            const index = appData.pages.work.items.findIndex(w => w.id === workId);
            if (index !== -1) {
                const work = appData.pages.work.items[index];
                if (work.imageKey) {
                    removeImageFromStorage(work.imageKey);
                }
                
                appData.pages.work.items.splice(index, 1);
                renderWorkPage();
                saveToLocalStorage();
                showNotification('Pekerjaan berhasil dihapus!', 'success');
            }
            
            hideLoading();
        }

        function editWorkImage(workId) {
            if (!isAdminLoggedIn && !isEditMode) {
                showNotification('Silakan login sebagai admin untuk mengedit foto', 'error');
                return;
            }
            
            openImageUploadModal('work', workId);
        }

        // Achievement specific functions
        function editAchievement(achievementId) {
            const achievement = appData.pages.achievements.items.find(a => a.id === achievementId);
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
            saveToLocalStorage();
            showNotification('Pencapaian berhasil diperbarui!', 'success');
        }

        function deleteAchievement(achievementId) {
            if (!confirm('Apakah Anda yakin ingin menghapus pencapaian ini?')) {
                return;
            }
            
            showLoading('Menghapus...');
            
            const index = appData.pages.achievements.items.findIndex(a => a.id === achievementId);
            if (index !== -1) {
                const achievement = appData.pages.achievements.items[index];
                if (achievement.imageKey) {
                    removeImageFromStorage(achievement.imageKey);
                }
                
                appData.pages.achievements.items.splice(index, 1);
                renderAchievementsPage();
                saveToLocalStorage();
                showNotification('Pencapaian berhasil dihapus!', 'success');
            }
            
            hideLoading();
        }

        function editAchievementImage(achievementId) {
            if (!isAdminLoggedIn && !isEditMode) {
                showNotification('Silakan login sebagai admin untuk mengedit foto', 'error');
                return;
            }
            
            openImageUploadModal('achievement', achievementId);
        }

        // Project specific functions
        function editProject(projectId) {
            const project = appData.pages.projects.items.find(p => p.id === projectId);
            if (!project) return;
            
            const newTitle = prompt('Edit judul proyek:', project.title);
            if (newTitle === null) return;
            
            const newDescription = prompt('Edit deskripsi:', project.description);
            if (newDescription === null) return;
            
            project.title = newTitle;
            project.description = newDescription;
            
            renderProjectsPage();
            saveToLocalStorage();
            showNotification('Proyek berhasil diperbarui!', 'success');
        }

        function deleteProject(projectId) {
            if (!confirm('Apakah Anda yakin ingin menghapus proyek ini?')) {
                return;
            }
            
            showLoading('Menghapus...');
            
            const index = appData.pages.projects.items.findIndex(p => p.id === projectId);
            if (index !== -1) {
                appData.pages.projects.items.splice(index, 1);
                renderProjectsPage();
                saveToLocalStorage();
                showNotification('Proyek berhasil dihapus!', 'success');
            }
            
            hideLoading();
        }

        // ============================================
        // ADMIN PANEL FUNCTIONS
        // ============================================

        // Setup admin panel
        function setupAdminPanel() {
            const adminToggle = document.getElementById('adminToggle');
            const adminPanel = document.getElementById('adminPanel');
            const adminLogin = document.getElementById('adminLogin');
            const adminLogout = document.getElementById('adminLogout');
            const toggleEditMode = document.getElementById('toggleEditMode');
            const saveAllData = document.getElementById('saveAllData');
            const resetDataBtn = document.getElementById('resetDataBtn');
            
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
                    setupEditModeListeners();
                }
                
                // Re-render current page to show/hide edit buttons
                renderPage(currentPage);
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
            
            resetDataBtn.addEventListener('click', function() {
                if (!confirm('Reset data akan menghapus semua data yang tersimpan. Lanjutkan?')) {
                    return;
                }
                
                showLoading('Mereset data...');
                
                localStorage.clear();
                location.reload();
            });
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
            
            document.getElementById('editStatus').style.display = isEditMode ? 'block' : 'none';
        }

        // ============================================
        // CHAT & CONTACT FUNCTIONS
        // ============================================

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
                
                // Auto reply
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

        // ============================================
        // EFFECTS FUNCTIONS
        // ============================================

        // Setup effects
        function setupEffects() {
            const effectToggle = document.getElementById('effectToggle');
            
            if (effectToggle) {
                effectToggle.addEventListener('click', toggleEffects);
            }
            
            // Show effect toggle on specific pages
            const aboutPage = document.getElementById('aboutPage');
            if (aboutPage) {
                aboutPage.addEventListener('mouseenter', function() {
                    if (currentPage === 'about' && !rainEffectActive) {
                        showEffectToggle('Rain Effect', 'fas fa-cloud-rain');
                    }
                });
            }
            
            const chatroomPage = document.getElementById('chatroomPage');
            if (chatroomPage) {
                chatroomPage.addEventListener('mouseenter', function() {
                    if (currentPage === 'chatroom' && !starfallEffectActive) {
                        showEffectToggle('Starfall Effect', 'fas fa-star');
                    }
                });
            }
        }

        // Show effect toggle
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

        // Hide effect toggle
        function hideEffectToggle() {
            const effectToggle = document.getElementById('effectToggle');
            if (effectToggle) {
                effectToggle.style.display = 'none';
                currentEffectPage = null;
            }
        }

        // Toggle effects
        function toggleEffects() {
            if (currentEffectPage === 'about') {
                toggleRainEffect();
            } else if (currentEffectPage === 'chatroom') {
                toggleStarfallEffect();
            }
        }

        // Toggle rain effect
        function toggleRainEffect() {
            rainEffectActive = !rainEffectActive;
            const rainContainer = document.getElementById('rainContainer');
            const effectToggle = document.getElementById('effectToggle');
            const effectText = document.getElementById('effectText');
            
            if (rainEffectActive) {
                // Disable other effect
                if (starfallEffectActive) {
                    toggleStarfallEffect();
                }
                
                rainContainer.style.display = 'block';
                effectText.textContent = 'Matikan Rain Effect';
                createRainDrops();
                effectToggle.style.background = 'var(--gradient-cyan)';
                effectToggle.style.color = '#000';
                
                showNotification('Rain Effect diaktifkan!', 'success');
            } else {
                rainContainer.style.display = 'none';
                effectText.textContent = 'Aktifkan Rain Effect';
                effectToggle.style.background = 'var(--gradient-gold)';
                effectToggle.style.color = '#000';
                
                showNotification('Rain Effect dimatikan.', 'info');
                hideEffectToggle();
            }
        }

        // Create rain drops
        function createRainDrops() {
            const rainContainer = document.getElementById('rainContainer');
            if (!rainContainer || !rainEffectActive) return;
            
            rainContainer.innerHTML = '';
            
            for (let i = 0; i < 50; i++) {
                const drop = document.createElement('div');
                drop.className = 'rain-drop';
                drop.style.left = Math.random() * 100 + '%';
                drop.style.animationDelay = Math.random() * 2 + 's';
                drop.style.animationDuration = (0.5 + Math.random() * 0.5) + 's';
                rainContainer.appendChild(drop);
            }
        }

        // Toggle starfall effect
        function toggleStarfallEffect() {
            starfallEffectActive = !starfallEffectActive;
            const starfallContainer = document.getElementById('starfallContainer');
            const effectToggle = document.getElementById('effectToggle');
            const effectText = document.getElementById('effectText');
            
            if (starfallEffectActive) {
                // Disable other effect
                if (rainEffectActive) {
                    toggleRainEffect();
                }
                
                starfallContainer.style.display = 'block';
                effectText.textContent = 'Matikan Starfall Effect';
                createStars();
                effectToggle.style.background = 'var(--gradient-purple)';
                effectToggle.style.color = '#fff';
                
                showNotification('Starfall Effect diaktifkan!', 'success');
            } else {
                starfallContainer.style.display = 'none';
                effectText.textContent = 'Aktifkan Starfall Effect';
                effectToggle.style.background = 'var(--gradient-gold)';
                effectToggle.style.color = '#000';
                
                showNotification('Starfall Effect dimatikan.', 'info');
                hideEffectToggle();
            }
        }

        // Create stars
        function createStars() {
            const starfallContainer = document.getElementById('starfallContainer');
            if (!starfallContainer || !starfallEffectActive) return;
            
            starfallContainer.innerHTML = '';
            
            for (let i = 0; i < 30; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.animationDelay = Math.random() * 3 + 's';
                star.style.animationDuration = (1 + Math.random() * 2) + 's';
                star.style.width = star.style.height = (2 + Math.random() * 3) + 'px';
                star.style.background = '#fff';
                star.style.boxShadow = '0 0 5px #fff';
                starfallContainer.appendChild(star);
            }
        }

        // ============================================
        // UTILITY FUNCTIONS
        // ============================================

        // Show loading
        function showLoading(text = 'Loading...') {
            const loadingOverlay = document.getElementById('loadingOverlay');
            const loadingText = document.getElementById('loadingText');
            
            loadingText.textContent = text;
            loadingOverlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        // Hide loading
        function hideLoading() {
            const loadingOverlay = document.getElementById('loadingOverlay');
            loadingOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // Show notification
        function showNotification(message, type = 'info') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            
            if (type === 'success') {
                notification.style.background = 'var(--gradient-gold)';
                notification.style.color = '#000';
            } else if (type === 'error') {
                notification.style.background = 'var(--gradient-danger)';
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

        // Cleanup unused images
        function cleanupUnusedImages() {
            const usedImageKeys = new Set();
            
            // Collect used image keys
            if (appData.user.profileImageKey) {
                usedImageKeys.add(appData.user.profileImageKey);
            }
            
            appData.pages.work.items.forEach(item => {
                if (item.imageKey) {
                    usedImageKeys.add(item.imageKey);
                }
            });
            
            appData.pages.achievements.items.forEach(item => {
                if (item.imageKey) {
                    usedImageKeys.add(item.imageKey);
                }
            });
            
            // Remove unused images
            const allKeys = Object.keys(localStorage);
            allKeys.forEach(key => {
                if (key.startsWith('work_') || key.startsWith('achievement_') || key.startsWith('profile_')) {
                    if (!usedImageKeys.has(key)) {
                        localStorage.removeItem(key);
                    }
                }
            });
        }
    </script>
</body>
</html>
