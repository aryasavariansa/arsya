<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CV Interaktif - Arya Savariansah</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1a73e8;
            --primary-dark: #0d47a1;
            --secondary: #00c853;
            --dark: #2d3748;
            --light: #f7fafc;
            --gray: #718096;
            --light-gray: #edf2f7;
            --border-radius: 10px;
            --box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
            --section-margin-left: 80px; /* Margin kiri untuk section */
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            color: var(--dark);
            background-color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary-dark), var(--primary));
            color: white;
            padding: 2rem 0;
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .profile-section {
            display: flex;
            align-items: center;
            gap: 2rem;
        }
        
        .profile-img-container {
            position: relative;
            width: 180px;
            height: 180px;
        }
        
        .profile-img {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 5px solid rgba(255,255,255,0.3);
            object-fit: cover;
            background-color: #f0f0f0;
        }
        
        .profile-img-placeholder {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 5px solid rgba(255,255,255,0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            background-color: rgba(255,255,255,0.2);
        }
        
        .profile-img-upload {
            position: absolute;
            bottom: 10px;
            right: 10px;
            background-color: var(--secondary);
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: var(--transition);
        }
        
        .profile-img-container:hover .profile-img-upload {
            opacity: 1;
        }
        
        .profile-info h1 {
            font-family: 'Poppins', sans-serif;
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
        }
        
        .profile-info p {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-bottom: 0.5rem;
        }
        
        .contact-info {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            margin-top: 1rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        /* Admin Panel (Tersembunyi) */
        .admin-panel {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
        }
        
        .admin-toggle {
            background-color: var(--secondary);
            color: white;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
            transition: var(--transition);
        }
        
        .admin-toggle:hover {
            transform: scale(1.1);
        }
        
        .admin-menu {
            position: absolute;
            top: 60px;
            right: 0;
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 1rem;
            width: 300px;
            display: none;
        }
        
        .admin-menu h3 {
            margin-bottom: 1rem;
            color: var(--primary-dark);
            font-family: 'Poppins', sans-serif;
        }
        
        .admin-menu.active {
            display: block;
        }
        
        .admin-input {
            width: 100%;
            padding: 0.8rem;
            margin-bottom: 1rem;
            border: 1px solid var(--light-gray);
            border-radius: 5px;
            font-family: 'Roboto', sans-serif;
        }
        
        .admin-btn {
            width: 100%;
            padding: 0.8rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-family: 'Poppins', sans-serif;
            font-weight: 500;
            transition: var(--transition);
            margin-bottom: 0.5rem;
        }
        
        .admin-btn:hover {
            background-color: var(--primary-dark);
        }
        
        .admin-btn-secondary {
            background-color: var(--gray);
        }
        
        .admin-btn-secondary:hover {
            background-color: var(--dark);
        }
        
        /* Navigation */
        .nav-container {
            background-color: white;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        nav ul li {
            padding: 1rem 1.5rem;
        }
        
        nav ul li a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }
        
        nav ul li a:hover {
            color: var(--primary);
        }
        
        nav ul li a.active {
            color: var(--primary);
        }
        
        nav ul li a.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: var(--primary);
            border-radius: 3px;
        }
        
        /* Main Content - dengan margin kiri */
        main {
            padding: 3rem 0;
        }
        
        .section {
            margin-bottom: 3rem;
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            padding: 2rem;
            transition: var(--transition);
            margin-left: var(--section-margin-left); /* Margin kiri */
            margin-right: 20px; /* Margin kanan lebih kecil */
        }
        
        .section:hover {
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--light-gray);
        }
        
        .section-title {
            font-family: 'Poppins', sans-serif;
            font-size: 1.8rem;
            font-weight: 600;
            color: var(--primary-dark);
        }
        
        /* Summary Section */
        .summary-content {
            font-size: 1.1rem;
            line-height: 1.8;
        }
        
        /* Work Experience */
        .timeline {
            position: relative;
            padding-left: 30px;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 4px;
            background-color: var(--primary);
            border-radius: 2px;
        }
        
        .timeline-item {
            position: relative;
            margin-bottom: 2rem;
            padding-left: 30px;
        }
        
        .timeline-item::before {
            content: '';
            position: absolute;
            left: -38px;
            top: 5px;
            width: 16px;
            height: 16px;
            border-radius: 50%;
            background-color: var(--primary);
            border: 3px solid white;
            box-shadow: 0 0 0 3px var(--primary);
        }
        
        .timeline-header {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            margin-bottom: 0.5rem;
        }
        
        .timeline-title {
            font-family: 'Poppins', sans-serif;
            font-size: 1.3rem;
            font-weight: 600;
            color: var(--dark);
        }
        
        .timeline-date {
            background-color: var(--light-gray);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-weight: 500;
            color: var(--primary);
        }
        
        .timeline-content {
            margin-top: 0.5rem;
        }
        
        .timeline-content ul {
            list-style-position: inside;
            padding-left: 1rem;
        }
        
        .timeline-content li {
            margin-bottom: 0.5rem;
        }
        
        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .skill-category {
            margin-bottom: 1.5rem;
        }
        
        .skill-category h3 {
            font-family: 'Poppins', sans-serif;
            margin-bottom: 1rem;
            color: var(--dark);
            font-size: 1.3rem;
        }
        
        .skill-items {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }
        
        .skill-item {
            background-color: var(--light-gray);
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-size: 0.9rem;
            transition: var(--transition);
        }
        
        .skill-item:hover {
            background-color: var(--primary);
            color: white;
            transform: translateY(-3px);
        }
        
        /* Language Progress */
        .language-progress {
            margin-top: 1.5rem;
        }
        
        .language-item {
            margin-bottom: 1.5rem;
        }
        
        .language-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }
        
        .progress-bar {
            height: 10px;
            background-color: var(--light-gray);
            border-radius: 5px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background-color: var(--primary);
            border-radius: 5px;
            width: 0;
            transition: width 1.5s ease;
        }
        
        /* Certificates */
        .certificates-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }
        
        .certificate-card {
            background-color: var(--light-gray);
            padding: 1.5rem;
            border-radius: var(--border-radius);
            transition: var(--transition);
        }
        
        .certificate-card:hover {
            transform: translateY(-5px);
            background-color: #e3f2fd;
        }
        
        .certificate-card h3 {
            font-family: 'Poppins', sans-serif;
            margin-bottom: 0.5rem;
            color: var(--dark);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 2rem 0;
            text-align: center;
            margin-left: var(--section-margin-left); /* Margin kiri sama dengan section */
            margin-right: 20px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1.5rem;
        }
        
        .footer-links {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: var(--transition);
        }
        
        .footer-links a:hover {
            color: var(--secondary);
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            :root {
                --section-margin-left: 40px;
            }
        }
        
        @media (max-width: 768px) {
            :root {
                --section-margin-left: 20px;
            }
            
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 1.5rem;
            }
            
            .profile-section {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            
            .skills-container {
                grid-template-columns: 1fr;
            }
            
            .certificates-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                flex-direction: column;
            }
            
            .section {
                margin-left: 10px;
                margin-right: 10px;
            }
            
            footer {
                margin-left: 10px;
                margin-right: 10px;
            }
        }
        
        /* Print Styles */
        @media print {
            .admin-panel, nav, footer {
                display: none !important;
            }
            
            .section {
                box-shadow: none;
                border: 1px solid #ddd;
                margin-left: 0;
                break-inside: avoid;
            }
            
            .profile-img-upload {
                display: none;
            }
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
            z-index: 1000;
            display: none;
            animation: slideIn 0.3s ease;
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
    </style>
</head>
<body>
    <!-- Admin Panel (Tersembunyi) -->
    <div class="admin-panel">
        <button class="admin-toggle" id="adminToggle">
            <i class="fas fa-user-lock"></i>
        </button>
        <div class="admin-menu" id="adminMenu">
            <h3>Panel Admin</h3>
            <input type="password" id="adminPassword" class="admin-input" placeholder="Password Admin">
            <button class="admin-btn" id="adminLogin">Login</button>
            <div id="adminControls" style="display: none;">
                <h4>Edit Data CV</h4>
                <select id="editSection" class="admin-input">
                    <option value="">Pilih bagian untuk diedit</option>
                    <option value="summary">Ringkasan</option>
                    <option value="experience">Pengalaman Kerja</option>
                    <option value="skills">Keahlian</option>
                    <option value="languages">Bahasa</option>
                    <option value="certificates">Sertifikat</option>
                </select>
                <textarea id="editContent" class="admin-input" rows="5" placeholder="Konten baru..."></textarea>
                <button class="admin-btn" id="saveChanges">Simpan Perubahan</button>
                <button class="admin-btn admin-btn-secondary" id="resetData">Reset ke Data Awal</button>
                <button class="admin-btn admin-btn-secondary" id="exportData">Ekspor Data</button>
                <button class="admin-btn admin-btn-secondary" id="adminLogout">Logout</button>
            </div>
        </div>
    </div>
    
    <!-- Header dengan informasi pribadi -->
    <header>
        <div class="container header-content">
            <div class="profile-section">
                <div class="profile-img-container">
                    <div class="profile-img-placeholder" id="profilePlaceholder">
                        <i class="fas fa-user-tie"></i>
                    </div>
                    <img src="" alt="Arya Savariansah" class="profile-img" id="profileImg" style="display: none;">
                    <div class="profile-img-upload" id="profileUpload">
                        <i class="fas fa-camera"></i>
                        <input type="file" id="profileInput" accept="image/*" style="display: none;">
                    </div>
                </div>
                <div class="profile-info">
                    <h1 id="profileName">ARYA SAVARIANSAH</h1>
                    <p id="profileTitle">Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi</p>
                    <div class="contact-info">
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <span id="profileEmail">aryasavarinasah@gmail.com</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <span id="profilePhone">089520336532</span>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <span id="profileLocation">Kosambi</span>
                        </div>
                        <div class="contact-item">
                            <i class="fab fa-linkedin"></i>
                            <span id="profileLinkedin">linkedin.com/in/arya-savariansah</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
    
    <!-- Navigasi -->
    <div class="nav-container">
        <div class="container">
            <nav>
                <ul>
                    <li><a href="#summary" class="nav-link active">Ringkasan</a></li>
                    <li><a href="#experience" class="nav-link">Pengalaman Kerja</a></li>
                    <li><a href="#skills" class="nav-link">Keahlian</a></li>
                    <li><a href="#languages" class="nav-link">Bahasa</a></li>
                    <li><a href="#certificates" class="nav-link">Sertifikat</a></li>
                </ul>
            </nav>
        </div>
    </div>
    
    <!-- Konten utama -->
    <main class="container">
        <!-- Ringkasan -->
        <section id="summary" class="section">
            <div class="section-header">
                <h2 class="section-title">Ringkasan</h2>
                <i class="fas fa-user-tie fa-2x" style="color: var(--primary);"></i>
            </div>
            <div class="summary-content" id="summaryContent">
                Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, hingga mechanical drafting. Memiliki kemampuan dalam meningkatkan efisiensi produksi, menurunkan tingkat reject, serta mendukung kelancaran proses manufaktur melalui desain teknis dan perencanaan yang sistematis.
            </div>
        </section>
        
        <!-- Pengalaman Kerja -->
        <section id="experience" class="section">
            <div class="section-header">
                <h2 class="section-title">Pengalaman Kerja</h2>
                <i class="fas fa-briefcase fa-2x" style="color: var(--primary);"></i>
            </div>
            <div class="timeline" id="experienceTimeline">
                <!-- Timeline items akan diisi oleh JavaScript -->
            </div>
        </section>
        
        <!-- Keahlian -->
        <section id="skills" class="section">
            <div class="section-header">
                <h2 class="section-title">Keahlian</h2>
                <i class="fas fa-cogs fa-2x" style="color: var(--primary);"></i>
            </div>
            <div class="skills-container" id="skillsContainer">
                <!-- Skills akan diisi oleh JavaScript -->
            </div>
        </section>
        
        <!-- Bahasa -->
        <section id="languages" class="section">
            <div class="section-header">
                <h2 class="section-title">Bahasa</h2>
                <i class="fas fa-language fa-2x" style="color: var(--primary);"></i>
            </div>
            <div class="language-progress" id="languageProgress">
                <!-- Language items akan diisi oleh JavaScript -->
            </div>
        </section>
        
        <!-- Sertifikat -->
        <section id="certificates" class="section">
            <div class="section-header">
                <h2 class="section-title">Sertifikat</h2>
                <i class="fas fa-certificate fa-2x" style="color: var(--primary);"></i>
            </div>
            <div class="certificates-grid" id="certificatesGrid">
                <!-- Certificate cards akan diisi oleh JavaScript -->
            </div>
        </section>
    </main>
    
    <!-- Footer -->
    <footer>
        <div class="container footer-content">
            <div>
                <p>&copy; 2025 Arya Savariansah. CV Interaktif.</p>
                <p style="font-size: 0.9rem; margin-top: 0.5rem; opacity: 0.8;">Update terakhir: <span id="lastUpdate"></span></p>
            </div>
            <div class="footer-links">
                <a href="mailto:aryasavarinasah@gmail.com"><i class="fas fa-envelope"></i> Email</a>
                <a href="https://www.linkedin.com/in/arya-savariansah-a45539366/"><i class="fab fa-linkedin"></i> LinkedIn</a>
                <a href="tel:089520336532"><i class="fas fa-phone"></i> Telepon</a>
            </div>
        </div>
    </footer>

    <!-- Notification -->
    <div class="notification" id="notification"></div>

    <script>
        // Data CV (disimpan di localStorage atau gunakan default)
        let cvData = {
            personalInfo: {
                name: "ARYA SAVARIANSAH",
                email: "aryasavarinasah@gmail.com",
                phone: "089520336532",
                location: "Kosambi",
                linkedin: "linkedin.com/in/arya-savariansah-a45539366/",
                title: "Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi",
                profileImage: "" // URL atau Base64 image
            },
            summary: "Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, hingga mechanical drafting. Memiliki kemampuan dalam meningkatkan efisiensi produksi, menurunkan tingkat reject, serta mendukung kelancaran proses manufaktur melalui desain teknis dan perencanaan yang sistematis.",
            workExperience: [
                {
                    title: "Mechanical Drafter Manufacturing",
                    period: "Jun 2025 - Sekarang",
                    achievements: [
                        "Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi.",
                        "Menyatukan berbagai variasi pengaturan molding menjadi 1 standar variasi, sehingga mempermudah operator dan menekan risiko kesalahan setting.",
                        "Berhasil mempercepat proses kerja operator bubut dengan membuat drawing detail yang lebih jelas, sehingga mengurangi waktu setup hingga 15% lebih cepat."
                    ]
                },
                {
                    title: "Staff Produksi",
                    period: "Jun 2024 - Jun 2025",
                    achievements: [
                        "Menganalisis dan menurunkan tingkat overconsumption material melalui evaluasi data penggunaan bahan, identifikasi penyebab pemborosan, dan koordinasi dengan tim terkait untuk perbaikan proses.",
                        "Menurunkan non-conformance bahan Div. Produksi dengan cara melakukan monitoring bahan.",
                        "Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dalam kurun waktu Desember 2024-Maret 2025 dengan cara membuat monitoring Stock WIP dan planning item Produksi.",
                        "Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)."
                    ]
                },
                {
                    title: "Operator Produksi",
                    period: "Mar 2024 - Jun 2024",
                    achievements: [
                        "Mengidentifikasi adanya ketidaksesuaian Parameter setting antara actual dan kapasitas mesin dan ditindaklanjuti oleh team RND.",
                        "Meningkatkan target Produksi harian tercapai dengan evaluasi kinerja dan standarisasi proses sesuai SOP.",
                        "Membuat jadwal pengecekan dan perawatan screw mesin.",
                        "Meningkatkan efisiensi Produksi hingga 20% melalui optimalisasi waktu kerja."
                    ]
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
            languages: [
                { language: "Indonesia", proficiency: 90 },
                { language: "English", proficiency: 50 }
            ],
            certificates: [
                { name: "Health, Safety, Environment and Quality (HSEQ)", description: "Sertifikasi profesional dalam bidang kesehatan, keselamatan, lingkungan, dan kualitas" },
                { name: "Introduction to Information Security Course", description: "Sertifikasi dasar keamanan informasi untuk memahami prinsip-prinsip keamanan data" }
            ],
            lastUpdate: new Date().toLocaleDateString('id-ID', { 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric',
                hour: '2-digit',
                minute: '2-digit'
            })
        };

        // Konfigurasi Admin (password bisa diganti)
        const ADMIN_PASSWORD = "arya2025"; // Ganti dengan password yang diinginkan
        
        // Status Admin
        let isAdminLoggedIn = false;
        
        // DOM Ready
        document.addEventListener('DOMContentLoaded', function() {
            // Load data dari localStorage jika ada
            loadFromLocalStorage();
            
            // Render data ke halaman
            renderCVData();
            
            // Setup event listeners
            setupEventListeners();
            
            // Setup navigasi
            setupNavigation();
            
            // Animate progress bars
            animateProgressBars();
        });
        
        // Load data dari localStorage
        function loadFromLocalStorage() {
            const savedData = localStorage.getItem('cvData');
            if (savedData) {
                try {
                    cvData = JSON.parse(savedData);
                } catch (e) {
                    console.error("Error loading data from localStorage:", e);
                }
            }
        }
        
        // Save data ke localStorage
        function saveToLocalStorage() {
            cvData.lastUpdate = new Date().toLocaleDateString('id-ID', { 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric',
                hour: '2-digit',
                minute: '2-digit'
            });
            
            localStorage.setItem('cvData', JSON.stringify(cvData));
        }
        
        // Render data CV ke halaman
        function renderCVData() {
            // Personal Info
            document.getElementById('profileName').textContent = cvData.personalInfo.name;
            document.getElementById('profileTitle').textContent = cvData.personalInfo.title;
            document.getElementById('profileEmail').textContent = cvData.personalInfo.email;
            document.getElementById('profilePhone').textContent = cvData.personalInfo.phone;
            document.getElementById('profileLocation').textContent = cvData.personalInfo.location;
            document.getElementById('profileLinkedin').textContent = cvData.personalInfo.linkedin;
            document.getElementById('lastUpdate').textContent = cvData.lastUpdate;
            
            // Profile Image
            if (cvData.personalInfo.profileImage) {
                document.getElementById('profilePlaceholder').style.display = 'none';
                document.getElementById('profileImg').style.display = 'block';
                document.getElementById('profileImg').src = cvData.personalInfo.profileImage;
            }
            
            // Summary
            document.getElementById('summaryContent').textContent = cvData.summary;
            
            // Work Experience
            const experienceTimeline = document.getElementById('experienceTimeline');
            experienceTimeline.innerHTML = '';
            
            cvData.workExperience.forEach(exp => {
                const expItem = document.createElement('div');
                expItem.className = 'timeline-item';
                expItem.innerHTML = `
                    <div class="timeline-header">
                        <h3 class="timeline-title">${exp.title}</h3>
                        <span class="timeline-date">${exp.period}</span>
                    </div>
                    <div class="timeline-content">
                        <ul>
                            ${exp.achievements.map(ach => `<li>${ach}</li>`).join('')}
                        </ul>
                    </div>
                `;
                experienceTimeline.appendChild(expItem);
            });
            
            // Skills
            const skillsContainer = document.getElementById('skillsContainer');
            skillsContainer.innerHTML = '';
            
            // Technical Skills
            const technicalSkillsDiv = document.createElement('div');
            technicalSkillsDiv.className = 'skill-category';
            technicalSkillsDiv.innerHTML = `
                <h3>Keahlian Teknis</h3>
                <div class="skill-items">
                    ${cvData.skills.technical.map(skill => `<div class="skill-item">${skill}</div>`).join('')}
                </div>
            `;
            skillsContainer.appendChild(technicalSkillsDiv);
            
            // Personal Skills
            const personalSkillsDiv = document.createElement('div');
            personalSkillsDiv.className = 'skill-category';
            personalSkillsDiv.innerHTML = `
                <h3>Keahlian Personal</h3>
                <div class="skill-items">
                    ${cvData.skills.personal.map(skill => `<div class="skill-item">${skill}</div>`).join('')}
                </div>
            `;
            skillsContainer.appendChild(personalSkillsDiv);
            
            // Languages
            const languageProgress = document.getElementById('languageProgress');
            languageProgress.innerHTML = '';
            
            cvData.languages.forEach(lang => {
                const langItem = document.createElement('div');
                langItem.className = 'language-item';
                langItem.innerHTML = `
                    <div class="language-info">
                        <span>${lang.language}</span>
                        <span>${lang.proficiency}%</span>
                    </div>
                    <div class="progress-bar">
                        <div class="progress-fill" data-width="${lang.proficiency}"></div>
                    </div>
                `;
                languageProgress.appendChild(langItem);
            });
            
            // Certificates
            const certificatesGrid = document.getElementById('certificatesGrid');
            certificatesGrid.innerHTML = '';
            
            cvData.certificates.forEach(cert => {
                const certCard = document.createElement('div');
                certCard.className = 'certificate-card';
                certCard.innerHTML = `
                    <h3>${cert.name}</h3>
                    <p>${cert.description}</p>
                `;
                certificatesGrid.appendChild(certCard);
            });
        }
        
        // Setup event listeners
        function setupEventListeners() {
            // Admin Toggle
            document.getElementById('adminToggle').addEventListener('click', function() {
                document.getElementById('adminMenu').classList.toggle('active');
            });
            
            // Admin Login
            document.getElementById('adminLogin').addEventListener('click', function() {
                const password = document.getElementById('adminPassword').value;
                
                if (password === ADMIN_PASSWORD) {
                    isAdminLoggedIn = true;
                    document.getElementById('adminControls').style.display = 'block';
                    document.getElementById('adminPassword').value = '';
                    showNotification('Login admin berhasil!', 'success');
                } else {
                    showNotification('Password salah!', 'error');
                }
            });
            
            // Admin Logout
            document.getElementById('adminLogout').addEventListener('click', function() {
                isAdminLoggedIn = false;
                document.getElementById('adminControls').style.display = 'none';
                document.getElementById('adminMenu').classList.remove('active');
                showNotification('Logout berhasil', 'info');
            });
            
            // Save Changes
            document.getElementById('saveChanges').addEventListener('click', function() {
                if (!isAdminLoggedIn) {
                    showNotification('Silakan login sebagai admin terlebih dahulu', 'error');
                    return;
                }
                
                const section = document.getElementById('editSection').value;
                const content = document.getElementById('editContent').value;
                
                if (!section || !content) {
                    showNotification('Pilih bagian dan isi konten terlebih dahulu', 'warning');
                    return;
                }
                
                // Update data berdasarkan section
                switch(section) {
                    case 'summary':
                        cvData.summary = content;
                        break;
                    case 'experience':
                        // Untuk pengalaman kerja, format khusus
                        try {
                            const expData = JSON.parse(content);
                            cvData.workExperience = expData;
                        } catch(e) {
                            showNotification('Format data pengalaman kerja tidak valid. Gunakan format JSON.', 'error');
                            return;
                        }
                        break;
                    case 'skills':
                        // Untuk skills, format khusus
                        try {
                            const skillsData = JSON.parse(content);
                            cvData.skills = skillsData;
                        } catch(e) {
                            showNotification('Format data keahlian tidak valid. Gunakan format JSON.', 'error');
                            return;
                        }
                        break;
                    case 'languages':
                        // Untuk bahasa, format khusus
                        try {
                            const langData = JSON.parse(content);
                            cvData.languages = langData;
                        } catch(e) {
                            showNotification('Format data bahasa tidak valid. Gunakan format JSON.', 'error');
                            return;
                        }
                        break;
                    case 'certificates':
                        // Untuk sertifikat, format khusus
                        try {
                            const certData = JSON.parse(content);
                            cvData.certificates = certData;
                        } catch(e) {
                            showNotification('Format data sertifikat tidak valid. Gunakan format JSON.', 'error');
                            return;
                        }
                        break;
                }
                
                // Simpan ke localStorage
                saveToLocalStorage();
                
                // Render ulang data
                renderCVData();
                
                // Reset form
                document.getElementById('editSection').value = '';
                document.getElementById('editContent').value = '';
                
                showNotification('Perubahan berhasil disimpan!', 'success');
            });
            
            // Reset Data
            document.getElementById('resetData').addEventListener('click', function() {
                if (!isAdminLoggedIn) {
                    showNotification('Silakan login sebagai admin terlebih dahulu', 'error');
                    return;
                }
                
                if (confirm('Apakah Anda yakin ingin mereset data ke default? Data yang sudah disimpan akan hilang.')) {
                    // Reset to default data
                    cvData = {
                        personalInfo: {
                            name: "ARYA SAVARIANSAH",
                            email: "aryasavarinasah@gmail.com",
                            phone: "089520336532",
                            location: "Kosambi",
                            linkedin: "linkedin.com/in/arya-savariansah-a45539366/",
                            title: "Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi",
                            profileImage: cvData.personalInfo.profileImage // Keep existing profile image
                        },
                        summary: "Lulusan SMK Teknik Permesinan dengan pengalaman di bidang manufaktur dan produksi. Terbiasa menangani perencanaan produksi, quality control, manajemen stok & distribusi, hingga mechanical drafting. Memiliki kemampuan dalam meningkatkan efisiensi produksi, menurunkan tingkat reject, serta mendukung kelancaran proses manufaktur melalui desain teknis dan perencanaan yang sistematis.",
                        workExperience: [
                            {
                                title: "Mechanical Drafter Manufacturing",
                                period: "Jun 2025 - Sekarang",
                                achievements: [
                                    "Membuat sistem pendataan molding beserta jangka waktu pakai (lifetime usage) untuk mendukung preventive maintenance dan mengurangi downtime produksi.",
                                    "Menyatukan berbagai variasi pengaturan molding menjadi 1 standar variasi, sehingga mempermudah operator dan menekan risiko kesalahan setting.",
                                    "Berhasil mempercepat proses kerja operator bubut dengan membuat drawing detail yang lebih jelas, sehingga mengurangi waktu setup hingga 15% lebih cepat."
                                ]
                            },
                            {
                                title: "Staff Produksi",
                                period: "Jun 2024 - Jun 2025",
                                achievements: [
                                    "Menganalisis dan menurunkan tingkat overconsumption material melalui evaluasi data penggunaan bahan, identifikasi penyebab pemborosan, dan koordinasi dengan tim terkait untuk perbaikan proses.",
                                    "Menurunkan non-conformance bahan Div. Produksi dengan cara melakukan monitoring bahan.",
                                    "Meningkatkan productivity penggunaan bahan WIP dari 2 Ton menjadi 724,5 kg dalam kurun waktu Desember 2024-Maret 2025 dengan cara membuat monitoring Stock WIP dan planning item Produksi.",
                                    "Menurunkan reject Div. Produksi pada mesin spiral dari 8% menjadi 3% dengan cara melakukan TFT (Task force Team)."
                                ]
                            },
                            {
                                title: "Operator Produksi",
                                period: "Mar 2024 - Jun 2024",
                                achievements: [
                                    "Mengidentifikasi adanya ketidaksesuaian Parameter setting antara actual dan kapasitas mesin dan ditindaklanjuti oleh team RND.",
                                    "Meningkatkan target Produksi harian tercapai dengan evaluasi kinerja dan standarisasi proses sesuai SOP.",
                                    "Membuat jadwal pengecekan dan perawatan screw mesin.",
                                    "Meningkatkan efisiensi Produksi hingga 20% melalui optimalisasi waktu kerja."
                                ]
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
                        languages: [
                            { language: "Indonesia", proficiency: 90 },
                            { language: "English", proficiency: 50 }
                        ],
                        certificates: [
                            { name: "Health, Safety, Environment and Quality (HSEQ)", description: "Sertifikasi profesional dalam bidang kesehatan, keselamatan, lingkungan, dan kualitas" },
                            { name: "Introduction to Information Security Course", description: "Sertifikasi dasar keamanan informasi untuk memahami prinsip-prinsip keamanan data" }
                        ],
                        lastUpdate: new Date().toLocaleDateString('id-ID', { 
                            year: 'numeric', 
                            month: 'long', 
                            day: 'numeric',
                            hour: '2-digit',
                            minute: '2-digit'
                        })
                    };
                    
                    saveToLocalStorage();
                    renderCVData();
                    showNotification('Data berhasil direset ke default', 'success');
                }
            });
            
            // Export Data
            document.getElementById('exportData').addEventListener('click', function() {
                if (!isAdminLoggedIn) {
                    showNotification('Silakan login sebagai admin terlebih dahulu', 'error');
                    return;
                }
                
                const dataStr = JSON.stringify(cvData, null, 2);
                const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
                const exportFileDefaultName = 'cv_arya_savariansah_backup.json';
                
                const linkElement = document.createElement('a');
                linkElement.setAttribute('href', dataUri);
                linkElement.setAttribute('download', exportFileDefaultName);
                linkElement.click();
                
                showNotification('Data berhasil diekspor', 'success');
            });
            
            // Profile Image Upload
            document.getElementById('profileUpload').addEventListener('click', function() {
                document.getElementById('profileInput').click();
            });
            
            document.getElementById('profileInput').addEventListener('change', function(e) {
                const file = e.target.files[0];
                if (file) {
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        cvData.personalInfo.profileImage = event.target.result;
                        saveToLocalStorage();
                        renderCVData();
                        showNotification('Foto profil berhasil diupdate!', 'success');
                    };
                    reader.readAsDataURL(file);
                }
            });
            
            // Edit Section Change
            document.getElementById('editSection').addEventListener('change', function() {
                if (!isAdminLoggedIn) return;
                
                const section = this.value;
                let content = '';
                
                switch(section) {
                    case 'summary':
                        content = cvData.summary;
                        break;
                    case 'experience':
                        content = JSON.stringify(cvData.workExperience, null, 2);
                        break;
                    case 'skills':
                        content = JSON.stringify(cvData.skills, null, 2);
                        break;
                    case 'languages':
                        content = JSON.stringify(cvData.languages, null, 2);
                        break;
                    case 'certificates':
                        content = JSON.stringify(cvData.certificates, null, 2);
                        break;
                }
                
                document.getElementById('editContent').value = content;
            });
        }
        
        // Setup navigasi
        function setupNavigation() {
            const navLinks = document.querySelectorAll('.nav-link');
            
            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    // Hapus kelas active dari semua link
                    navLinks.forEach(l => l.classList.remove('active'));
                    
                    // Tambah kelas active ke link yang diklik
                    this.classList.add('active');
                    
                    // Scroll ke bagian yang dituju
                    const targetId = this.getAttribute('href');
                    const targetSection = document.querySelector(targetId);
                    
                    window.scrollTo({
                        top: targetSection.offsetTop - 80,
                        behavior: 'smooth'
                    });
                });
            });
            
            // Update navigasi active berdasarkan scroll
            window.addEventListener('scroll', function() {
                let current = '';
                const sections = document.querySelectorAll('section');
                
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    const sectionHeight = section.clientHeight;
                    
                    if (pageYOffset >= (sectionTop - 100)) {
                        current = section.getAttribute('id');
                    }
                });
                
                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href') === `#${current}`) {
                        link.classList.add('active');
                    }
                });
            });
        }
        
        // Animate progress bars
        function animateProgressBars() {
            const progressFillElements = document.querySelectorAll('.progress-fill');
            
            const animateProgressBarsFunc = () => {
                progressFillElements.forEach(el => {
                    const width = el.getAttribute('data-width');
                    el.style.width = width + '%';
                });
            };
            
            // Trigger animasi ketika elemen terlihat di viewport
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        animateProgressBarsFunc();
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.5 });
            
            document.querySelectorAll('.language-progress').forEach(section => {
                observer.observe(section);
            });
            
            // Initial animation
            animateProgressBarsFunc();
        }
        
        // Show notification
        function showNotification(message, type = 'info') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            
            // Set color based on type
            if (type === 'success') {
                notification.style.backgroundColor = '#00c853';
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
        
        // Fungsi untuk preview JSON data (untuk admin)
        window.previewCVData = function() {
            if (isAdminLoggedIn) {
                console.log("CV Data:", cvData);
                return cvData;
            } else {
                console.log("Anda perlu login sebagai admin terlebih dahulu");
                return null;
            }
        };
    </script>
</body>
</html>
