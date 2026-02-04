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
            position: relative;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 10% 20%, rgba(255, 215, 0, 0.03) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(0, 255, 255, 0.03) 0%, transparent 20%),
                radial-gradient(circle at 50% 50%, rgba(255, 255, 255, 0.01) 0%, transparent 30%);
            z-index: -1;
        }

        /* ===== SIDEBAR ELEGAN ===== */
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
            overflow-y: auto;
            transition: var(--transition);
            border-right: 1px solid rgba(255, 215, 0, 0.1);
        }

        .sidebar-header {
            padding: 40px 30px 30px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            overflow: hidden;
        }

        .sidebar-header::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 10%;
            width: 80%;
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--primary), transparent);
        }

        .profile-section {
            display: flex;
            align-items: center;
            gap: 20px;
            margin-bottom: 30px;
            position: relative;
            z-index: 2;
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
            flex-shrink: 0;
            box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);
            border: 3px solid rgba(255, 215, 0, 0.5);
            transition: var(--transition);
        }

        .profile-img:hover {
            transform: scale(1.05) rotate(5deg);
            box-shadow: 0 15px 30px rgba(255, 215, 0, 0.4);
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
            opacity: 0.9;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        /* Menu Navigasi Sidebar */
        .nav-menu {
            list-style: none;
            padding: 30px 0;
            flex-grow: 1;
            position: relative;
            z-index: 2;
        }

        .nav-menu li {
            margin-bottom: 5px;
            position: relative;
        }

        .nav-menu li::before {
            content: '';
            position: absolute;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 3px;
            height: 0;
            background: var(--gradient-gold);
            transition: var(--transition);
            border-radius: 0 3px 3px 0;
        }

        .nav-menu li:hover::before {
            height: 70%;
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
            position: relative;
            overflow: hidden;
        }

        .nav-menu a::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 0;
            height: 100%;
            background: linear-gradient(90deg, rgba(255, 215, 0, 0.1), transparent);
            transition: width 0.3s ease;
        }

        .nav-menu a:hover::before {
            width: 100%;
        }

        .nav-menu a:hover {
            color: var(--light);
            transform: translateX(5px);
        }

        .nav-menu a.active {
            color: var(--primary);
            background: linear-gradient(90deg, rgba(255, 215, 0, 0.1), transparent);
        }

        .nav-menu a.active i {
            color: var(--primary);
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
        }

        .nav-menu a i {
            width: 24px;
            margin-right: 15px;
            text-align: center;
            font-size: 1.2rem;
            transition: var(--transition);
        }

        /* Admin Panel di Sidebar */
        .admin-section {
            padding: 25px 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            position: relative;
            z-index: 2;
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
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .admin-toggle:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 215, 0, 0.2);
            border-color: var(--primary);
        }

        .admin-panel {
            background: linear-gradient(135deg, #1a1a1a 0%, #252525 100%);
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 25px;
            margin-top: 20px;
            display: none;
            z-index: 101;
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

        .admin-panel h3 {
            margin-bottom: 20px;
            color: var(--primary);
            font-size: 1.1rem;
            font-weight: 600;
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
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.3);
        }

        .admin-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.4);
        }

        .admin-btn.secondary {
            background: linear-gradient(135deg, #2a2a2a 0%, #3a3a3a 100%);
            color: var(--light);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .admin-btn.danger {
            background: linear-gradient(135deg, #ff4757 0%, #ff6b81 100%);
            box-shadow: 0 8px 20px rgba(255, 71, 87, 0.3);
        }

        .sidebar-footer {
            padding: 25px 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            color: var(--gray);
            font-size: 0.85rem;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        /* ===== KONTEN UTAMA DENGAN SCROLL ===== */
        .main-content {
            flex: 1;
            margin-left: var(--sidebar-width);
            min-height: 100vh;
            padding: 0;
            overflow-y: auto;
            position: relative;
            background: linear-gradient(135deg, rgba(10, 10, 10, 0.95) 0%, rgba(26, 26, 26, 0.98) 100%);
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
        }

        .page-title h2 {
            font-size: 2.2rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            font-weight: 800;
            letter-spacing: -0.5px;
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

        .edit-status i {
            margin-right: 8px;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        /* Body Konten dengan Scroll */
        .content-body {
            padding: 50px;
            min-height: calc(100vh - 120px);
            position: relative;
        }

        /* Page Container */
        .page {
            display: none;
            animation: fadeInUp 0.6s ease;
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

        /* ===== HOME PAGE - BLACK & GOLD DESIGN ===== */
        .hero {
            padding: 60px;
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            margin-bottom: 50px;
            text-align: center;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: var(--box-shadow);
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(255, 215, 0, 0.1) 0%, transparent 70%);
            z-index: 0;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero-badge {
            display: inline-block;
            background: var(--gradient-gold);
            color: #000;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: 700;
            margin-bottom: 30px;
            font-size: 1rem;
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.3);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .hero h1 {
            font-size: 3.5rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 20px;
            font-weight: 800;
            letter-spacing: -1px;
            line-height: 1.2;
            text-shadow: 0 10px 30px rgba(255, 215, 0, 0.2);
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--gray);
            max-width: 800px;
            margin: 0 auto 40px;
            line-height: 1.7;
            font-weight: 400;
        }

        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            padding: 40px;
            border-radius: var(--border-radius);
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
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

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 25px 50px rgba(255, 215, 0, 0.1);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
            line-height: 1;
        }

        .stat-label {
            color: var(--gray);
            font-size: 1rem;
            font-weight: 500;
            max-width: 200px;
            margin: 0 auto;
        }

        /* ===== ABOUT PAGE ===== */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            margin-bottom: 50px;
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

        .skill-category {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 35px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-gold);
            opacity: 0.02;
            z-index: 0;
        }

        .skill-category h3 {
            font-size: 1.4rem;
            margin-bottom: 25px;
            color: var(--primary);
            padding-bottom: 15px;
            border-bottom: 2px solid rgba(255, 215, 0, 0.1);
            font-weight: 700;
            position: relative;
            z-index: 1;
        }

        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            position: relative;
            z-index: 1;
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
            background: linear-gradient(135deg, rgba(255, 215, 0, 0.15) 0%, rgba(255, 215, 0, 0.1) 100%);
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.15);
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
            box-shadow: 0 25px 50px rgba(255, 215, 0, 0.1);
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
        }

        .experience-content li::before {
            content: '▶';
            color: var(--primary);
            font-weight: bold;
            position: absolute;
            left: -20px;
            font-size: 0.8rem;
        }

        /* ===== ACHIEVEMENTS PAGE ===== */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(380px, 1fr));
            gap: 35px;
            margin-top: 30px;
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
            box-shadow: 0 30px 60px rgba(255, 215, 0, 0.1);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .achievement-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-gold);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .achievement-card:hover::before {
            opacity: 0.03;
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
            position: relative;
            border: 2px dashed rgba(255, 215, 0, 0.2);
        }

        .achievement-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: none;
        }

        .achievement-image-placeholder {
            font-size: 4rem;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .achievement-card h3 {
            font-size: 1.4rem;
            margin-bottom: 10px;
            color: var(--primary);
            font-weight: 700;
            position: relative;
            z-index: 1;
        }

        .achievement-card .date {
            color: var(--secondary);
            font-weight: 600;
            margin-bottom: 20px;
            font-size: 1rem;
            position: relative;
            z-index: 1;
        }

        .achievement-card p {
            color: var(--gray);
            line-height: 1.7;
            position: relative;
            z-index: 1;
        }

        .upload-btn {
            position: absolute;
            bottom: 20px;
            right: 20px;
            background: var(--gradient-gold);
            color: #000;
            border: none;
            border-radius: 10px;
            padding: 10px 18px;
            font-size: 0.9rem;
            cursor: pointer;
            display: none;
            z-index: 10;
            transition: var(--transition);
            font-weight: 700;
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.3);
        }

        .upload-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.4);
        }

        /* ===== PROJECTS PAGE ===== */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(550px, 1fr));
            gap: 35px;
            margin-top: 30px;
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
            box-shadow: 0 30px 60px rgba(255, 215, 0, 0.1);
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

        .stat-value:not(.improvement):not(.reduction) {
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-label {
            font-size: 0.9rem;
            color: var(--gray);
            font-weight: 500;
        }

        /* ===== DASHBOARD PAGE ===== */
        .dashboard-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .dashboard-card {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 35px;
            text-align: center;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .dashboard-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--gradient-gold);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .dashboard-card:hover::before {
            opacity: 0.03;
        }

        .dashboard-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 25px 50px rgba(255, 215, 0, 0.1);
            border-color: rgba(255, 215, 0, 0.3);
        }

        .dashboard-number {
            font-size: 3rem;
            font-weight: 800;
            background: var(--gradient-gold);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            line-height: 1;
            position: relative;
            z-index: 1;
        }

        .dashboard-label {
            color: var(--gray);
            font-weight: 500;
            font-size: 1rem;
            position: relative;
            z-index: 1;
        }

        .dashboard-chart {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            padding: 40px;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.3);
            margin-bottom: 40px;
        }

        .dashboard-chart h3 {
            margin-bottom: 30px;
            color: var(--primary);
            font-size: 1.5rem;
            font-weight: 700;
        }

        /* ===== CHATROOM PAGE ===== */
        .chatroom-container {
            background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%);
            border-radius: var(--border-radius);
            overflow: hidden;
            border: 1px solid rgba(255, 215, 0, 0.1);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5);
            max-width: 1000px;
            margin: 0 auto;
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

        .chatroom-header p {
            opacity: 0.8;
            font-size: 1.1rem;
        }

        .chatroom-messages {
            padding: 35px;
            height: 450px;
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
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.1);
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

        .message.user .message-info {
            opacity: 0.9;
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
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.3);
        }

        .chatroom-input button:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.4);
        }

        /* ===== CONTACT PAGE ===== */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
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
            box-shadow: 0 25px 50px rgba(255, 215, 0, 0.1);
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

        .form-group textarea {
            height: 180px;
            resize: vertical;
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
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.4);
        }

        .submit-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .submit-btn:hover::before {
            left: 100%;
        }

        /* ===== EDIT MODE STYLES ===== */
        .edit-mode .editable {
            position: relative;
            border: 2px dashed rgba(255, 215, 0, 0.3);
            padding: 15px;
            margin: 8px 0;
            border-radius: 10px;
            transition: var(--transition);
            background: rgba(255, 215, 0, 0.03);
        }

        .edit-mode .editable:hover {
            background: rgba(255, 215, 0, 0.08);
            border-color: var(--primary);
            box-shadow: 0 5px 20px rgba(255, 215, 0, 0.1);
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
            box-shadow: 0 4px 15px rgba(255, 215, 0, 0.3);
        }

        .edit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 215, 0, 0.4);
        }

        .edit-mode .edit-btn {
            display: block;
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
            box-shadow: 0 8px 20px rgba(255, 215, 0, 0.3);
        }

        .add-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.4);
        }

        .edit-mode .add-btn {
            display: inline-block;
        }

        .edit-mode .achievement-card .upload-btn {
            display: block;
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
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        .modal-btn.primary {
            background: var(--gradient-gold);
            color: #000;
        }

        .modal-btn.primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.4);
        }

        .modal-btn.secondary {
            background: linear-gradient(135deg, #2a2a2a 0%, #3a3a3a 100%);
            color: var(--light);
            border: 1px solid rgba(255, 215, 0, 0.2);
        }

        .modal-btn.secondary:hover {
            transform: translateY(-3px);
            box-shadow: 0 12px 25px rgba(255, 215, 0, 0.2);
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
            z-index: 1003;
            transition: var(--transition);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
        }

        .mobile-menu-toggle:hover {
            transform: scale(1.1);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.4);
        }

        /* ===== CUSTOM SCROLLBAR ===== */
        .main-content::-webkit-scrollbar {
            width: 8px;
        }

        .main-content::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
        }

        .main-content::-webkit-scrollbar-thumb {
            background: var(--gradient-gold);
            border-radius: 4px;
        }

        .main-content::-webkit-scrollbar-thumb:hover {
            background: var(--primary);
        }

        .chatroom-messages::-webkit-scrollbar {
            width: 6px;
        }

        .chatroom-messages::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
        }

        .chatroom-messages::-webkit-scrollbar-thumb {
            background: var(--gradient-gold);
            border-radius: 3px;
        }

        /* ===== RESPONSIVE STYLES ===== */
        
        /* Tablet (768px - 1024px) */
        @media (max-width: 1024px) {
            .sidebar {
                width: 250px;
            }
            
            .main-content {
                margin-left: 250px;
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
            
            .hero {
                padding: 40px;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
        }

        /* Mobile (≤ 768px) */
        @media (max-width: 768px) {
            .sidebar {
                width: 100%;
                max-width: 320px;
                transform: translateX(-100%);
                transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            }
            
            .sidebar.active {
                transform: translateX(0);
                box-shadow: 10px 0 50px rgba(0, 0, 0, 0.8);
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
            
            .hero {
                padding: 30px 20px;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .achievements-grid {
                grid-template-columns: 1fr;
            }
            
            .about-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .stats-grid,
            .dashboard-stats {
                grid-template-columns: repeat(2, 1fr);
                gap: 20px;
            }
            
            .stat-card,
            .dashboard-card {
                padding: 25px;
            }
            
            .stat-number {
                font-size: 2.5rem;
            }
            
            .project-stats {
                flex-direction: column;
                gap: 20px;
            }
            
            .contact-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .contact-info {
                grid-template-columns: 1fr;
            }
            
            .chatroom-container {
                max-width: 100%;
            }
            
            .chatroom-messages {
                height: 350px;
                padding: 20px;
            }
            
            .message {
                max-width: 85%;
            }
            
            .chatroom-input {
                padding: 20px;
                flex-direction: column;
            }
            
            .modal-content {
                padding: 25px;
                width: 95%;
            }
            
            .modal-buttons {
                flex-direction: column;
            }
        }

        /* Mobile Small (≤ 480px) */
        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .stats-grid,
            .dashboard-stats {
                grid-template-columns: 1fr;
            }
            
            .achievement-image-container {
                height: 200px;
            }
            
            .project-card {
                padding: 25px;
            }
            
            .skill-category {
                padding: 25px;
            }
            
            .skill-item {
                font-size: 0.9rem;
                padding: 10px 18px;
            }
            
            .contact-card {
                padding: 25px;
            }
            
            .contact-icon {
                font-size: 2rem;
            }
            
            .mobile-menu-toggle {
                top: 20px;
                right: 20px;
                padding: 12px;
            }
            
            .notification {
                bottom: 20px;
                right: 20px;
                left: 20px;
                max-width: none;
            }
        }

        /* Print Styles */
        @media print {
            .sidebar,
            .mobile-menu-toggle,
            .admin-section,
            .edit-btn,
            .add-btn,
            .upload-btn,
            .notification,
            .chatroom-input {
                display: none !important;
            }
            
            .main-content {
                margin-left: 0;
                width: 100%;
            }
            
            body {
                background: white !important;
                color: black !important;
            }
            
            .hero {
                background: none !important;
                border: 2px solid #ddd;
            }
            
            .stat-card,
            .dashboard-card,
            .achievement-card,
            .project-card,
            .skill-category,
            .contact-card,
            .contact-form {
                box-shadow: none !important;
                border: 1px solid #ddd !important;
                background: white !important;
            }
        }
    </style>
</head>
<body>
    <!-- Mobile Menu Toggle Button -->
    <button class="mobile-menu-toggle" id="mobileMenuToggle">
        <i class="fas fa-bars"></i>
    </button>
    
    <!-- SIDEBAR ELEGAN -->
    <aside class="sidebar" id="sidebar">
        <div class="sidebar-header">
            <div class="profile-section">
                <div class="profile-img">
                    <i class="fas fa-user-tie"></i>
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
                    <button class="admin-btn secondary" id="adminLogout">Logout</button>
                </div>
            </div>
        </div>
        
        <div class="sidebar-footer">
            <p>© 2026 Arya Savariansah. All rights reserved.</p>
        </div>
    </aside>
    
    <!-- KONTEN UTAMA DENGAN SCROLL -->
    <main class="main-content">
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
        
        <!-- Content Body - Pages (SCROLLABLE) -->
        <div class="content-body" id="contentBody">
            <!-- Home Page -->
            <div class="page active" id="homePage">
                <div class="hero">
                    <div class="hero-content">
                        <div class="hero-badge editable">
                            <span id="homeBadge">Lulusan SMK Teknik Permesinan</span>
                            <button class="edit-btn" data-edit="homeBadge">Edit</button>
                        </div>
                        <h1 class="editable" id="homeTitle">Arya Savariansah</h1>
                        <p class="editable" id="homeSubtitle">Spesialis Manufaktur & Produksi</p>
                        <button class="edit-btn" data-edit="homeTitle">Edit</button>
                        <button class="edit-btn" data-edit="homeSubtitle">Edit</button>
                        
                        <p class="editable" id="homeDescription">
                            Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. 
                            Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, 
                            hingga mechanical drafting.
                        </p>
                        <button class="edit-btn" data-edit="homeDescription">Edit</button>
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
                            </div>
                        </div>
                        <button class="add-btn" data-add="experience">+ Tambah Pengalaman</button>
                    </div>
                </div>
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
                    </div>
                </div>
                <button class="add-btn" data-add="project">+ Tambah Proyek</button>
            </div>
            
            <!-- Dashboard Page -->
            <div class="page" id="dashboardPage">
                <h2 style="margin-bottom: 40px; font-size: 2.5rem; background: var(--gradient-gold); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Dashboard Statistik</h2>
                
                <div class="dashboard-stats" id="dashboardStats">
                    <div class="dashboard-card editable" id="dashboardStat1">
                        <div class="dashboard-number">15%</div>
                        <div class="dashboard-label">Pengurangan Waktu Setup</div>
                        <button class="edit-btn" data-edit="dashboardStat1">Edit</button>
                    </div>
                    
                    <div class="dashboard-card editable" id="dashboardStat2">
                        <div class="dashboard-number">60%</div>
                        <div class="dashboard-label">Penurunan Reject Material</div>
                        <button class="edit-btn" data-edit="dashboardStat2">Edit</button>
                    </div>
                    
                    <div class="dashboard-card editable" id="dashboardStat3">
                        <div class="dashboard-number">20%</div>
                        <div class="dashboard-label">Peningkatan Efisiensi</div>
                        <button class="edit-btn" data-edit="dashboardStat3">Edit</button>
                    </div>
                    
                    <div class="dashboard-card editable" id="dashboardStat4">
                        <div class="dashboard-number">67%</div>
                        <div class="dashboard-label">Pengurangan Lead Time</div>
                        <button class="edit-btn" data-edit="dashboardStat4">Edit</button>
                    </div>
                    
                    <div class="dashboard-card editable" id="dashboardStat5">
                        <div class="dashboard-number">90%</div>
                        <div class="dashboard-label">Kesesuaian Dokumen (KPH)</div>
                        <button class="edit-btn" data-edit="dashboardStat5">Edit</button>
                    </div>
                </div>
                
                <div class="dashboard-chart editable" id="dashboardChart">
                    <h3>Grafik Produktivitas</h3>
                    <div style="height: 350px; background: linear-gradient(135deg, rgba(30, 30, 30, 0.8) 0%, rgba(26, 26, 26, 0.6) 100%); border-radius: 12px; display: flex; align-items: flex-end; padding: 25px; border: 1px solid rgba(255, 215, 0, 0.1);">
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 220px; width: 50px; background: var(--gradient-gold); margin: 0 15px; border-radius: 8px 8px 0 0; box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Jan</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 180px; width: 50px; background: var(--gradient-gold); margin: 0 15px; border-radius: 8px 8px 0 0; box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Feb</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 250px; width: 50px; background: var(--gradient-gold); margin: 0 15px; border-radius: 8px 8px 0 0; box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Mar</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 280px; width: 50px; background: var(--gradient-gold); margin: 0 15px; border-radius: 8px 8px 0 0; box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Apr</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 320px; width: 50px; background: var(--gradient-gold); margin: 0 15px; border-radius: 8px 8px 0 0; box-shadow: 0 10px 20px rgba(255, 215, 0, 0.3);"></div>
                            <div style="margin-top: 15px; color: var(--primary); font-weight: 600;">Mei</div>
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
                        
                        <div class="message">
                            <div class="message-info">
                                <span class="message-user">Rufa Resto Ramadhani</span>
                                <span class="message-time">01/04/2025, 16:37</span>
                            </div>
                            <div class="message-content">
                                Test - checking out the chat functionality
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
    
    <!-- Modal untuk Upload Foto Achievement -->
    <div class="modal" id="imageUploadModal">
        <div class="modal-content">
            <h3 class="modal-title" id="modalTitle">Upload Foto Achievement</h3>
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
    
    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <script>
        // Data aplikasi - DENGAN FITUR FOTO UNTUK ACHIEVEMENTS
        const appData = {
            user: {
                name: "Arya Savariansah",
                title: "Spesialis Manufaktur",
                email: "aryasavarinasah@gmail.com",
                phone: "089520336532",
                location: "Kosambi, Indonesia",
                linkedin: "linkedin.com/in/arya-savariansah"
            },
            pages: {
                home: {
                    title: "Home",
                    description: "Selamat datang di portfolio Arya Savariansah",
                    badge: "Lulusan SMK Teknik Permesinan",
                    mainTitle: "Arya Savariansah",
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
                achievements: {
                    title: "Achievements",
                    description: "Pencapaian dan sertifikat profesional",
                    items: [
                        {
                            id: "achievement1",
                            title: "Health, Safety, Environment and Quality (HSEQ)",
                            date: "Sertifikasi Profesional",
                            description: "Sertifikasi profesional dalam bidang kesehatan, keselamatan, lingkungan, dan kualitas untuk industri manufaktur",
                            image: null
                        },
                        {
                            id: "achievement2",
                            title: "Introduction to Information Security Course",
                            date: "Sertifikasi Keamanan Informasi",
                            description: "Sertifikasi dasar keamanan informasi untuk memahami prinsip-prinsip keamanan data dalam sistem produksi",
                            image: null
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
                    stats: [
                        { id: "dashboardStat1", number: "15%", label: "Pengurangan Waktu Setup" },
                        { id: "dashboardStat2", number: "60%", label: "Penurunan Reject Material" },
                        { id: "dashboardStat3", number: "20%", label: "Peningkatan Efisiensi" },
                        { id: "dashboardStat4", number: "67%", label: "Pengurangan Lead Time" },
                        { id: "dashboardStat5", number: "90%", label: "Kesesuaian Dokumen (KPH)" }
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
        let currentAchievementEditing = null;

        // DOM Ready
        document.addEventListener('DOMContentLoaded', function() {
            // Load data dari localStorage jika ada
            loadFromLocalStorage();
            
            // Setup navigation
            setupNavigation();
            
            // Setup admin panel
            setupAdminPanel();
            
            // Setup chat functionality
            setupChat();
            
            // Setup contact form
            setupContactForm();
            
            // Setup mobile menu toggle
            setupMobileMenu();
            
            // Setup image upload modal
            setupImageUploadModal();
            
            // Setup responsive behavior
            setupResponsiveBehavior();
            
            // Render initial page
            renderPage(currentPage);
            
            // Update UI based on admin status
            updateAdminUI();
            
            // Tambah animasi saat load
            setTimeout(() => {
                document.body.style.opacity = 1;
                document.body.style.transform = 'translateY(0)';
            }, 100);
        });

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
                    
                    // Get page id
                    const pageId = this.getAttribute('data-page');
                    
                    // Update active nav link
                    navLinks.forEach(l => l.classList.remove('active'));
                    this.classList.add('active');
                    
                    // Change page
                    changePage(pageId);
                    
                    // Di mobile, tutup sidebar setelah memilih halaman
                    if (window.innerWidth <= 768) {
                        document.getElementById('sidebar').classList.remove('active');
                        document.getElementById('mobileMenuToggle').innerHTML = '<i class="fas fa-bars"></i>';
                    }
                });
            });
        }

        // Setup mobile menu toggle
        function setupMobileMenu() {
            const mobileMenuToggle = document.getElementById('mobileMenuToggle');
            const sidebar = document.getElementById('sidebar');
            
            if (mobileMenuToggle && sidebar) {
                mobileMenuToggle.addEventListener('click', function() {
                    sidebar.classList.toggle('active');
                    
                    // Ubah ikon toggle
                    if (sidebar.classList.contains('active')) {
                        this.innerHTML = '<i class="fas fa-times"></i>';
                        this.style.transform = 'rotate(90deg)';
                    } else {
                        this.innerHTML = '<i class="fas fa-bars"></i>';
                        this.style.transform = 'rotate(0deg)';
                    }
                });
                
                // Tutup sidebar saat klik di luar pada mobile
                document.addEventListener('click', function(e) {
                    if (window.innerWidth <= 768) {
                        if (!sidebar.contains(e.target) && 
                            !mobileMenuToggle.contains(e.target) &&
                            sidebar.classList.contains('active')) {
                            sidebar.classList.remove('active');
                            mobileMenuToggle.innerHTML = '<i class="fas fa-bars"></i>';
                            mobileMenuToggle.style.transform = 'rotate(0deg)';
                        }
                    }
                });
            }
        }

        // Setup responsive behavior
        function setupResponsiveBehavior() {
            window.addEventListener('resize', function() {
                if (window.innerWidth > 768) {
                    document.getElementById('sidebar').classList.add('active');
                    document.getElementById('mobileMenuToggle').style.display = 'none';
                } else {
                    document.getElementById('sidebar').classList.remove('active');
                    document.getElementById('mobileMenuToggle').style.display = 'block';
                    document.getElementById('mobileMenuToggle').innerHTML = '<i class="fas fa-bars"></i>';
                    document.getElementById('mobileMenuToggle').style.transform = 'rotate(0deg)';
                }
            });
            
            // Initial check
            if (window.innerWidth <= 768) {
                document.getElementById('sidebar').classList.remove('active');
                document.getElementById('mobileMenuToggle').style.display = 'block';
            } else {
                document.getElementById('sidebar').classList.add('active');
                document.getElementById('mobileMenuToggle').style.display = 'none';
            }
        }

        // Setup image upload modal
        function setupImageUploadModal() {
            const imageInput = document.getElementById('imageInput');
            const imagePreview = document.getElementById('imagePreview');
            const previewImage = document.getElementById('previewImage');
            const saveImageBtn = document.getElementById('saveImageBtn');
            const cancelImageBtn = document.getElementById('cancelImageBtn');
            const removeImageBtn = document.getElementById('removeImageBtn');
            const modal = document.getElementById('imageUploadModal');
            
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
                    
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        previewImage.src = event.target.result;
                        imagePreview.style.display = 'block';
                        removeImageBtn.style.display = 'inline-block';
                    };
                    reader.readAsDataURL(file);
                }
            });
            
            saveImageBtn.addEventListener('click', function() {
                if (currentAchievementEditing && previewImage.src) {
                    const achievement = appData.pages.achievements.items.find(a => a.id === currentAchievementEditing);
                    if (achievement) {
                        achievement.image = previewImage.src;
                        renderAchievementsPage();
                        showNotification('Foto berhasil diupload!', 'success');
                        modal.classList.remove('active');
                        
                        // Reset modal
                        imageInput.value = '';
                        imagePreview.style.display = 'none';
                        previewImage.src = '';
                        removeImageBtn.style.display = 'none';
                        currentAchievementEditing = null;
                    }
                }
            });
            
            cancelImageBtn.addEventListener('click', function() {
                modal.classList.remove('active');
                
                // Reset modal
                imageInput.value = '';
                imagePreview.style.display = 'none';
                previewImage.src = '';
                removeImageBtn.style.display = 'none';
                currentAchievementEditing = null;
            });
            
            removeImageBtn.addEventListener('click', function() {
                if (currentAchievementEditing) {
                    const achievement = appData.pages.achievements.items.find(a => a.id === currentAchievementEditing);
                    if (achievement) {
                        achievement.image = null;
                        renderAchievementsPage();
                        showNotification('Foto berhasil dihapus!', 'success');
                        modal.classList.remove('active');
                        
                        // Reset modal
                        imageInput.value = '';
                        imagePreview.style.display = 'none';
                        previewImage.src = '';
                        removeImageBtn.style.display = 'none';
                        currentAchievementEditing = null;
                    }
                }
            });
            
            modal.addEventListener('click', function(e) {
                if (e.target === modal) {
                    modal.classList.remove('active');
                    
                    // Reset modal
                    imageInput.value = '';
                    imagePreview.style.display = 'none';
                    previewImage.src = '';
                    removeImageBtn.style.display = 'none';
                    currentAchievementEditing = null;
                }
            });
        }

        // Change page
        function changePage(pageId) {
            // Animasi fade out
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
                        <div class="achievement-image-container">
                            <img src="${item.image}" alt="${item.title}" class="achievement-image">
                            <button class="upload-btn" data-upload="${item.id}">Ganti Foto</button>
                        </div>
                    `;
                } else {
                    imageHTML = `
                        <div class="achievement-image-container">
                            <div class="achievement-image-placeholder">
                                <i class="fas fa-trophy"></i>
                            </div>
                            <button class="upload-btn" data-upload="${item.id}">Upload Foto</button>
                        </div>
                    `;
                }
                
                achievementElement.innerHTML = `
                    ${imageHTML}
                    <h3>${item.title}</h3>
                    <div class="date">${item.date}</div>
                    <p>${item.description}</p>
                    <button class="edit-btn" data-edit="${item.id}">Edit</button>
                `;
                
                container.appendChild(achievementElement);
            });
            
            if (isEditMode) {
                document.querySelectorAll('.upload-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const achievementId = this.getAttribute('data-upload');
                        openImageUploadModal(achievementId);
                    });
                });
                
                document.querySelectorAll('.edit-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const elementId = this.getAttribute('data-edit');
                        editAchievement(elementId);
                    });
                });
                
                const addButton = document.createElement('button');
                addButton.className = 'add-btn';
                addButton.setAttribute('data-add', 'achievement');
                addButton.textContent = '+ Tambah Pencapaian';
                addButton.addEventListener('click', addAchievement);
                container.appendChild(addButton);
            }
        }

        // Open image upload modal
        function openImageUploadModal(achievementId) {
            currentAchievementEditing = achievementId;
            const modal = document.getElementById('imageUploadModal');
            const modalTitle = document.getElementById('modalTitle');
            const removeImageBtn = document.getElementById('removeImageBtn');
            
            const achievement = appData.pages.achievements.items.find(a => a.id === achievementId);
            if (achievement) {
                modalTitle.textContent = `Upload Foto untuk: ${achievement.title}`;
                
                if (achievement.image) {
                    removeImageBtn.style.display = 'inline-block';
                } else {
                    removeImageBtn.style.display = 'none';
                }
            }
            
            modal.classList.add('active');
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
                `;
                
                container.appendChild(projectElement);
            });
            
            if (isEditMode) {
                document.querySelectorAll('.edit-btn').forEach(btn => {
                    btn.addEventListener('click', function() {
                        const elementId = this.getAttribute('data-edit');
                        editProject(elementId);
                    });
                });
                
                const addButton = document.createElement('button');
                addButton.className = 'add-btn';
                addButton.setAttribute('data-add', 'project');
                addButton.textContent = '+ Tambah Proyek';
                addButton.addEventListener('click', addProject);
                container.appendChild(addButton);
            }
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

        // Add project
        function addProject() {
            const newTitle = prompt('Masukkan judul proyek baru:');
            if (!newTitle) return;
            
            const newDescription = prompt('Masukkan deskripsi:');
            if (!newDescription) return;
            
            const newId = 'project' + (appData.pages.projects.items.length + 1);
            const newProject = {
                id: newId,
                title: newTitle,
                description: newDescription,
                stats: [
                    { value: "0%", label: "Sebelum" },
                    { value: "↓ 0%", label: "Perubahan", type: "improvement" },
                    { value: "0%", label: "Sesudah" }
                ]
            };
            
            appData.pages.projects.items.push(newProject);
            renderProjectsPage();
            showNotification('Proyek berhasil ditambahkan!', 'success');
        }

        // Render dashboard page
        function renderDashboardPage() {
            const pageData = appData.pages.dashboard;
            
            pageData.stats.forEach((stat) => {
                const statElement = document.getElementById(stat.id);
                if (statElement) {
                    const numberElement = statElement.querySelector('.dashboard-number');
                    const labelElement = statElement.querySelector('.dashboard-label');
                    
                    if (numberElement) numberElement.textContent = stat.number;
                    if (labelElement) labelElement.textContent = stat.label;
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
                document.body.classList.remove('edit-mode');
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
                document.body.classList.toggle('edit-mode', isEditMode);
                document.getElementById('editStatus').style.display = isEditMode ? 'block' : 'none';
                toggleEditMode.textContent = isEditMode ? 'Nonaktifkan Edit Mode' : 'Aktifkan Edit Mode';
                
                if (isEditMode) {
                    setupEditMode();
                } else {
                    if (currentPage === 'achievements') {
                        renderAchievementsPage();
                    }
                    if (currentPage === 'projects') {
                        renderProjectsPage();
                    }
                }
            });
            
            saveAllData.addEventListener('click', function() {
                if (!isAdminLoggedIn) {
                    showNotification('Silakan login sebagai admin terlebih dahulu', 'error');
                    return;
                }
                
                saveToLocalStorage();
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
                                   element.id.startsWith('stat')) {
                            editStat(elementId);
                        } else if (element.classList.contains('contact-card')) {
                            editContact(elementId);
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

        // Edit stat
        function editStat(statId) {
            const element = document.getElementById(statId);
            if (!element) return;
            
            let numberElement, labelElement;
            
            if (element.classList.contains('dashboard-card')) {
                numberElement = element.querySelector('.dashboard-number');
                labelElement = element.querySelector('.dashboard-label');
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
                    
                    alert(`Thank you ${name}! Your message has been sent successfully. I'll get back to you at ${email} soon.`);
                    
                    contactForm.reset();
                });
            }
        }

        // Update admin UI
        function updateAdminUI() {
            const adminToggle = document.getElementById('adminToggle');
            
            if (isAdminLoggedIn) {
                adminToggle.innerHTML = '<i class="fas fa-user-check"></i> Admin Mode';
                adminToggle.style.background = 'var(--gradient-gold)';
                adminToggle.style.color = '#000';
            } else {
                adminToggle.innerHTML = '<i class="fas fa-user-lock"></i> Login Admin';
                adminToggle.style.background = 'linear-gradient(135deg, #1e1e1e 0%, #2a2a2a 100%)';
                adminToggle.style.color = 'var(--primary)';
            }
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
