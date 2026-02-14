<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>STRIDE & CARRY - Premium Shoes & Leather Bags</title>
    
    <style>
        /* ==================== VARIABLES & RESET ==================== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --color-primary: #87ceeb;
            --color-secondary: #b0e0e6;
            --color-badge: #ffd700;
            --color-yellow: #ffeb3b;
            --color-olive: #7cb342;
            --color-soft: #f5e6d3;
            --color-dark: #faf8f3;
            --color-dark-light: #f0ebe3;
            --color-text: #333333;
            --color-text-muted: #666666;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: var(--color-dark);
            color: var(--color-text);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* ==================== BACKGROUND ==================== */
        .background-wrapper {
            display: none;
        }

        .futuristic-bg {
            display: none;
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

        @keyframes glow {
            0%, 100% {
                box-shadow: 0 0 20px rgba(0, 212, 255, 0.3);
            }
            50% {
                box-shadow: 0 0 40px rgba(0, 212, 255, 0.6);
            }
        }

        @keyframes slideInTitle {
            from {
                transform: translateY(30px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes slideInSubtitle {
            from {
                transform: translateY(20px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        /* ==================== CONTAINER ==================== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ==================== HEADER ==================== */
        .header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 2px solid rgba(135, 206, 235, 0.3);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 0 30px rgba(135, 206, 235, 0.1);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            font-size: 24px;
            font-weight: 300;
            letter-spacing: 3px;
            background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav {
            display: flex;
            gap: 30px;
        }

        .nav-link {
            background: none;
            border: none;
            color: var(--color-text);
            font-size: 14px;
            cursor: pointer;
            font-weight: 300;
            position: relative;
            transition: all 0.3s ease;
            letter-spacing: 1px;
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--color-primary);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        /* ==================== HERO CAROUSEL ==================== */
        .hero-carousel {
            width: 100%;
            height: 600px;
            margin: 40px 0;
            position: relative;
        }

        .carousel-container {
            position: relative;
            width: 100%;
            height: 100%;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 0 50px rgba(135, 206, 235, 0.2), inset 0 0 50px rgba(135, 206, 235, 0.05);
            border: 2px solid rgba(135, 206, 235, 0.3);
        }

        .carousel-slides {
            position: relative;
            width: 100%;
            height: 100%;
        }

        .carousel-slide {
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 0.7s ease;
            border-radius: 20px;
            overflow: hidden;
        }

        .carousel-slide.active {
            opacity: 1;
            z-index: 10;
        }

        .carousel-slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .slide-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(135, 206, 235, 0.15), rgba(176, 224, 230, 0.15));
            z-index: 2;
        }

        .slide-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            z-index: 3;
            width: 100%;
        }

        .slide-title {
            font-size: 60px;
            font-weight: 300;
            margin-bottom: 15px;
            color: #333333;
            text-shadow: 0 0 20px rgba(135, 206, 235, 0.2);
            letter-spacing: 2px;
            animation: slideInTitle 0.8s ease forwards;
        }

        .slide-subtitle {
            font-size: 18px;
            color: rgba(51, 51, 51, 0.85);
            text-shadow: 0 0 10px rgba(135, 206, 235, 0.15);
            animation: slideInSubtitle 0.8s ease 0.2s forwards;
            opacity: 0;
        }

        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(135, 206, 235, 0.2);
            border: 2px solid var(--color-primary);
            color: var(--color-primary);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 24px;
            z-index: 20;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .carousel-btn:hover {
            background: rgba(135, 206, 235, 0.4);
            box-shadow: 0 0 20px rgba(135, 206, 235, 0.4);
            transform: translateY(-50%) scale(1.1);
        }

        .prev-btn {
            left: 20px;
        }

        .next-btn {
            right: 20px;
        }

        .carousel-indicators {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 15px;
            z-index: 20;
        }

        .indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(135, 206, 235, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .indicator.active {
            background: var(--color-primary);
            width: 30px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(135, 206, 235, 0.4);
        }

        .indicator:hover {
            background: var(--color-primary);
            box-shadow: 0 0 15px rgba(135, 206, 235, 0.4);
        }

        /* ==================== TRUST BADGES ==================== */
        .trust-badges {
            background: rgba(240, 235, 227, 0.8);
            backdrop-filter: blur(10px);
            border-top: 1px solid rgba(135, 206, 235, 0.2);
            border-bottom: 1px solid rgba(135, 206, 235, 0.2);
            padding: 40px 0;
            margin: 40px 0;
        }

        .badges-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .badge {
            text-align: center;
            padding: 20px;
            background: rgba(135, 206, 235, 0.08);
            border: 1px solid rgba(135, 206, 235, 0.25);
            border-radius: 15px;
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: rgba(135, 206, 235, 0.15);
            border-color: var(--color-primary);
            box-shadow: 0 0 20px rgba(135, 206, 235, 0.15);
            transform: translateY(-5px);
        }

        .badge-icon {
            font-size: 36px;
            margin-bottom: 15px;
        }

        .badge p {
            font-size: 14px;
            color: var(--color-text-muted);
        }

        /* ==================== PRODUCTS SECTION ==================== */
        .products-section {
            padding: 60px 0;
        }

        .section-title {
            font-size: 42px;
            font-weight: 300;
            margin-bottom: 10px;
            background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 1px;
        }

        .section-subtitle {
            color: var(--color-text-muted);
            font-size: 16px;
            margin-bottom: 40px;
            font-weight: 300;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: rgba(255, 255, 255, 0.7);
            border: 1px solid rgba(135, 206, 235, 0.25);
            border-radius: 15px;
            overflow: hidden;
            cursor: pointer;
            transition: all 0.3s ease;
            padding: 15px;
        }

        .product-card:hover {
            border-color: var(--color-primary);
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 0 30px rgba(135, 206, 235, 0.2);
            transform: translateY(-10px);
        }

        .product-image {
            position: relative;
            width: 100%;
            height: 250px;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 15px;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .product-card:hover .product-image img {
            transform: scale(1.1);
        }

        .product-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(135, 206, 235, 0.15), rgba(176, 224, 230, 0.15));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .product-card:hover .product-overlay {
            opacity: 1;
        }

        .product-name {
            font-size: 18px;
            font-weight: 400;
            color: var(--color-text);
            margin-bottom: 5px;
        }

        .product-category {
            font-size: 12px;
            color: var(--color-primary);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 10px;
        }

        .product-price {
            display: none;
        }

        /* ==================== NEWSLETTER SECTION ==================== */
        .newsletter-section {
            padding: 60px 0;
            margin: 40px 0;
        }

        .newsletter-box {
            background: rgba(240, 235, 227, 0.9);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(135, 206, 235, 0.3);
            border-radius: 20px;
            padding: 50px;
            text-align: center;
            box-shadow: 0 0 40px rgba(135, 206, 235, 0.15);
        }

        .newsletter-box h3 {
            font-size: 36px;
            font-weight: 300;
            margin-bottom: 15px;
            letter-spacing: 1px;
        }

        .newsletter-box p {
            color: var(--color-text-muted);
            margin-bottom: 30px;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
        }

        .newsletter-form {
            display: flex;
            gap: 10px;
            max-width: 500px;
            margin: 0 auto;
            flex-wrap: wrap;
            justify-content: center;
        }

        .newsletter-input {
            flex: 1;
            min-width: 250px;
            background: rgba(135, 206, 235, 0.1);
            border: 1px solid rgba(135, 206, 235, 0.3);
            padding: 15px 20px;
            border-radius: 10px;
            color: var(--color-text);
            font-size: 14px;
            transition: all 0.3s ease;
        }

        .newsletter-input::placeholder {
            color: var(--color-text-muted);
        }

        .newsletter-input:focus {
            outline: none;
            background: rgba(135, 206, 235, 0.15);
            border-color: var(--color-primary);
            box-shadow: 0 0 20px rgba(135, 206, 235, 0.15);
        }

        .newsletter-btn {
            background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
            border: none;
            color: white;
            padding: 15px 30px;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            letter-spacing: 1px;
            min-width: 150px;
        }

        .newsletter-btn:hover {
            box-shadow: 0 0 30px rgba(135, 206, 235, 0.4);
            transform: scale(1.05);
        }

        /* ==================== FOOTER ==================== */
        .footer {
            background: rgba(255, 255, 255, 0.95);
            border-top: 1px solid rgba(135, 206, 235, 0.2);
            padding: 60px 0 30px;
            margin-top: 60px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4,
        .footer-col h5 {
            font-weight: 400;
            margin-bottom: 20px;
            color: var(--color-primary);
            font-size: 16px;
            letter-spacing: 1px;
        }

        .footer-col p {
            color: var(--color-text-muted);
            font-size: 13px;
            line-height: 1.8;
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col ul li {
            margin-bottom: 10px;
        }

        .footer-col a {
            color: var(--color-text-muted);
            text-decoration: none;
            font-size: 13px;
            transition: all 0.3s ease;
        }

        .footer-col a:hover {
            color: var(--color-primary);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(135, 206, 235, 0.2);
            color: var(--color-text-muted);
            font-size: 12px;
        }

        /* ==================== MODAL ==================== */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(5px);
        }

        .modal.show {
            display: flex;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
        }

        .modal-content {
            background: rgba(255, 255, 255, 0.98);
            border: 2px solid rgba(135, 206, 235, 0.3);
            border-radius: 20px;
            padding: 50px;
            text-align: center;
            max-width: 500px;
            box-shadow: 0 0 50px rgba(135, 206, 235, 0.2);
            animation: slideUp 0.3s ease;
        }

        .success-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 32px;
            color: white;
            margin: 0 auto 20px;
            box-shadow: 0 0 20px rgba(135, 206, 235, 0.3);
        }

        .modal-content h2 {
            font-size: 32px;
            margin-bottom: 15px;
            background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .modal-content p {
            color: var(--color-text-muted);
            margin-bottom: 10px;
            font-size: 14px;
        }

        .product-name-modal {
            color: var(--color-primary) !important;
            font-size: 18px !important;
            font-weight: 600 !important;
            margin-bottom: 20px !important;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .modal-btn {
            background: linear-gradient(90deg, var(--color-primary), var(--color-secondary));
            border: none;
            color: white;
            padding: 15px 40px;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            margin-top: 20px;
            transition: all 0.3s ease;
            letter-spacing: 1px;
            width: 100%;
        }

        .modal-btn:hover {
            box-shadow: 0 0 30px rgba(135, 206, 235, 0.4);
            transform: scale(1.02);
        }

        /* ==================== RESPONSIVE ==================== */
        @media (max-width: 768px) {
            .logo {
                font-size: 18px;
            }

            .nav {
                gap: 15px;
            }

            .nav-link {
                font-size: 12px;
            }

            .hero-carousel {
                height: 400px;
                margin: 20px 0;
            }

            .slide-title {
                font-size: 36px;
            }

            .slide-subtitle {
                font-size: 14px;
            }

            .carousel-btn {
                width: 40px;
                height: 40px;
                font-size: 18px;
            }

            .products-grid {
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
                gap: 15px;
            }

            .product-image {
                height: 150px;
            }

            .section-title {
                font-size: 28px;
            }

            .newsletter-box {
                padding: 30px 20px;
            }

            .modal-content {
                padding: 30px 20px;
                max-width: 90%;
            }
        }

        @media (max-width: 480px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }

            .nav {
                flex-direction: column;
                gap: 10px;
                align-items: center;
            }

            .carousel-indicators {
                bottom: 15px;
                gap: 8px;
            }

            .indicator {
                width: 8px;
                height: 8px;
            }

            .indicator.active {
                width: 20px;
            }

            .products-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .newsletter-form {
                flex-direction: column;
            }

            .newsletter-input {
                min-width: unset;
            }

            .newsletter-btn {
                min-width: unset;
            }

            .footer-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Background -->
    <div class="background-wrapper">
        <div class="futuristic-bg"></div>
    </div>

    <!-- Header -->
    <header class="header">
        <div class="container">
            <div class="header-content">
                <h1 class="logo">STRIDE & CARRY</h1>
                <nav class="nav">
                    <button class="nav-link">Shoes</button>
                    <button class="nav-link">Bags</button>
                    <button class="nav-link">About</button>
                </nav>
            </div>
        </div>
    </header>

    <!-- Hero Carousel -->
    <section class="hero-carousel">
        <div class="carousel-container">
            <div class="carousel-slides">
                <div class="carousel-slide active">
                    <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=1400&h=600&fit=crop" alt="Casual Shoes">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h2 class="slide-title">Casual Elegance</h2>
                        <p class="slide-subtitle">Discover our collection of premium casual shoes</p>
                    </div>
                </div>

                <div class="carousel-slide">
                    <img src="https://images.unsplash.com/photo-1548036328-c9fa89d128fa?w=1400&h=600&fit=crop" alt="Leather Bags">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h2 class="slide-title">Leather Craftsmanship</h2>
                        <p class="slide-subtitle">Handcrafted bags for every occasion</p>
                    </div>
                </div>

                <div class="carousel-slide">
                    <img src="https://images.unsplash.com/photo-1552062407-291826dfc003?w=1400&h=600&fit=crop" alt="Sports Shoes">
                    <div class="slide-overlay"></div>
                    <div class="slide-content">
                        <h2 class="slide-title">Active Performance</h2>
                        <p class="slide-subtitle">Sports shoes engineered for excellence</p>
                    </div>
                </div>
            </div>

            <!-- Carousel Controls -->
            <button class="carousel-btn prev-btn" onclick="prevSlide()">❮</button>
            <button class="carousel-btn next-btn" onclick="nextSlide()">❯</button>

            <!-- Slide Indicators -->
            <div class="carousel-indicators">
                <span class="indicator active" onclick="currentSlide(1)"></span>
                <span class="indicator" onclick="currentSlide(2)"></span>
                <span class="indicator" onclick="currentSlide(3)"></span>
            </div>
        </div>
    </section>

    <!-- Trust Badges -->
    <section class="trust-badges">
        <div class="container">
            <div class="badges-grid">
                <div class="badge">
                    <div class="badge-icon">🚚</div>
                    <p>Free Shipping on Orders $100+</p>
                </div>
                <div class="badge">
                    <div class="badge-icon">🛡️</div>
                    <p>100% Authentic Products</p>
                </div>
                <div class="badge">
                    <div class="badge-icon">↩️</div>
                    <p>30-Day Returns</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Shoes Section -->
    <section class="products-section shoes-section">
        <div class="container">
            <h3 class="section-title">Sports & Casual Shoes</h3>
            <p class="section-subtitle">Engineered for comfort, designed for style</p>

            <div class="products-grid">
                <div class="product-card" onclick="openForm('Urban Runner', 'shoe')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=500&h=500&fit=crop" alt="Urban Runner">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Urban Runner</h4>
                    <p class="product-category">Sports</p>
                </div>

                <div class="product-card" onclick="openForm('Casual Stride', 'shoe')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1514989940723-e8e51c9c6307?w=500&h=500&fit=crop" alt="Casual Stride">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Casual Stride</h4>
                    <p class="product-category">Casual</p>
                </div>

                <div class="product-card" onclick="openForm('Street Style', 'shoe')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1460353581641-37baddab0fa2?w=500&h=500&fit=crop" alt="Street Style">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Street Style</h4>
                    <p class="product-category">Casual</p>
                </div>

                <div class="product-card" onclick="openForm('Performance Pro', 'shoe')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1552062407-291826dfc003?w=500&h=500&fit=crop" alt="Performance Pro">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Performance Pro</h4>
                    <p class="product-category">Sports</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Bags Section -->
    <section class="products-section bags-section">
        <div class="container">
            <h3 class="section-title">Leather Bags</h3>
            <p class="section-subtitle">Crafted with precision, built to last</p>

            <div class="products-grid">
                <div class="product-card" onclick="openForm('Classic Tote', 'bag')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1548036328-c9fa89d128fa?w=500&h=500&fit=crop" alt="Classic Tote">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Classic Tote</h4>
                    <p class="product-category">Full Grain</p>
                </div>

                <div class="product-card" onclick="openForm('Crossbody Charm', 'bag')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1594938298603-c8148c4dae35?w=500&h=500&fit=crop" alt="Crossbody Charm">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Crossbody Charm</h4>
                    <p class="product-category">Premium</p>
                </div>

                <div class="product-card" onclick="openForm('Minimal Clutch', 'bag')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1543163521-9145f931371e?w=500&h=500&fit=crop" alt="Minimal Clutch">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Minimal Clutch</h4>
                    <p class="product-category">Vegetable Dyed</p>
                </div>

                <div class="product-card" onclick="openForm('Weekend Carryall', 'bag')">
                    <div class="product-image">
                        <img src="https://images.unsplash.com/photo-1556998603-c5ff8f88daad?w=500&h=500&fit=crop" alt="Weekend Carryall">
                        <div class="product-overlay"></div>
                    </div>
                    <h4 class="product-name">Weekend Carryall</h4>
                    <p class="product-category">Full Grain</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter Section -->
    <section class="newsletter-section">
        <div class="container">
            <div class="newsletter-box">
                <h3>Be the First to Know</h3>
                <p>Get exclusive early access to new collections and special offers</p>
                <div class="newsletter-form">
                    <input type="email" placeholder="Enter your email" class="newsletter-input">
                    <button class="newsletter-btn">Subscribe</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-col">
                    <h4>STRIDE & CARRY</h4>
                    <p>Premium shoes and leather bags for modern living.</p>
                </div>
                <div class="footer-col">
                    <h5>Shop</h5>
                    <ul>
                        <li><a href="#">Shoes</a></li>
                        <li><a href="#">Bags</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h5>Company</h5>
                    <ul>
                        <li><a href="#">About</a></li>
                        <li><a href="#">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-col">
                    <h5>Legal</h5>
                    <ul>
                        <li><a href="#">Privacy</a></li>
                        <li><a href="#">Terms</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2024 Stride & Carry. All rights reserved. | Waitlist: Connecting quality with you.</p>
            </div>
        </div>
    </footer>

    <!-- Waitlist Modal -->
    <div id="waitlistModal" class="modal">
        <div class="modal-content">
            <div class="modal-success">
                <div class="success-icon">✓</div>
                <h2>Thank You!</h2>
                <p>You've been added to our exclusive waitlist for:</p>
                <p class="product-name-modal" id="productNameModal"></p>
                <p>We'll notify you as soon as this item is available. Stay tuned for early access offers!</p>
                <button class="modal-btn" onclick="closeWaitlist()">Continue Shopping</button>
            </div>
        </div>
    </div>

    <script>
        let currentSlideIndex = 1;
        let autoSlideTimer;

        function initCarousel() {
            showSlide(currentSlideIndex);
            autoSlideCarousel();
        }

        function showSlide(n) {
            const slides = document.querySelectorAll('.carousel-slide');
            const indicators = document.querySelectorAll('.indicator');
            
            if (n > slides.length) {
                currentSlideIndex = 1;
            }
            if (n < 1) {
                currentSlideIndex = slides.length;
            }
            
            slides.forEach(slide => slide.classList.remove('active'));
            indicators.forEach(indicator => indicator.classList.remove('active'));
            
            if (slides[currentSlideIndex - 1]) {
                slides[currentSlideIndex - 1].classList.add('active');
            }
            if (indicators[currentSlideIndex - 1]) {
                indicators[currentSlideIndex - 1].classList.add('active');
            }
        }

        function nextSlide() {
            clearTimeout(autoSlideTimer);
            currentSlideIndex++;
            showSlide(currentSlideIndex);
            autoSlideCarousel();
        }

        function prevSlide() {
            clearTimeout(autoSlideTimer);
            currentSlideIndex--;
            showSlide(currentSlideIndex);
            autoSlideCarousel();
        }

        function currentSlide(n) {
            clearTimeout(autoSlideTimer);
            currentSlideIndex = n;
            showSlide(currentSlideIndex);
            autoSlideCarousel();
        }

        function autoSlideCarousel() {
            autoSlideTimer = setTimeout(() => {
                currentSlideIndex++;
                showSlide(currentSlideIndex);
                autoSlideCarousel();
            }, 5000);
        }

        function openForm(productName, productType) {
            const modal = document.getElementById('waitlistModal');
            const productNameModal = document.getElementById('productNameModal');
            
            productNameModal.textContent = productName;
            modal.classList.add('show');
        }

        function closeWaitlist() {
            const modal = document.getElementById('waitlistModal');
            modal.classList.remove('show');
        }

        window.onclick = function(event) {
            const modal = document.getElementById('waitlistModal');
            if (event.target == modal) {
                modal.classList.remove('show');
            }
        }

        const newsletterForm = document.querySelector('.newsletter-form');
        if (newsletterForm) {
            const newsletterBtn = document.querySelector('.newsletter-btn');
            
            newsletterBtn.addEventListener('click', function(e) {
                const emailInput = document.querySelector('.newsletter-input');
                const email = emailInput.value;
                
                if (email && validateEmail(email)) {
                    const originalText = newsletterBtn.textContent;
                    newsletterBtn.textContent = '✓ Subscribed!';
                    newsletterBtn.style.background = 'linear-gradient(90deg, #00ff88, #7cb342)';
                    
                    setTimeout(() => {
                        newsletterBtn.textContent = originalText;
                        newsletterBtn.style.background = 'linear-gradient(90deg, #87ceeb, #b0e0e6)';
                        emailInput.value = '';
                    }, 2000);
                } else {
                    alert('Please enter a valid email address');
                }
            });
        }

        function validateEmail(email) {
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        }

        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.6s ease forwards';
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.product-card').forEach(card => {
            card.style.opacity = '0';
            observer.observe(card);
        });

        document.querySelectorAll('.product-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.animation = 'glow 1.5s ease-in-out infinite';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.animation = 'none';
            });
        });

        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowLeft') {
                prevSlide();
            } else if (e.key === 'ArrowRight') {
                nextSlide();
            } else if (e.key === 'Escape') {
                const modal = document.getElementById('waitlistModal');
                modal.classList.remove('show');
            }
        });

        document.addEventListener('DOMContentLoaded', () => {
            initCarousel();
        });
    </script>
</body>
</html>
