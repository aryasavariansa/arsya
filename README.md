<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arya Savariansah - Portfolio Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2d5aa0;
            --primary-dark: #1e3a6e;
            --secondary: #00a86b;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --gray: #6c757d;
            --light-gray: #e9ecef;
            --sidebar-width: 20%;
            --content-width: 80%;
            --border-radius: 10px;
            --box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            color: var(--dark);
            background-color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
            display: flex;
            min-height: 100vh;
        }

        /* Sidebar Navigation */
        .sidebar {
            width: var(--sidebar-width);
            background-color: var(--dark);
            color: white;
            position: fixed;
            height: 100vh;
            overflow-y: auto;
            padding: 2rem 0;
            z-index: 1000;
        }

        .sidebar-header {
            padding: 0 2rem 2rem;
            border-bottom: 1px solid #2d3748;
            margin-bottom: 2rem;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 1.5rem;
        }

        .logo h1 {
            font-size: 1.5rem;
            font-weight: 700;
            color: white;
        }

        .logo span {
            color: var(--secondary);
        }

        .profile-mini {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .profile-mini-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
        }

        .profile-mini-info h3 {
            font-size: 1rem;
            margin-bottom: 0.2rem;
        }

        .profile-mini-info p {
            font-size: 0.8rem;
            color: #adb5bd;
        }

        .nav-menu {
            list-style: none;
            padding: 0 1rem;
        }

        .nav-menu li {
            margin-bottom: 0.5rem;
        }

        .nav-menu li a {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem 1.5rem;
            color: #adb5bd;
            text-decoration: none;
            border-radius: 8px;
            transition: var(--transition);
        }

        .nav-menu li a:hover {
            background-color: #2d3748;
            color: white;
        }

        .nav-menu li a.active {
            background-color: var(--primary);
            color: white;
        }

        .nav-menu li a i {
            width: 20px;
            text-align: center;
        }

        .admin-section {
            margin-top: 3rem;
            padding: 0 2rem;
        }

        .admin-section h3 {
            font-size: 0.9rem;
            color: #adb5bd;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 1rem;
        }

        .admin-toggle {
            background-color: var(--secondary);
            color: white;
            border: none;
            width: 100%;
            padding: 0.8rem;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            font-weight: 500;
            transition: var(--transition);
        }

        .admin-toggle:hover {
            background-color: #00995c;
        }

        .admin-panel {
            position: absolute;
            bottom: 2rem;
            left: 2rem;
            right: 2rem;
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 1.5rem;
            display: none;
            z-index: 1001;
        }

        .admin-panel.active {
            display: block;
        }

        .admin-panel h3 {
            margin-bottom: 1rem;
            color: var(--dark);
        }

        .admin-input {
            width: 100%;
            padding: 0.8rem;
            margin-bottom: 1rem;
            border: 1px solid var(--light-gray);
            border-radius: 5px;
            font-family: 'Poppins', sans-serif;
        }

        .admin-btn {
            width: 100%;
            padding: 0.8rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 500;
            transition: var(--transition);
            margin-bottom: 0.5rem;
        }

        .admin-btn:hover {
            background-color: var(--primary-dark);
        }

        /* Main Content */
        .main-content {
            width: var(--content-width);
            margin-left: var(--sidebar-width);
            padding: 0;
            min-height: 100vh;
        }

        .content-header {
            background-color: white;
            padding: 1.5rem 2rem;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 999;
        }

        .page-title h2 {
            font-size: 1.8rem;
            color: var(--primary-dark);
        }

        .page-title p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .content-body {
            padding: 2rem;
            min-height: calc(100vh - 80px);
        }

        /* Page Styles */
        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        /* Home Page */
        .hero {
            padding: 3rem 0;
            background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%);
            border-radius: var(--border-radius);
            margin-bottom: 2rem;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            color: var(--primary-dark);
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--gray);
            max-width: 800px;
            margin: 0 auto 2rem;
        }

        .hero-badge {
            display: inline-block;
            background: rgba(45, 90, 160, 0.1);
            color: var(--primary);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            font-weight: 500;
            margin-bottom: 1.5rem;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin: 3rem 0;
        }

        .stat-card {
            background-color: white;
            padding: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            text-align: center;
            transition: var(--transition);
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* About Page */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .about-text p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            color: var(--gray);
            line-height: 1.8;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-category {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 1.5rem;
            box-shadow: var(--box-shadow);
        }

        .skill-category h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--primary-dark);
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--light-gray);
        }

        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .skill-item {
            background-color: var(--light-gray);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            font-size: 0.9rem;
        }

        /* Achievement Page */
        .achievements-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }

        .achievement-card {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 2rem;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            position: relative;
        }

        .achievement-card:hover {
            transform: translateY(-5px);
        }

        .achievement-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--primary-dark);
        }

        .achievement-card .date {
            color: var(--gray);
            font-weight: 500;
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        /* Project Page */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
        }

        .project-image {
            height: 200px;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: var(--primary);
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--primary-dark);
        }

        /* Dashboard Page */
        .dashboard-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .dashboard-card {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 2rem;
            text-align: center;
            box-shadow: var(--box-shadow);
        }

        .dashboard-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }

        .dashboard-label {
            color: var(--gray);
            font-weight: 500;
        }

        .dashboard-chart {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 2rem;
            box-shadow: var(--box-shadow);
            margin-bottom: 2rem;
        }

        /* Chatroom Page */
        .chatroom-container {
            background-color: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--box-shadow);
            max-width: 800px;
            margin: 0 auto;
        }

        .chatroom-header {
            background-color: var(--primary);
            color: white;
            padding: 1.5rem;
            text-align: center;
        }

        .chatroom-messages {
            padding: 2rem;
            height: 400px;
            overflow-y: auto;
        }

        .message {
            margin-bottom: 1.5rem;
            padding: 1rem;
            background-color: #f1f3f5;
            border-radius: 10px;
            max-width: 80%;
        }

        .message.user {
            margin-left: auto;
            background-color: var(--primary);
            color: white;
        }

        .message-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .message-content {
            font-size: 1rem;
        }

        .chatroom-input {
            padding: 1.5rem;
            background-color: #f8f9fa;
            display: flex;
            gap: 1rem;
        }

        .chatroom-input input {
            flex: 1;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 50px;
            font-family: 'Poppins', sans-serif;
        }

        .chatroom-input button {
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 50px;
            padding: 0.8rem 2rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
        }

        .chatroom-input button:hover {
            background-color: var(--primary-dark);
        }

        /* Contact Page */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }

        .contact-info {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
        }

        .contact-card {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 1.5rem;
            box-shadow: var(--box-shadow);
            text-align: center;
        }

        .contact-icon {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .contact-form {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 2rem;
            box-shadow: var(--box-shadow);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        .submit-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 50px;
            padding: 1rem 2.5rem;
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
            width: 100%;
        }

        .submit-btn:hover {
            background-color: var(--primary-dark);
        }

        /* Edit Mode */
        .edit-mode .editable {
            position: relative;
            border: 1px dashed #ccc;
            padding: 0.5rem;
            margin: 0.2rem 0;
        }

        .edit-mode .editable:hover {
            background-color: #f8f9fa;
        }

        .edit-btn {
            position: absolute;
            top: 5px;
            right: 5px;
            background-color: var(--secondary);
            color: white;
            border: none;
            border-radius: 3px;
            padding: 0.2rem 0.5rem;
            font-size: 0.8rem;
            cursor: pointer;
            display: none;
        }

        .edit-mode .edit-btn {
            display: block;
        }

        .add-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            padding: 0.5rem 1rem;
            margin: 1rem 0;
            cursor: pointer;
            display: none;
        }

        .edit-mode .add-btn {
            display: inline-block;
        }

        /* Notification */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--secondary);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            z-index: 1002;
            display: none;
            animation: slideIn 0.3s ease;
            max-width: 350px;
        }

        @keyframes slideIn {
            from {
                transform: translateX(100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        /* Responsive Styles */
        @media (max-width: 1200px) {
            :root {
                --sidebar-width: 25%;
                --content-width: 75%;
            }
        }

        @media (max-width: 992px) {
            :root {
                --sidebar-width: 30%;
                --content-width: 70%;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .contact-content {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            body {
                flex-direction: column;
            }
            
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
                padding: 1rem 0;
            }
            
            .main-content {
                width: 100%;
                margin-left: 0;
            }
            
            .nav-menu {
                display: flex;
                overflow-x: auto;
                padding: 0 1rem;
            }
            
            .nav-menu li {
                margin-bottom: 0;
                flex-shrink: 0;
            }
            
            .nav-menu li a {
                padding: 0.8rem 1rem;
            }
            
            .admin-section {
                display: none;
            }
            
            .profile-mini {
                justify-content: center;
                text-align: center;
            }
        }

        @media (max-width: 576px) {
            .content-body {
                padding: 1rem;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .stats-grid,
            .dashboard-stats {
                grid-template-columns: 1fr;
            }
            
            .projects-grid,
            .achievements-grid {
                grid-template-columns: 1fr;
            }
            
            .skill-category {
                padding: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Sidebar Navigation -->
    <aside class="sidebar">
        <div class="sidebar-header">
            <div class="logo">
                <h1>Arya<span>Savariansah</span></h1>
            </div>
            
            <div class="profile-mini">
                <div class="profile-mini-img">
                    <i class="fas fa-user-cog"></i>
                </div>
                <div class="profile-mini-info">
                    <h3>Arya Savariansah</h3>
                    <p>Spesialis Manufaktur</p>
                </div>
            </div>
        </div>
        
        <ul class="nav-menu">
            <li><a href="#home" class="nav-link active" data-page="home"><i class="fas fa-home"></i> Home</a></li>
            <li><a href="#about" class="nav-link" data-page="about"><i class="fas fa-user"></i> About Me</a></li>
            <li><a href="#achievements" class="nav-link" data-page="achievements"><i class="fas fa-trophy"></i> Achievements</a></li>
            <li><a href="#projects" class="nav-link" data-page="projects"><i class="fas fa-project-diagram"></i> Projects</a></li>
            <li><a href="#dashboard" class="nav-link" data-page="dashboard"><i class="fas fa-chart-line"></i> Dashboard</a></li>
            <li><a href="#chatroom" class="nav-link" data-page="chatroom"><i class="fas fa-comments"></i> Chat Room</a></li>
            <li><a href="#contact" class="nav-link" data-page="contact"><i class="fas fa-envelope"></i> Contact</a></li>
        </ul>
        
        <div class="admin-section">
            <h3>Admin Panel</h3>
            <button class="admin-toggle" id="adminToggle">
                <i class="fas fa-user-lock"></i> Login Admin
            </button>
        </div>
        
        <div class="admin-panel" id="adminPanel">
            <h3>Login Admin</h3>
            <input type="password" id="adminPassword" class="admin-input" placeholder="Password Admin">
            <button class="admin-btn" id="adminLogin">Login</button>
            <div id="adminControls" style="display: none;">
                <h3>Edit Mode</h3>
                <button class="admin-btn" id="toggleEditMode">Aktifkan Edit Mode</button>
                <button class="admin-btn" id="saveAllData">Simpan Semua Data</button>
                <button class="admin-btn admin-btn-secondary" id="adminLogout">Logout</button>
            </div>
        </div>
    </aside>
    
    <!-- Main Content Area -->
    <main class="main-content">
        <!-- Content Header -->
        <div class="content-header">
            <div class="page-title">
                <h2 id="currentPageTitle">Home</h2>
                <p id="currentPageDesc">Selamat datang di portfolio Arya Savariansah</p>
            </div>
            <div id="editStatus" style="color: var(--gray); font-size: 0.9rem; display: none;">
                <i class="fas fa-edit"></i> Edit Mode Aktif
            </div>
        </div>
        
        <!-- Content Body - Pages will be loaded here -->
        <div class="content-body" id="contentBody">
            <!-- Home Page -->
            <div class="page active" id="homePage">
                <div class="hero">
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
                <h2 style="margin-bottom: 2rem; color: var(--primary-dark);">Tentang Saya</h2>
                
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
                        <h3 style="margin-bottom: 1.5rem; color: var(--primary-dark);">Pengalaman Kerja</h3>
                        
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
                <h2 style="margin-bottom: 2rem; color: var(--primary-dark);">Pencapaian & Sertifikat</h2>
                
                <div class="achievements-grid" id="achievementsContainer">
                    <div class="achievement-card editable" id="achievement1">
                        <h3>Health, Safety, Environment and Quality (HSEQ)</h3>
                        <div class="date">Sertifikasi Profesional</div>
                        <p>Sertifikasi profesional dalam bidang kesehatan, keselamatan, lingkungan, dan kualitas untuk industri manufaktur</p>
                        <button class="edit-btn" data-edit="achievement1">Edit</button>
                    </div>
                    
                    <div class="achievement-card editable" id="achievement2">
                        <h3>Introduction to Information Security Course</h3>
                        <div class="date">Sertifikasi Keamanan Informasi</div>
                        <p>Sertifikasi dasar keamanan informasi untuk memahami prinsip-prinsip keamanan data dalam sistem produksi</p>
                        <button class="edit-btn" data-edit="achievement2">Edit</button>
                    </div>
                </div>
                <button class="add-btn" data-add="achievement">+ Tambah Pencapaian</button>
            </div>
            
            <!-- Projects Page -->
            <div class="page" id="projectsPage">
                <h2 style="margin-bottom: 2rem; color: var(--primary-dark);">Proyek & Portofolio</h2>
                
                <div class="projects-grid" id="projectsContainer">
                    <div class="project-card editable" id="project1">
                        <div class="project-image">
                            <i class="fas fa-drafting-compass"></i>
                        </div>
                        <div class="project-content">
                            <h3>Sistem Pendataan Molding</h3>
                            <p>Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi</p>
                        </div>
                        <button class="edit-btn" data-edit="project1">Edit</button>
                    </div>
                    
                    <div class="project-card editable" id="project2">
                        <div class="project-image">
                            <i class="fas fa-chart-line"></i>
                        </div>
                        <div class="project-content">
                            <h3>Optimasi Produksi WIP</h3>
                            <p>Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dengan monitoring Stock WIP dan planning item Produksi</p>
                        </div>
                        <button class="edit-btn" data-edit="project2">Edit</button>
                    </div>
                    
                    <div class="project-card editable" id="project3">
                        <div class="project-image">
                            <i class="fas fa-cogs"></i>
                        </div>
                        <div class="project-content">
                            <h3>Reduksi Reject Mesin Spiral</h3>
                            <p>Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)</p>
                        </div>
                        <button class="edit-btn" data-edit="project3">Edit</button>
                    </div>
                </div>
                <button class="add-btn" data-add="project">+ Tambah Proyek</button>
            </div>
            
            <!-- Dashboard Page -->
            <div class="page" id="dashboardPage">
                <h2 style="margin-bottom: 2rem; color: var(--primary-dark);">Dashboard Statistik</h2>
                
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
                    <h3 style="margin-bottom: 1.5rem; color: var(--primary-dark);">Grafik Produktivitas</h3>
                    <div style="height: 300px; background-color: #f8f9fa; border-radius: 8px; display: flex; align-items: flex-end; padding: 1rem;">
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 200px; width: 40px; background-color: var(--primary); margin: 0 0.5rem;"></div>
                            <div style="margin-top: 0.5rem;">Jan</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 180px; width: 40px; background-color: var(--primary); margin: 0 0.5rem;"></div>
                            <div style="margin-top: 0.5rem;">Feb</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 220px; width: 40px; background-color: var(--primary); margin: 0 0.5rem;"></div>
                            <div style="margin-top: 0.5rem;">Mar</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 250px; width: 40px; background-color: var(--primary); margin: 0 0.5rem;"></div>
                            <div style="margin-top: 0.5rem;">Apr</div>
                        </div>
                        <div style="flex: 1; display: flex; flex-direction: column; align-items: center;">
                            <div style="height: 300px; width: 40px; background-color: var(--primary); margin: 0 0.5rem;"></div>
                            <div style="margin-top: 0.5rem;">Mei</div>
                        </div>
                    </div>
                    <button class="edit-btn" data-edit="dashboardChart">Edit</button>
                </div>
            </div>
            
            <!-- Chatroom Page -->
            <div class="page" id="chatroomPage">
                <h2 style="margin-bottom: 2rem; color: var(--primary-dark); text-align: center;">Chat Room</h2>
                <p style="text-align: center; margin-bottom: 3rem; color: var(--gray); max-width: 800px; margin-left: auto; margin-right: auto;">
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
                <h2 style="margin-bottom: 2rem; color: var(--primary-dark);">Hubungi Saya</h2>
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
                        <h3 style="margin-bottom: 1.5rem; font-size: 1.5rem;">Kirim Pesan</h3>
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
    
    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <script>
        // Data aplikasi
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
                            description: "Sertifikasi profesional dalam bidang kesehatan, keselamatan, lingkungan, dan kualitas untuk industri manufaktur"
                        },
                        {
                            id: "achievement2",
                            title: "Introduction to Information Security Course",
                            date: "Sertifikasi Keamanan Informasi",
                            description: "Sertifikasi dasar keamanan informasi untuk memahami prinsip-prinsip keamanan data dalam sistem produksi"
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
                            icon: "fas fa-drafting-compass"
                        },
                        {
                            id: "project2",
                            title: "Optimasi Produksi WIP",
                            description: "Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dengan monitoring Stock WIP dan planning item Produksi",
                            icon: "fas fa-chart-line"
                        },
                        {
                            id: "project3",
                            title: "Reduksi Reject Mesin Spiral",
                            description: "Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)",
                            icon: "fas fa-cogs"
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
            
            // Render initial page
            renderPage(currentPage);
            
            // Update UI based on admin status
            updateAdminUI();
        });

        // Load data dari localStorage
        function loadFromLocalStorage() {
            const savedData = localStorage.getItem('portfolioData');
            if (savedData) {
                try {
                    const data = JSON.parse(savedData);
                    // Merge dengan data default
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
                });
            });
        }

        // Change page
        function changePage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Show selected page
            const pageElement = document.getElementById(pageId + 'Page');
            if (pageElement) {
                pageElement.classList.add('active');
                currentPage = pageId;
                
                // Update page title
                const pageData = appData.pages[pageId];
                if (pageData) {
                    document.getElementById('currentPageTitle').textContent = pageData.title;
                    document.getElementById('currentPageDesc').textContent = pageData.description;
                }
                
                // Render page content
                renderPage(pageId);
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
            
            // Update text elements
            document.getElementById('homeBadge').textContent = pageData.badge;
            document.getElementById('homeTitle').textContent = pageData.mainTitle;
            document.getElementById('homeSubtitle').textContent = pageData.subtitle;
            document.getElementById('homeDescription').textContent = pageData.descriptionText;
            
            // Update stats
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
            
            // Update about text
            pageData.sections.forEach(section => {
                const element = document.getElementById(section.id);
                if (element) {
                    element.innerHTML = `<p>${section.content}</p>`;
                }
            });
            
            // Update skills
            renderSkills();
            
            // Update experiences
            renderExperiences();
        }

        // Render skills
        function renderSkills() {
            const pageData = appData.pages.about;
            
            // Technical skills
            const techSkillsContainer = document.querySelector('#technicalSkills .skill-items');
            if (techSkillsContainer) {
                techSkillsContainer.innerHTML = pageData.skills.technical.map(skill => 
                    `<div class="skill-item">${skill}</div>`
                ).join('');
            }
            
            // Personal skills
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
            
            // Clear existing experiences except the first two (default)
            const existingExperiences = timeline.querySelectorAll('.experience-item');
            for (let i = 2; i < existingExperiences.length; i++) {
                existingExperiences[i].remove();
            }
            
            // Render experiences
            pageData.experiences.forEach((exp, index) => {
                let expElement = document.getElementById(exp.id);
                
                if (!expElement && index >= 2) {
                    // Create new experience element
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
                    
                    // Insert before the add button
                    const addButton = timeline.querySelector('[data-add="experience"]');
                    if (addButton) {
                        timeline.insertBefore(expElement, addButton);
                    } else {
                        timeline.appendChild(expElement);
                    }
                } else if (expElement) {
                    // Update existing experience
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
            
            // Clear container
            const existingAchievements = container.querySelectorAll('.achievement-card');
            for (let i = 2; i < existingAchievements.length; i++) {
                existingAchievements[i].remove();
            }
            
            // Render achievements
            pageData.items.forEach((item, index) => {
                let achievementElement = document.getElementById(item.id);
                
                if (!achievementElement && index >= 2) {
                    // Create new achievement element
                    achievementElement = document.createElement('div');
                    achievementElement.className = 'achievement-card editable';
                    achievementElement.id = item.id;
                    achievementElement.innerHTML = `
                        <h3>${item.title}</h3>
                        <div class="date">${item.date}</div>
                        <p>${item.description}</p>
                        <button class="edit-btn" data-edit="${item.id}">Edit</button>
                    `;
                    
                    // Insert before the add button
                    const addButton = document.querySelector('[data-add="achievement"]');
                    if (addButton) {
                        container.insertBefore(achievementElement, addButton);
                    } else {
                        container.appendChild(achievementElement);
                    }
                } else if (achievementElement) {
                    // Update existing achievement
                    achievementElement.querySelector('h3').textContent = item.title;
                    achievementElement.querySelector('.date').textContent = item.date;
                    achievementElement.querySelector('p').textContent = item.description;
                }
            });
        }

        // Render projects page
        function renderProjectsPage() {
            const pageData = appData.pages.projects;
            const container = document.getElementById('projectsContainer');
            
            if (!container) return;
            
            // Clear container
            const existingProjects = container.querySelectorAll('.project-card');
            for (let i = 3; i < existingProjects.length; i++) {
                existingProjects[i].remove();
            }
            
            // Render projects
            pageData.items.forEach((item, index) => {
                let projectElement = document.getElementById(item.id);
                
                if (!projectElement && index >= 3) {
                    // Create new project element
                    projectElement = document.createElement('div');
                    projectElement.className = 'project-card editable';
                    projectElement.id = item.id;
                    projectElement.innerHTML = `
                        <div class="project-image">
                            <i class="${item.icon}"></i>
                        </div>
                        <div class="project-content">
                            <h3>${item.title}</h3>
                            <p>${item.description}</p>
                        </div>
                        <button class="edit-btn" data-edit="${item.id}">Edit</button>
                    `;
                    
                    // Insert before the add button
                    const addButton = document.querySelector('[data-add="project"]');
                    if (addButton) {
                        container.insertBefore(projectElement, addButton);
                    } else {
                        container.appendChild(projectElement);
                    }
                } else if (projectElement) {
                    // Update existing project
                    projectElement.querySelector('h3').textContent = item.title;
                    projectElement.querySelector('p').textContent = item.description;
                    projectElement.querySelector('.project-image i').className = item.icon;
                }
            });
        }

        // Render dashboard page
        function renderDashboardPage() {
            const pageData = appData.pages.dashboard;
            
            // Update dashboard stats
            pageData.stats.forEach((stat, index) => {
                const statElement = document.getElementById(stat.id);
                if (statElement) {
                    statElement.querySelector('.dashboard-number').textContent = stat.number;
                    statElement.querySelector('.dashboard-label').textContent = stat.label;
                }
            });
        }

        // Render contact page
        function renderContactPage() {
            const pageData = appData.pages.contact;
            
            // Update contact items
            pageData.items.forEach(item => {
                const contactElement = document.getElementById(item.id);
                if (contactElement) {
                    contactElement.querySelector('h3').textContent = item.label;
                    contactElement.querySelector('p').textContent = item.value;
                    contactElement.querySelector('.contact-icon i').className = item.icon;
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
            
            // Toggle admin panel
            adminToggle.addEventListener('click', function(e) {
                e.stopPropagation();
                adminPanel.classList.toggle('active');
            });
            
            // Close admin panel when clicking outside
            document.addEventListener('click', function(e) {
                if (!e.target.closest('.admin-panel') && !e.target.closest('.admin-toggle')) {
                    adminPanel.classList.remove('active');
                }
            });
            
            // Admin login
            adminLogin.addEventListener('click', function() {
                const password = document.getElementById('adminPassword').value;
                
                if (password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    document.getElementById('adminControls').style.display = 'block';
                    document.getElementById('adminPassword').value = '';
                    showNotification('Login admin berhasil!', 'success');
                    updateAdminUI();
                    adminPanel.classList.remove('active');
                } else {
                    showNotification('Password salah!', 'error');
                }
            });
            
            // Admin logout
            adminLogout.addEventListener('click', function() {
                isAdminLoggedIn = false;
                isEditMode = false;
                document.getElementById('adminControls').style.display = 'none';
                document.body.classList.remove('edit-mode');
                document.getElementById('editStatus').style.display = 'none';
                showNotification('Logout berhasil', 'info');
                updateAdminUI();
            });
            
            // Toggle edit mode
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
                }
            });
            
            // Save all data
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
            // Setup edit buttons
            document.querySelectorAll('.edit-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const elementId = this.getAttribute('data-edit');
                    const element = document.getElementById(elementId);
                    
                    if (element) {
                        // Determine element type and content
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
                            // Default text edit
                            editText(elementId);
                        }
                    }
                });
            });
            
            // Setup add buttons
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
                
                // Update appData based on element type
                if (elementId.startsWith('stat')) {
                    // Update home stats
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
                description: newDescription
            };
            
            appData.pages.achievements.items.push(newAchievement);
            renderAchievementsPage();
            showNotification('Pencapaian berhasil ditambahkan!', 'success');
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
                icon: 'fas fa-project-diagram'
            };
            
            appData.pages.projects.items.push(newProject);
            renderProjectsPage();
            showNotification('Proyek berhasil ditambahkan!', 'success');
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
            
            // Update appData
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
                
                // Auto scroll to bottom
                chatMessages.scrollTop = chatMessages.scrollHeight;
                
                // Simulate a reply after 1 second
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
                    
                    // Reset form
                    contactForm.reset();
                });
            }
        }

        // Update admin UI
        function updateAdminUI() {
            const adminToggle = document.getElementById('adminToggle');
            
            if (isAdminLoggedIn) {
                adminToggle.innerHTML = '<i class="fas fa-user-check"></i> Admin Mode';
                adminToggle.style.backgroundColor = '#00a86b';
            } else {
                adminToggle.innerHTML = '<i class="fas fa-user-lock"></i> Login Admin';
                adminToggle.style.backgroundColor = 'var(--secondary)';
            }
        }

        // Show notification
        function showNotification(message, type = 'info') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            
            // Set color based on type
            if (type === 'success') {
                notification.style.backgroundColor = '#00a86b';
            } else if (type === 'error') {
                notification.style.backgroundColor = '#f44336';
            } else if (type === 'warning') {
                notification.style.backgroundColor = '#ff9800';
            } else {
                notification.style.backgroundColor = '#2196f3';
            }
            
            notification.style.display = 'block';
            
            // Hide after 3 seconds
            setTimeout(() => {
                notification.style.display = 'none';
            }, 3000);
        }
    </script>
</body>
</html>
