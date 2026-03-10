# html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Projects - Portfolio</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <!-- Your CSS (fixed path) -->
    <link rel="stylesheet" href="../style.css/style.css">
    <style>
        /* Additional styles for projects page */
        .page-header {
            background: linear-gradient(135deg, var(--color-primary), var(--color-primary-dark));
            color: white;
            padding: var(--space-xl) var(--space-lg);
            text-align: center;
        }
        
        .page-header h1 {
            color: white;
            margin-bottom: var(--space-sm);
        }
        
        .page-header p {
            font-size: var(--font-lg);
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .filter-buttons {
            display: flex;
            justify-content: center;
            gap: var(--space-sm);
            margin: var(--space-lg) 0;
            flex-wrap: wrap;
        }
        
        .filter-btn {
            padding: var(--space-xs) var(--space-md);
            border: 2px solid var(--color-primary);
            background: transparent;
            color: var(--color-primary);
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .filter-btn:hover,
        .filter-btn.active {
            background: var(--color-primary);
            color: white;
        }
        
        /* Gallery Grid (Task 4.2 Exercise 1) */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: var(--space-md);
            padding: var(--space-lg);
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            aspect-ratio: 1;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        .gallery-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.8));
            color: white;
            padding: var(--space-md);
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover .gallery-overlay {
            transform: translateY(0);
        }
        
        /* Magazine Layout (Task 4.2 Exercise 2) */
        .magazine-layout {
            display: grid;
            grid-template-areas: 
                "header header header"
                "sidebar main main"
                "sidebar main main"
                "footer footer footer";
            grid-template-columns: 1fr 2fr 2fr;
            gap: var(--space-md);
            padding: var(--space-lg);
            max-width: 1200px;
            margin: 0 auto;
            background: var(--color-background-alt);
            border-radius: 8px;
        }
        
        .magazine-header {
            grid-area: header;
            background: var(--color-primary);
            color: white;
            padding: var(--space-md);
            border-radius: 8px;
        }
        
        .magazine-sidebar {
            grid-area: sidebar;
            background: var(--color-primary-light);
            padding: var(--space-md);
            border-radius: 8px;
            color: white;
        }
        
        .magazine-main {
            grid-area: main;
            background: white;
            padding: var(--space-md);
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        
        .magazine-footer {
            grid-area: footer;
            background: var(--color-primary-dark);
            color: white;
            padding: var(--space-md);
            border-radius: 8px;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .gallery-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .magazine-layout {
                grid-template-areas: 
                    "header"
                    "sidebar"
                    "main"
                    "footer";
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 480px) {
            .gallery-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation (same as index) -->
    <nav class="navbar">
        <div class="logo">My Portfolio</div>
        <ul class="nav-links">
            <li><a href="../index.html/Untitled-1.html">Home</a></li>
            <li><a href="../about.html/">About</a></li>
            <li><a href="../projects.html/projects.html" class="active">Projects</a></li>
            <li><a href="../contact.html/">Contact</a></li>
        </ul>
    </nav>

    <!-- Page Header -->
    <section class="page-header">
        <h1>My Projects</h1>
        <p>Check out my latest work and creative endeavors</p>
    </section>

    <!-- Filter Buttons -->
    <div class="filter-buttons">
        <button class="filter-btn active" role="button" tabindex="0" aria-pressed="true">All</button>
        <button class="filter-btn" role="button" tabindex="0" aria-pressed="false">Web Design</button>
        <button class="filter-btn" role="button" tabindex="0" aria-pressed="false">Development</button>
        <button class="filter-btn" role="button" tabindex="0" aria-pressed="false">UI/UX</button>
        <button class="filter-btn" role="button" tabindex="0" aria-pressed="false">Mobile</button>
    </div>

    <!-- Task 4.2 Exercise 1: Photo Gallery -->
    <h2 style="text-align: center; margin: var(--space-lg) 0 var(--space-md);">📸 Photo Gallery</h2>
    <div class="gallery-grid">
        <div class="gallery-item" data-categories="Web Design, Development">
            <img loading="lazy" src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=400" alt="Coding - laptop and code editor">
            <div class="gallery-overlay">
                <h3>Web Project 1</h3>
                <p>HTML, CSS, JS</p>
            </div>
        </div>
        <div class="gallery-item" data-categories="UI/UX, Design">
            <img loading="lazy" src="https://images.unsplash.com/photo-1522542550221-31fd19575a2d?w=400" alt="Design mockups on desk">
            <div class="gallery-overlay">
                <h3>Design Project</h3>
                <p>UI/UX Design</p>
            </div>
        </div>
        <div class="gallery-item" data-categories="Mobile">
            <img loading="lazy" src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=400" alt="Mobile app on phone">
            <div class="gallery-overlay">
                <h3>Mobile App</h3>
                <p>React Native</p>
            </div>
        </div>
        <div class="gallery-item" data-categories="Web Design">
            <img loading="lazy" src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?w=400" alt="Portfolio site screenshot">
            <div class="gallery-overlay">
                <h3>Portfolio Site</h3>
                <p>HTML, CSS</p>
            </div>
        </div>
        <div class="gallery-item" data-categories="Development">
            <img loading="lazy" src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=400" alt="E-commerce product listing">
            <div class="gallery-overlay">
                <h3>E-commerce</h3>
                <p>Full Stack</p>
            </div>
        </div>
        <div class="gallery-item" data-categories="Development, Web Design">
            <img loading="lazy" src="https://images.unsplash.com/photo-1558655146-9f40138edfeb?w=400" alt="Blog platform admin view">
            <div class="gallery-overlay">
                <h3>Blog Platform</h3>
                <p>WordPress</p>
            </div>
        </div>
    </div>

    <!-- Featured Projects with Cards -->
    <h2 style="text-align: center; margin: var(--space-xl) 0 var(--space-md);">🌟 Featured Projects</h2>
    <div class="projects-grid" style="padding-top: 0;">
        <!-- Card 1 -->
        <div class="card">
            <img loading="lazy" src="https://images.unsplash.com/photo-1517180102446-f3ece451e9d8?w=400" alt="Responsive website screenshot" class="card-image">
            <div class="card-content">
                <h3 class="card-title">Responsive Website</h3>
                <p class="card-description">A fully responsive website built with Flexbox and Grid.</p>
                <div class="card-tags">
                    <span class="card-tag">HTML5</span>
                    <span class="card-tag">CSS3</span>
                    <span class="card-tag">Flexbox</span>
                </div>
                <a href="#" class="btn btn-primary" style="width: 100%;">Live Demo</a>
            </div>
        </div>
        
        <!-- Card 2 -->
        <div class="card">
            <img loading="lazy" src="https://images.unsplash.com/photo-1523437113738-bbd3cc89f19f?w=400" alt="Mobile app UI mockup" class="card-image">
            <div class="card-content">
                <h3 class="card-title">Mobile App UI</h3>
                <p class="card-description">Beautiful mobile app interface with smooth animations.</p>
                <div class="card-tags">
                    <span class="card-tag">UI Design</span>
                    <span class="card-tag">Figma</span>
                    <span class="card-tag">Prototype</span>
                </div>
                <a href="#" class="btn btn-primary" style="width: 100%;">View Design</a>
            </div>
        </div>
        
        <!-- Card 3 -->
        <div class="card">
            <img loading="lazy" src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=400" alt="E-commerce store mockup" class="card-image">
            <div class="card-content">
                <h3 class="card-title">E-commerce Store</h3>
                <p class="card-description">Online store with shopping cart and product filters.</p>
                <div class="card-tags">
                    <span class="card-tag">JavaScript</span>
                    <span class="card-tag">API</span>
                    <span class="card-tag">CSS Grid</span>
                </div>
                <a href="#" class="btn btn-primary" style="width: 100%;">Shop Now</a>
            </div>
        </div>
    </div>

    <!-- Task 4.2 Exercise 2: Magazine Layout -->
    <h2 style="text-align: center; margin: var(--space-xl) 0 var(--space-md);">📰 Magazine Layout</h2>
    <div class="magazine-layout">
        <div class="magazine-header">
            <h3 style="color: white;">Magazine Header</h3>
            <p>This spans the full width</p>
        </div>
        <div class="magazine-sidebar">
            <h3 style="color: white;">Sidebar</h3>
            <ul style="color: white; list-style: none;">
                <li>📌 Latest News</li>
                <li>📌 Popular Posts</li>
                <li>📌 Categories</li>
                <li>📌 Archive</li>
            </ul>
        </div>
        <div class="magazine-main">
            <h3>Main Content</h3>
            <p>This is the main article area. Grid layout makes it easy to create complex layouts like magazines and newspapers.</p>
            <p>The sidebar stays fixed while the main content area is flexible.</p>
        </div>
        <div class="magazine-footer">
            <h3 style="color: white;">Footer</h3>
            <p style="color: white;">Full width footer with copyright info</p>
        </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-column">
                <h3>About Me</h3>
                <p style="color: var(--color-muted);">Web developer creating responsive, user-friendly websites.</p>
            </div>
            <div class="footer-column">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="index.html">Home</a></li>
                    <li><a href="about.html">About</a></li>
                    <li><a href="projects.html">Projects</a></li>
                    <li><a href="contact.html">Contact</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Projects</h3>
                <ul>
                    <li><a href="#">Web Design</a></li>
                    <li><a href="#">Development</a></li>
                    <li><a href="#">UI/UX</a></li>
                    <li><a href="#">Mobile Apps</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Connect</h3>
                <ul>
                    <li><a href="#">GitHub</a></li>
                    <li><a href="#">LinkedIn</a></li>
                    <li><a href="#">Twitter</a></li>
                    <li><a href="mailto:emmanuelwachira45@gmail.com">Email</a></li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 My Portfolio. All rights reserved.</p>
        </div>
    </footer>
    <script>
        (function(){
            const btns = document.querySelectorAll('.filter-btn');
            const items = document.querySelectorAll('.gallery-item');
            const normalize = s => (s || '').trim().toLowerCase();

            function setFilter(filter){
                const f = normalize(filter);
                items.forEach(item => {
                    const cats = (item.dataset.categories || '').toLowerCase();
                    if(f === 'all' || (cats && cats.includes(f)) ){
                        item.style.display = '';
                    } else {
                        item.style.display = 'none';
                    }
                });
            }

            btns.forEach(btn => {
                // ensure keyboard and ARIA behavior
                btn.setAttribute('role','button');
                if(!btn.hasAttribute('tabindex')) btn.setAttribute('tabindex','0');
                btn.setAttribute('aria-pressed', btn.classList.contains('active') ? 'true' : 'false');

                btn.addEventListener('click', () => {
                    btns.forEach(b => { b.classList.remove('active'); b.setAttribute('aria-pressed','false'); });
                    btn.classList.add('active');
                    btn.setAttribute('aria-pressed','true');
                    setFilter(btn.textContent);
                });

                btn.addEventListener('keydown', (e) => {
                    if(e.key === 'Enter' || e.key === ' '){
                        e.preventDefault();
                        btn.click();
                    }
                });
            });

            // init from active button or show all
            const active = document.querySelector('.filter-btn.active');
            setFilter(active ? active.textContent : 'all');
        })();
    </script>
</body>
</html>ojects.html
