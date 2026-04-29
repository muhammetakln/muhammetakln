<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muhammet Akalın - Backend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* CSS Variables */
        :root {
            --primary: #1e3a8a;
            --secondary: #0ea5e9;
            --accent: #06b6d4;
            --dark: #0f172a;
            --light: #f8fafc;
            --border: #1e293b;
            --success: #10b981;
            --warning: #f59e0b;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, var(--dark) 0%, #1a2637 100%);
            color: #e2e8f0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header/Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border);
            z-index: 1000;
            padding: 1rem 2rem;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #cbd5e1;
            transition: all 0.3s ease;
            font-size: 0.95rem;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        /* Hero Section */
        .hero {
            margin-top: 80px;
            padding: 6rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 800px;
            height: 800px;
            background: radial-gradient(circle, rgba(14, 165, 233, 0.1) 0%, transparent 70%);
            pointer-events: none;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
            animation: slideUp 0.8s ease;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            color: #f1f5f9;
            font-weight: 800;
            letter-spacing: -1px;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            color: var(--accent);
            margin-bottom: 2rem;
            font-weight: 600;
        }

        .hero p {
            font-size: 1.1rem;
            color: #cbd5e1;
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .location {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(14, 165, 233, 0.1);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            border: 1px solid var(--border);
            margin-bottom: 2rem;
            font-size: 0.95rem;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }

        .btn {
            padding: 0.75rem 1.5rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-weight: 600;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            color: white;
            box-shadow: 0 10px 25px rgba(14, 165, 233, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 35px rgba(14, 165, 233, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: var(--accent);
            border: 2px solid var(--accent);
        }

        .btn-secondary:hover {
            background: rgba(14, 165, 233, 0.1);
            transform: translateY(-2px);
        }

        /* Skills Section */
        .skills-section {
            max-width: 1200px;
            margin: 4rem auto;
            padding: 0 2rem;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 3rem;
            color: #f1f5f9;
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 4px;
            background: linear-gradient(135deg, var(--secondary), var(--accent));
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-card {
            background: rgba(30, 58, 138, 0.5);
            border: 1px solid var(--border);
            padding: 2rem;
            border-radius: 12px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .skill-card:hover {
            border-color: var(--accent);
            background: rgba(30, 58, 138, 0.7);
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(6, 182, 212, 0.15);
        }

        .skill-card h3 {
            color: var(--accent);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 0.75rem;
        }

        .badge {
            background: rgba(6, 182, 212, 0.2);
            color: var(--accent);
            padding: 0.4rem 0.8rem;
            border-radius: 20px;
            font-size: 0.85rem;
            border: 1px solid rgba(6, 182, 212, 0.5);
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: rgba(6, 182, 212, 0.3);
            border-color: var(--accent);
        }

        /* Tech Stack */
        .tech-stack {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 0 2rem;
        }

        .stack-categories {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .stack-item {
            background: rgba(15, 23, 42, 0.8);
            border-left: 4px solid var(--secondary);
            padding: 1.5rem;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .stack-item:hover {
            border-left-color: var(--accent);
            background: rgba(15, 23, 42, 0.95);
        }

        .stack-item h4 {
            color: var(--secondary);
            margin-bottom: 1rem;
            font-size: 1.1rem;
        }

        .stack-item p {
            color: #cbd5e1;
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* Timeline */
        .timeline {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 0 2rem;
        }

        .timeline-items {
            position: relative;
            padding: 2rem 0;
        }

        .timeline-items::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, var(--secondary), transparent);
            transform: translateX(-50%);
        }

        .timeline-item {
            margin-bottom: 3rem;
            position: relative;
        }

        .timeline-item:nth-child(odd) {
            text-align: right;
            padding-right: 50%;
            padding-left: 0;
        }

        .timeline-item:nth-child(even) {
            text-align: left;
            padding-left: 50%;
            padding-right: 0;
        }

        .timeline-content {
            background: rgba(30, 58, 138, 0.5);
            padding: 1.5rem;
            border-radius: 8px;
            border: 1px solid var(--border);
            position: relative;
        }

        .timeline-content h4 {
            color: var(--accent);
            margin-bottom: 0.5rem;
        }

        .timeline-content p {
            color: #cbd5e1;
            font-size: 0.95rem;
        }

        .timeline-dot {
            position: absolute;
            left: 50%;
            top: 2rem;
            width: 16px;
            height: 16px;
            background: var(--accent);
            border: 3px solid var(--dark);
            border-radius: 50%;
            transform: translateX(-50%);
        }

        /* Projects Section */
        .projects {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 0 2rem;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background: rgba(30, 58, 138, 0.5);
            border: 1px solid var(--border);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .project-header {
            background: linear-gradient(135deg, rgba(30, 58, 138, 0.8), rgba(14, 165, 233, 0.2));
            padding: 2rem;
            border-bottom: 1px solid var(--border);
        }

        .project-header h3 {
            color: var(--accent);
            margin-bottom: 0.5rem;
        }

        .project-body {
            padding: 1.5rem;
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .project-body p {
            color: #cbd5e1;
            margin-bottom: 1rem;
            font-size: 0.95rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: auto;
        }

        .project-tag {
            background: rgba(6, 182, 212, 0.1);
            color: var(--accent);
            padding: 0.3rem 0.7rem;
            border-radius: 15px;
            font-size: 0.8rem;
        }

        .project-card:hover {
            border-color: var(--accent);
            box-shadow: 0 15px 40px rgba(6, 182, 212, 0.2);
            transform: translateY(-5px);
        }

        /* Contact Section */
        .contact {
            max-width: 1200px;
            margin: 6rem auto;
            padding: 4rem 2rem;
            text-align: center;
        }

        .contact-content {
            max-width: 500px;
            margin: 0 auto;
        }

        .contact p {
            color: #cbd5e1;
            margin-bottom: 2rem;
            font-size: 1.1rem;
        }

        .contact-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 3rem;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.75rem 1.5rem;
            background: rgba(30, 58, 138, 0.5);
            border: 1px solid var(--border);
            border-radius: 8px;
            color: var(--accent);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .contact-link:hover {
            background: rgba(14, 165, 233, 0.2);
            border-color: var(--accent);
        }

        /* Footer */
        footer {
            border-top: 1px solid var(--border);
            padding: 3rem 2rem;
            text-align: center;
            color: #64748b;
            margin-top: 6rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .timeline-items::before {
                left: 0;
            }

            .timeline-item:nth-child(odd),
            .timeline-item:nth-child(even) {
                padding-left: 50px;
                padding-right: 0;
                text-align: left;
            }

            .timeline-dot {
                left: 0;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .skill-card {
            animation: fadeInUp 0.6s ease forwards;
        }

        .skill-card:nth-child(1) { animation-delay: 0.1s; }
        .skill-card:nth-child(2) { animation-delay: 0.2s; }
        .skill-card:nth-child(3) { animation-delay: 0.3s; }
        .skill-card:nth-child(4) { animation-delay: 0.4s; }

        .project-card {
            animation: fadeInUp 0.6s ease forwards;
        }

        .project-card:nth-child(1) { animation-delay: 0.1s; }
        .project-card:nth-child(2) { animation-delay: 0.2s; }
        .project-card:nth-child(3) { animation-delay: 0.3s; }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">MA</div>
            <ul class="nav-links">
                <li><a href="#skills">Teknolojiler</a></li>
                <li><a href="#projects">Projeler</a></li>
                <li><a href="#contact">İletişim</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Muhammet Akalın</h1>
            <p class="hero-subtitle">Backend Developer | C# & SQL Specialist</p>
            <div class="location">
                📍 Sivas, Türkiye
            </div>
            <p>Veritabanı tasarımı, API geliştirme ve clean code yaşayan full-stack developer. 
            Her gün daha güçlü ve daha hızlı çalışan kod yazmak için çalışıyorum.</p>
            
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">Projelerimi Gör</a>
                <a href="#contact" class="btn btn-secondary">Bana Ulaş</a>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="skills-section" id="skills">
        <h2 class="section-title">Teknolojiler & Araçlar</h2>
        
        <div class="skills-grid">
            <!-- Backend -->
            <div class="skill-card">
                <h3>🔧 Backend Development</h3>
                <div class="tech-badges">
                    <span class="badge">C#</span>
                    <span class="badge">.NET</span>
                    <span class="badge">ASP.NET</span>
                    <span class="badge">REST API</span>
                    <span class="badge">Entity Framework</span>
                </div>
            </div>

            <!-- Database -->
            <div class="skill-card">
                <h3>💾 Database</h3>
                <div class="tech-badges">
                    <span class="badge">SQL Server</span>
                    <span class="badge">SQLite</span>
                    <span class="badge">T-SQL</span>
                    <span class="badge">Database Design</span>
                    <span class="badge">Optimization</span>
                </div>
            </div>

            <!-- Frontend Basics -->
            <div class="skill-card">
                <h3>🎨 Frontend Basics</h3>
                <div class="tech-badges">
                    <span class="badge">HTML5</span>
                    <span class="badge">CSS3</span>
                    <span class="badge">JavaScript</span>
                    <span class="badge">Responsive Design</span>
                    <span class="badge">Bootstrap</span>
                </div>
            </div>

            <!-- Tools & Versioning -->
            <div class="skill-card">
                <h3>⚙️ Tools & DevOps</h3>
                <div class="tech-badges">
                    <span class="badge">Git</span>
                    <span class="badge">GitHub</span>
                    <span class="badge">Visual Studio</span>
                    <span class="badge">VS Code</span>
                    <span class="badge">SQL Management Studio</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Tech Stack Details -->
    <section class="tech-stack">
        <h2 class="section-title">Teknoloji Stack'im</h2>
        
        <div class="stack-categories">
            <div class="stack-item">
                <h4>💻 Backend</h4>
                <p><strong>C#</strong> ile yazılım geliştiriyorum. ASP.NET Core kullanarak modern web uygulamaları ve RESTful API'ler inşa ediyorum. Entity Framework ORM ile veritabanı operasyonlarını yönetiyorum.</p>
            </div>

            <div class="stack-item">
                <h4>🗄️ Database</h4>
                <p><strong>SQL Server</strong> ve <strong>SQLite</strong> ile çalışıyorum. T-SQL yazarak karmaşık sorgular oluşturuyor, veritabanı tasarımı yapıyor ve performans optimizasyonu sağlıyorum.</p>
            </div>

            <div class="stack-item">
                <h4>🌐 Frontend Integration</h4>
                <p><strong>HTML, CSS, JavaScript</strong> temellerine hakim olarak backend'i frontend ile entegre ediyorum. Responsive web tasarımı ve modern UI/UX prensiplerini uyguluyorum.</p>
            </div>

            <div class="stack-item">
                <h4>🛠️ Development Tools</h4>
                <p><strong>Git</strong> ve <strong>GitHub</strong> kullanarak versiyon kontrol yapıyorum. Visual Studio ve SQL Management Studio'da verimli bir şekilde kod yazıyor ve debug ediyorum.</p>
            </div>
        </div>
    </section>

    <!-- Learning Journey -->
    <section class="timeline">
        <h2 class="section-title">Gelişim Yolculuğum</h2>
        
        <div class="timeline-items">
            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <h4>HTML & CSS Temelleri</h4>
                    <p>Web geliştirmenin temel taşlarını öğrendim. Responsive design ve CSS Grid/Flexbox'a hakim oldum.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <h4>JavaScript & DOM</h4>
                    <p>JavaScript ile interaktif web uygulamaları yapmaya başladım. DOM manipülasyonu ve API çağrılarını öğrendim.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <h4>C# & Backend Development</h4>
                    <p>C# ile backend development'a geçiş yaptım. .NET framework ve ASP.NET Core öğrenimine başladım.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <h4>SQL & Database Design</h4>
                    <p>SQL Server ve SQLite ile çalışmaya başladım. Veritabanı tasarımı ve T-SQL sorguları yazıyor, optimizasyon yapıyorum.</p>
                </div>
            </div>

            <div class="timeline-item">
                <div class="timeline-dot"></div>
                <div class="timeline-content">
                    <h4>Full Stack Integration 🎯</h4>
                    <p>Şu an C# Backend'i Frontend'le entegre ederek tam fledged uygulamalar geliştiriyorum. REST API'ler yazıyor ve veritabanı yönetiyorum.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects" id="projects">
        <h2 class="section-title">Öne Çıkan Projeler</h2>
        
        <div class="project-grid">
            <div class="project-card">
                <div class="project-header">
                    <h3>PawPrintShop</h3>
                    <p style="font-size: 0.9rem; color: #cbd5e1; margin: 0;">Hayvan Bakım & Satış Platformu</p>
                </div>
                <div class="project-body">
                    <p>Hayvan ürünleri satış platformu. Kullanıcı yönetimi, ürün kataloğu ve siparişler için tam yönetim paneli.</p>
                    <div class="project-tags">
                        <span class="project-tag">C#</span>
                        <span class="project-tag">SQL Server</span>
                        <span class="project-tag">ASP.NET</span>
                        <span class="project-tag">HTML/CSS</span>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-header">
                    <h3>Todo Aplikasyonu</h3>
                    <p style="font-size: 0.9rem; color: #cbd5e1; margin: 0;">Görev Yönetim Sistemi</p>
                </div>
                <div class="project-body">
                    <p>C# backend ve HTML/CSS/JavaScript frontend ile yapılan görev yönetim uygulaması. SQLite veritabanı kullanılmıştır.</p>
                    <div class="project-tags">
                        <span class="project-tag">C#</span>
                        <span class="project-tag">SQLite</span>
                        <span class="project-tag">JavaScript</span>
                        <span class="project-tag">REST API</span>
                    </div>
                </div>
            </div>

            <div class="project-card">
                <div class="project-header">
                    <h3>E-Commerce API</h3>
                    <p style="font-size: 0.9rem; color: #cbd5e1; margin: 0;">Ürün Yönetim API'si</p>
                </div>
                <div class="project-body">
                    <p>Entity Framework Core kullanarak geliştirilmiş RESTful API. Ürün, kategori ve sipariş yönetimi işlemleri.</p>
                    <div class="project-tags">
                        <span class="project-tag">C#</span>
                        <span class="project-tag">Entity Framework</span>
                        <span class="project-tag">SQL Server</span>
                        <span class="project-tag">Swagger</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">İletişim Bilgileri</h2>
        <div class="contact-content">
            <p>Projeler hakkında konuşmak, işbirliği yapmak veya danışmanlık almak istiyorsanız bana ulaşın!</p>
            
            <div class="contact-links">
                <a href="https://github.com/muhammetakln" class="contact-link" target="_blank">
                    <span>🐙</span> GitHub
                </a>
                <a href="https://linkedin.com/in/muhammetakln" class="contact-link" target="_blank">
                    <span>💼</span> LinkedIn
                </a>
                <a href="mailto:muhammetakln@gmail.com" class="contact-link">
                    <span>📧</span> Email
                </a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Muhammet Akalın | Backend Developer in Progress 🚀</p>
        <p style="font-size: 0.9rem; margin-top: 1rem;">
            "Önce sorunları çöz, sonra düzelt, sonra hızlı çalışmasını sağla"
        </p>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Scroll reveal animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.skill-card, .project-card, .stack-item').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });

        // Active nav link
        window.addEventListener('scroll', () => {
            const sections = document.querySelectorAll('section');
            let current = '';
            
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (scrollY >= sectionTop - 200) {
                    current = section.getAttribute('id');
                }
            });

            document.querySelectorAll('.nav-links a').forEach(link => {
                link.style.color = '';
                if (link.getAttribute('href').substring(1) === current) {
                    link.style.color = 'var(--accent)';
                }
            });
        });
    </script>
</body>
</html>
