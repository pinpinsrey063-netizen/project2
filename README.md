# project2
just project2
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PinkBloom | Product Showcase</title>
    <link rel="stylesheet" type="text/css" href="css/bootstrap.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
         :root {
            --pink-light: #fff5f7;
            --pink-medium: #ffc2d1;
            --pink-dark: #ff8fab;
            --pink-accent: #fb6f92;
            --white: #ffffff;
            --gray-light: #f8f9fa;
            --gray-dark: #495057;
            --shadow: rgba(251, 111, 146, 0.15);
        }
        
        body {
            background-color: var(--pink-light);
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        /* Header Styles */
        
        header {
            background: linear-gradient(to right, var(--white), var(--pink-light));
            padding: 1.2rem 0;
            box-shadow: 0 4px 12px var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--pink-accent);
        }
        
        .logo i {
            margin-right: 10px;
            background: linear-gradient(45deg, var(--pink-accent), var(--pink-dark));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--gray-dark);
            font-weight: 600;
            transition: all 0.3s ease;
            padding: 5px 10px;
            border-radius: 20px;
        }
        
        .nav-links a:hover,
        .nav-links a.active {
            color: var(--pink-accent);
            background-color: rgba(255, 143, 171, 0.1);
        }
        
        .header-icons {
            display: flex;
            gap: 1.5rem;
            font-size: 1.3rem;
        }
        
        .header-icons i {
            color: var(--pink-accent);
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        
        .header-icons i:hover {
            transform: scale(1.1);
        }
        
        .cart-icon {
            position: relative;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--pink-accent);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .mobile-menu-btn {
            display: none;
            font-size: 1.5rem;
            color: var(--pink-accent);
            cursor: pointer;
        }
        /* Hero Section */
        
        .hero {
            background: linear-gradient(135deg, var(--white) 0%, var(--pink-light) 100%);
            padding: 4rem 0;
            margin-bottom: 3rem;
            border-radius: 0 0 30px 30px;
            overflow: hidden;
            position: relative;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -20%;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, var(--pink-medium) 0%, transparent 70%);
            opacity: 0.3;
            z-index: 0;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: relative;
            z-index: 1;
        }
        
        .hero-text {
            flex: 1;
            max-width: 600px;
        }
        
        .hero-text h1 {
            font-size: 3.2rem;
            color: var(--pink-accent);
            margin-bottom: 1rem;
            line-height: 1.2;
        }
        
        .hero-text p {
            font-size: 1.2rem;
            color: var(--gray-dark);
            margin-bottom: 2rem;
        }
        
        .cta-button {
            display: inline-block;
            background: linear-gradient(to right, var(--pink-accent), var(--pink-dark));
            color: white;
            padding: 15px 35px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            box-shadow: 0 4px 15px var(--shadow);
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(251, 111, 146, 0.3);
        }
        
        .hero-image {
            flex: 1;
            text-align: center;
        }
        
        .hero-image img {
            max-width: 100%;
            border-radius: 20px;
            box-shadow: 0 10px 30px var(--shadow);
            transform: perspective(1000px) rotateY(-10deg);
            transition: transform 0.5s ease;
        }
        
        .hero-image img:hover {
            transform: perspective(1000px) rotateY(0deg);
        }
        /* Categories Section */
        
        .categories {
            margin-bottom: 3rem;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 2.5rem;
            color: var(--pink-accent);
            font-size: 2.2rem;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(to right, var(--pink-medium), var(--pink-accent));
            border-radius: 2px;
        }
        
        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 25px;
        }
        
        .category-card {
            background-color: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px var(--shadow);
            transition: all 0.3s ease;
            text-align: center;
            padding: 2rem 1rem;
        }
        
        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(251, 111, 146, 0.2);
        }
        
        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--pink-accent), var(--pink-dark));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .category-card h3 {
            color: var(--pink-accent);
            margin-bottom: 0.5rem;
        }
        /* Products Section */
        
        .products {
            margin-bottom: 4rem;
        }
        
        .product-filter {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 2.5rem;
        }
        
        .filter-btn {
            background-color: var(--white);
            color: var(--pink-accent);
            border: 2px solid var(--pink-medium);
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .filter-btn:hover,
        .filter-btn.active {
            background-color: var(--pink-accent);
            color: white;
            border-color: var(--pink-accent);
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .product-card {
            background-color: var(--white);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px var(--shadow);
            transition: all 0.3s ease;
            position: relative;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(251, 111, 146, 0.25);
        }
        
        .product-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background-color: var(--pink-accent);
            color: white;
            padding: 5px 15px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 700;
            z-index: 2;
        }
        
        .product-image {
            height: 220px;
            width: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .product-card:hover .product-image {
            transform: scale(1.05);
        }
        
        .product-info {
            padding: 1.5rem;
        }
        
        .product-category {
            color: var(--pink-dark);
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 5px;
        }
        
        .product-name {
            font-size: 1.3rem;
            color: var(--gray-dark);
            margin-bottom: 10px;
            font-weight: 700;
        }
        
        .product-description {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.95rem;
        }
        
        .product-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1rem;
        }
        
        .price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--pink-accent);
        }
        
        .add-to-cart {
            background-color: var(--pink-medium);
            color: var(--pink-accent);
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2rem;
            transition: all 0.3s ease;
        }
        
        .add-to-cart:hover {
            background-color: var(--pink-accent);
            color: white;
            transform: rotate(90deg);
        }
        /* Gallery Section */
        
        .gallery {
            margin-bottom: 4rem;
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .gallery-item {
            border-radius: 15px;
            overflow: hidden;
            height: 250px;
            position: relative;
            box-shadow: 0 5px 15px var(--shadow);
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
            background: linear-gradient(to top, rgba(251, 111, 146, 0.8), transparent);
            color: white;
            padding: 1.5rem;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover .gallery-overlay {
            transform: translateY(0);
        }
        /* Newsletter Section */
        
        .newsletter {
            background: linear-gradient(135deg, var(--pink-accent) 0%, var(--pink-dark) 100%);
            padding: 4rem 2rem;
            border-radius: 30px;
            text-align: center;
            color: white;
            margin-bottom: 4rem;
            box-shadow: 0 10px 30px rgba(251, 111, 146, 0.3);
        }
        
        .newsletter h2 {
            margin-bottom: 1rem;
            font-size: 2.2rem;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 2rem;
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .newsletter-input {
            flex-grow: 1;
            padding: 15px 20px;
            border: none;
            border-radius: 30px 0 0 30px;
            font-size: 1rem;
        }
        
        .newsletter-button {
            background-color: var(--white);
            color: var(--pink-accent);
            border: none;
            padding: 15px 30px;
            border-radius: 0 30px 30px 0;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .newsletter-button:hover {
            background-color: var(--pink-light);
        }
        /* Footer */
        
        footer {
            background-color: var(--white);
            padding: 4rem 0 2rem;
            box-shadow: 0 -5px 15px var(--shadow);
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            color: var(--pink-accent);
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
        }
        
        .footer-column p {
            color: #666;
            margin-bottom: 1rem;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: var(--pink-light);
            color: var(--pink-accent);
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background-color: var(--pink-accent);
            color: white;
            transform: translateY(-3px);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            text-decoration: none;
            color: #666;
            transition: color 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--pink-accent);
        }
        
        .c {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid var(--pink-medium);
            color: #666;
            font-size: 0.9rem;
        }
        /* Responsive Design */
        
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            .hero-text {
                margin-bottom: 3rem;
            }
            .hero-text h1 {
                font-size: 2.8rem;
            }
            .newsletter-form {
                flex-direction: column;
                gap: 15px;
            }
            .newsletter-input,
            .newsletter-button {
                border-radius: 30px;
                width: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links,
            .header-icons {
                display: none;
            }
            .mobile-menu-btn {
                display: block;
            }
            .hero-text h1 {
                font-size: 2.3rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .category-grid,
            .product-grid,
            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
        
        @media (max-width: 480px) {
            .hero-text h1 {
                font-size: 1.9rem;
            }
            .hero {
                padding: 3rem 0;
            }
            .category-grid,
            .product-grid,
            .gallery-grid {
                grid-template-columns: 1fr;
            }
            .product-filter {
                justify-content: flex-start;
                overflow-x: auto;
                padding-bottom: 10px;
            }
        }
    </style>
</head>

<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-gem"></i>
                <span>VLPK Store</span>
            </div>

            <ul class="nav-links">
                <li><a href="#" class="active">Home</a></li>
                <li><a href="#">Products</a></li>
                <li><a href="#">Categories</a></li>
                <li><a href="#">Gallery</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>

            <div class="header-icons">
                <i class="fas fa-search"></i>
                <div class="cart-icon">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-count">3</span>
                </div>
                <i class="fas fa-user"></i>
            </div>

            <div class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container hero-content">
            <div class="hero-text">
                <h1 style="color:#d3536c">WELCOME ! VLKP STORE</h1>
                <p>Explore our exclusive collection of beautifully designed products that combine elegance and functionality. From home decor to fashion accessories, find the perfect items to brighten your day.</p>
                <a href="#products" class="cta-button">Shop Now</a>
            </div>
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Featured Product">
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories">
        <div class="container">
            <h2 class="section-title">Shop By Category</h2>
            <div class="category-grid">
                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-home"></i>
                    </div>
                    <h3>Home Decor</h3>
                    <p>Beautiful items to make your home cozy</p>
                </div>

                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-tshirt"></i>
                    </div>
                    <h3>Fashion</h3>
                    <p>Trendy clothing and accessories</p>
                </div>

                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-spa"></i>
                    </div>
                    <h3>Beauty</h3>
                    <p>Skincare and makeup products</p>
                </div>

                <div class="category-card">
                    <div class="category-icon">
                        <i class="fas fa-gift"></i>
                    </div>
                    <h3>Gifts</h3>
                    <p>Perfect presents for any occasion</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <div class="container">
            <h2 class="section-title">Featured Products</h2>

            <div class="product-filter">
                <button class="filter-btn active">All Products</button>
                <button class="filter-btn">Best Sellers</button>
                <button class="filter-btn">New Arrivals</button>
                <button class="filter-btn">On Sale</button>
                <button class="filter-btn">Luxury</button>
            </div>

            <div class="product-grid">
                <!-- Product 1 -->
                <div class="product-card">
                    <div class="product-badge">New</div>
                    <img src="https://images.unsplash.com/photo-1560769629-975ec94e6a86?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Pink Wireless Headphones" class="product-image">
                    <div class="product-info">
                        <div class="product-category"></div>
                        <h3 class="product-name">Urban Sneakers</h3>
                        <p class="product-description"> Urban Sneakers are made with high-quality materials, offering comfort, durability, and a modern design. They are lightweight, breathable, and perfect for everyday wear.</p>
                        <div class="product-price">
                            <span class="price">$89.99</span>
                            <button class="add-to-cart">
                                <i class="fas fa-shopping-cart"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Product 2 -->
                <div class="product-card">
                    <div class="product-badge">Sale</div>
                    <img src="https://images.unsplash.com/photo-1556155092-490a1ba16284?ixlib=rb-1.2.1&auto=format&fit=crop&w-800&q=80" alt="White Ceramic Mug Set" class="product-image">
                    <div class="product-info">
                        <div class="product-category"></div>
                        <h3 class="product-name">Lenovo</h3>
                        <p class="product-description">Lenovo computers are known for their reliable quality and strong performance. They come with good RAM that allows smooth multitasking and fast system operation. Lenovo also uses powerful CPUs such as Intel Core or AMD Ryzen, which
                            provide high speed and stable performance. Overall, Lenovo is a good choice for study, work, and daily use.</p>
                        <div class="product-price">
                            <span class="price">$500.99</span>
                            <button class="add-to-cart">
                                <i class="fas fa-shopping-cart"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Product 3 -->
                <div class="product-card">
                    <img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Pink Perfume Bottle" class="product-image">
                    <div class="product-info">
                        <div class="product-category"></div>
                        <h3 class="product-name">Cartier Necklace</h3>
                        <p class="product-description">A famous European luxury necklace brand from France, known for elegant design, high-quality materials, and timeless style.</p>
                        <div class="product-price">
                            <span class="price">$125000.99</span>
                            <button class="add-to-cart">
                                <i class="fas fa-shopping-cart"></i>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Product 4 -->
                <div class="product-card">
                    <img src="https://images.unsplash.com/photo-1545235617-9465d2a55698?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Pink Watch" class="product-image">
                    <div class="product-info">
                        <div class="product-category">Smartphone</div>
                        <h3 class="product-name">iPhone 14 Pro</h3>
                        <p class="product-description">Premium build quality with a sleek design, high-resolution OLED display, powerful performance, excellent camera system, and smooth, reliable user experience for everyday and professional use.</p>
                        <div class="product-price">
                            <span class="price">$300.99</span>
                            <button class="add-to-cart">
                                <i class="fas fa-shopping-cart"></i>
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section class="gallery">
        <div class="container">
            <h2 class="section-title">Product Gallery</h2>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1526170375885-4d8ecf77b99f?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Product Collection">
                    <div class="gallery-overlay">
                        <h3>Spring Collection</h3>
                        <p>Fresh arrivals for the season</p>
                    </div>
                </div>

                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1479064555552-3ef4979f8908?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Luxury Products">
                    <div class="gallery-overlay">
                        <h3>Luxury Line</h3>
                        <p>Premium quality products</p>
                    </div>
                </div>

                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1490481651871-ab68de25d43d?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Gift Ideas">
                    <div class="gallery-overlay">
                        <h3>Gift Ideas</h3>
                        <p>Perfect presents for loved ones</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter Section -->
    <section class="newsletter">
        <div class="container">
            <h2>Subscribe to Our Newsletter</h2>
            <p>Get exclusive offers, new product announcements, and styling tips delivered straight to your inbox.</p>
            <form class="newsletter-form">
                <input type="email" placeholder="Your email address" class="newsletter-input" required>
                <button type="submit" class="newsletter-button">Subscribe</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>PinkBloom</h3>
                    <p>We specialize in beautiful, high-quality products with a focus on pink and white aesthetics. Bringing elegance to everyday life.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                        <a href="#"><i class="fab fa-tiktok"></i></a>
                    </div>
                </div>

                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#">Home</a></li>
                        <li><a href="#">All Products</a></li>
                        <li><a href="#">New Arrivals</a></li>
                        <li><a href="#">Best Sellers</a></li>
                        <li><a href="#">Sale</a></li>
                    </ul>
                </div>

                <div class="footer-column">
                    <h3>Customer Service</h3>
                    <ul class="footer-links">
                        <li><a href="#">Contact Us</a></li>
                        <li><a href="#">Shipping Policy</a></li>
                        <li><a href="#">Returns & Exchanges</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Size Guide</a></li>
                    </ul>
                </div>

                <div class="footer-column">
                    <h3>Contact Info</h3>
                    <p><i class="fas fa-map-marker-alt"></i> 143, Phnom Penh City</p>
                    <p><i class="fas fa-phone"></i> (855)+097 337 675</p>
                    <p><i class="fas fa-envelope"></i> VLPK112030KKK@.com</p>
                </div>
            </div>

            <div class="c">
                <p>&copy; 2023 VLPK Store. All rights reserved. | Designed with <i class="fas fa-heart" style="color: var(--pink-accent);"></i></p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile menu toggle
        document.querySelector('.mobile-menu-btn').addEventListener('click', function() {
            const navLinks = document.querySelector('.nav-links');
            const headerIcons = document.querySelector('.header-icons');

            // Toggle display for mobile menu
            if (navLinks.style.display === 'flex') {
                navLinks.style.display = 'none';
                headerIcons.style.display = 'none';
            } else {
                navLinks.style.display = 'flex';
                headerIcons.style.display = 'flex';

                // Make it vertical for mobile
                navLinks.style.flexDirection = 'column';
                navLinks.style.position = 'absolute';
                navLinks.style.top = '100%';
                navLinks.style.left = '0';
                navLinks.style.width = '100%';
                navLinks.style.backgroundColor = 'var(--white)';
                navLinks.style.padding = '1.5rem';
                navLinks.style.boxShadow = '0 5px 15px var(--shadow)';

                headerIcons.style.position = 'absolute';
                headerIcons.style.top = 'calc(100% + 150px)';
                headerIcons.style.left = '0';
                headerIcons.style.width = '100%';
                headerIcons.style.justifyContent = 'center';
                headerIcons.style.backgroundColor = 'var(--white)';
                headerIcons.style.padding = '1rem';
                headerIcons.style.boxShadow = '0 5px 15px var(--shadow)';
            }
        });

        // Filter buttons functionality
        document.querySelectorAll('.filter-btn').forEach(button => {
            button.addEventListener('click', function() {
                // Remove active class from all buttons
                document.querySelectorAll('.filter-btn').forEach(btn => {
                    btn.classList.remove('active');
                });

                // Add active class to clicked button
                this.classList.add('active');

                // In a real application, this would filter the products
                // For this demo, we'll just show an alert
                const filterText = this.textContent;
                if (filterText !== 'All Products') {
                    alert(`Filtering by: ${filterText}`);
                }
            });
        });

        // Add to cart functionality
        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', function() {
                const productCard = this.closest('.product-card');
                const productName = productCard.querySelector('.product-name').textContent;
                const productPrice = productCard.querySelector('.price').textContent;

                // Update cart count
                const cartCount = document.querySelector('.cart-count');
                let currentCount = parseInt(cartCount.textContent);
                cartCount.textContent = currentCount + 1;

                // Show notification
                showNotification(`${productName} added to cart!`);

                // Animate the button
                this.style.backgroundColor = 'var(--pink-accent)';
                this.style.color = 'white';

                setTimeout(() => {
                    this.style.backgroundColor = '';
                    this.style.color = '';
                }, 300);
            });
        });

        // Newsletter form submission
        document.querySelector('.newsletter-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = this.querySelector('.newsletter-input').value;

            if (email) {
                showNotification(`Thank you for subscribing with: ${email}`);
                this.reset();
            }
        });

        // Show notification function
        function showNotification(message) {
            // Create notification element
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 100px;
                right: 20px;
                background-color: var(--pink-accent);
                color: white;
                padding: 15px 25px;
                border-radius: 10px;
                box-shadow: 0 5px 15px rgba(251, 111, 146, 0.3);
                z-index: 1001;
                font-weight: 600;
                transition: all 0.3s ease;
                transform: translateX(120%);
                max-width: 300px;
            `;
            notification.textContent = message;

            document.body.appendChild(notification);

            // Animate in
            setTimeout(() => {
                notification.style.transform = 'translateX(0)';
            }, 10);

            // Animate out and remove after 3 seconds
            setTimeout(() => {
                notification.style.transform = 'translateX(120%)';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const href = this.getAttribute('href');

                if (href !== '#') {
                    e.preventDefault();
                    const targetElement = document.querySelector(href);

                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                }
            });
        });
    </script>
</body>

</html>
