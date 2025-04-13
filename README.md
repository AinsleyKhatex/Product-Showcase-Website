# Product-Showcase-Website

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spike - Athletic Footwear & Apparel</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <style>
        html {
            scroll-behavior: smooth;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
            transition: all 0.3s ease;
        }
        body {
            background-color: #000;
            color: #fff;
        }
        header {
            background-color: #000;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #222;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .logo {
            height: 40px;
        }
        .logo img {
            height: 100%;
        }
        nav {
            display: flex;
            align-items: center;
        }

        nav ul {
            display: flex;
            list-style: none;
        }
        nav ul li {
            margin: 0 30px;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 5px 0;
        }
        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: #fff;
            transition: width 0.3s ease;
        }
        nav ul li a:hover::after {
            width: 100%;
        }

        .icons-container {
            display: flex;
            align-items: center;
        }
        .icon {
            margin-left: 20px;
            cursor: pointer;
            color: #ffffff;
        }
        .icon i {
            transition: transform 0.3s ease;
            font-size: 18px;
            color: white;
        }
        .icon:hover i {
            transform: scale(1.2);
        }
        .search-bar {
            display: flex;
            align-items: center;
            background-color: transparent;
            border: none;
            color: #fff;
        }
        .search-bar input {
            background: transparent;
            border: none;
            color: #fff;
            padding: 5px;
            outline: none;
            border-bottom: 1px solid transparent;
            transition: border-bottom 0.3s ease;
        }
        .search-bar input:focus {
            border-bottom: 1px solid #fff;
        }
        .search-bar i {
            margin-right: 8px;
        }
        .promo-bar {
            background-color: #000;
            padding: 8px 0;
            text-align: center;
            border-bottom: 1px solid #222;
        }
        .promo-bar a {
            color: #fff;
            text-decoration: none;
            margin: 0 10px;
            font-size: 14px;
            position: relative;
        }
        .promo-bar a::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 0;
            height: 1px;
            background-color: #fff;
            transition: width 0.3s ease;
        }
        .promo-bar a:hover::after {
            width: 100%;
        }
        .hero {
            display: flex;
            height: 100vh;
            position: relative;
        }
        .hero-left,
        .hero-right {
            flex: 1;
            position: relative;
            height: 100%;
        }
        .hero-left img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        .video-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: 0;
        }
        .video-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            z-index: 0;
        }
        .hero-right {
            flex: 1;
            position: relative;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-content {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            text-align: center;
            z-index: 1;
            padding: 30px;
            color: #3f3b3b;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: rgba(0, 0, 0, 0.6);
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.5);
            max-width: 500px;
            width: 90%;
        }
        .hero-content h3 {
            font-size: 20px;
            color: #ffffff;
            font-weight: 600;
            letter-spacing: 1px;
            margin-bottom: 10px;
        }

        .hero-content h1 {
            font-size: 38px;
            color: #ffffff;
            font-weight: 800;
            text-transform: uppercase;
            margin-bottom: 10px;
        }

        .hero-content p {
            font-size: 16px;
            color: #dddddd;
            font-style: italic;
        }


        .shop-btn {
            padding: 12px 30px;
            background-color: #ffffff;
            color: #000;
            text-decoration: none;
            font-weight: 600;
            border-radius: 30px;
            transition: background-color 0.3s ease;
        }
        .shop-btn:hover {
            background-color: #5f5c5c;
        }
        .category-showcase {
            display: flex;
            padding: 20px;
            gap: 20px;
            background-color: #000;
        }
        .category-card {
            flex: 1;
            position: relative;
            height: 70vh;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #1a1a1a;
            cursor: pointer;
        }
        .category-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.2);
            z-index: 1;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .category-card:hover::before {
            opacity: 1;
        }
        .category-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        .category-card:hover img {
            transform: scale(1.1);
        }
        .category-label {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(255, 255, 255, 0.8);
            color: #000;
            padding: 8px 20px;
            border-radius: 20px;
            text-transform: uppercase;
            font-weight: bold;
            font-size: 14px;
            z-index: 2;
            transition: all 0.3s ease;
        }

        .category-card:hover .category-label {
            background-color: #fff;
            transform: translateX(-50%) translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        .top-bar {
            background-color: #000000;
            padding: 8px 20px;
            display: flex;
            justify-content: flex-end;
            font-size: 14px;
        }

        .top-links a {
            color: #ffffff;
            text-decoration: none;
            margin-left: 10px;
        }
        .top-links a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="top-bar">
        <div class="top-links">
            <a href="#findStore" class="top-link">Find a Store</a> |
            <a href="#help-section" class="top-link">Help</a> |
            <a href="#joinUs" class="top-link">Join Us</a> |
            <a href="#signIn" class="top-link">Sign In</a>
        </div>
    </div>
    <header>
      <div class="logo">
        <a href="#home">
            <img src="Images/Logo.png" alt="Spike Logo" width="120" height="200">
        </a>
    </div>
    <nav>
        <ul>
            <li><a href="#home">New & Featured</a></li>
            <li><a href="#men">Men</a></li>
            <li><a href="#women">Women</a></li>
            <li><a href="#kids">Kids</a></li>
            <li><a href="#sale">Sale</a></li> 
            <li><a href="#snkrs">SNKRS</a></li> 
        </ul>
    </nav>    
        <div class="icons-container">
            <div class="search-bar">
                <i class="fa fa-search"></i>
                <input type="text" placeholder="Search...">
            </div>
            <div class="icon">
                <a href="/favorites">
                    <i class="fa fa-heart"></i>
                </a>
            </div>
            <div class="icon">
                <a href="/account">
                    <i class="fa fa-user"></i>
                </a>
            </div>
            <div class="mobile-menu-icon">
                <div></div>
                <div></div>
                <div></div>
            </div>
        </div>
    </header>
    <div class="promo-bar">
        <span>Free Standard Delivery & 30-Day Free Returns </span>
        <br><a href="/join">Join Now</a>
        <a href="/details">View Details</a>
    </div>
    <section id="home">
        <div class="hero">
            <div class="hero-left">
                <img src="Images/shoe1.jpeg" alt="Spike Air DN10 shoe">
            </div>
            <div class="hero-right">
                <video class="video-background" autoplay loop muted>
                    <source src="Videos/Shoes (1).mp4" type="video/mp4">
                    <img src="/api/placeholder/800/600" alt="Background">
                </video>
            </div>
        </div>
    
        <div class="hero-content">
            <h3>Just In</h3>
            <h1>SPIKE AIR DN10</h1>
            <p>Exploration 2 of 6: Hannihae by Jeo</p><br>
            <a href="#shop" class="shop-btn">SHOP</a>
        </div>
    </section>
    
    </style>
    <section class="category-showcase">
      <a href="#women" class="category-card">
        <img src="Images/women model 2.jpg" alt="Women's clothing" class="clickable-image">
        <div class="category-label">WOMENS</div>
      </a>
  
      <a href="#men" class="category-card">
        <img src="Images/Men's Model.jpg" alt="Men's clothing" class="clickable-image">
        <div class="category-label">MENS</div>
      </a>
  
      <a href="#kids" class="category-card">
        <img src="Images/kids model 1.jpg" alt="Kids' clothing" class="clickable-image">
        <div class="category-label">KIDS</div>
      </a>
    </section>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
            transition: all 0.3s ease;
        }
        body {
            background-color: #000;
            color: #fff;
        }
        header {
            background-color: #000;
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #222;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .category-section {
            padding: 50px 20px;
            background-color: #111;
        }
        .section-header {
            text-align: center;
            margin-bottom: 40px;
        }
        .section-header h2 {
            font-size: 32px;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
            position: relative;
            display: inline-block;
        }
        .section-header h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            width: 60px;
            height: 3px;
            background-color: #fff;
            transform: translateX(-50%);
            transition: width 0.3s ease;
        }
        .section-header:hover h2::after {
            width: 100px;
        }
        .section-header p {
            color: #999;
            font-size: 16px;
            max-width: 700px;
            margin: 0 auto;
        }
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }
        .product-card {
            background-color: #222;
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            cursor: pointer;
        }
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        .product-image {
            height: 300px;
            overflow: hidden;
            position: relative;
            cursor: pointer;
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
        .product-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: rgba(0, 0, 0, 0.7);
            color: #fff;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 12px;
            font-weight: bold;
            text-transform: uppercase;
            z-index: 2;
        }
        .product-details {
            padding: 20px;
        }
        .product-name {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 10px;
        }
        .product-category {
            color: #999;
            font-size: 14px;
            margin-bottom: 10px;
        }
        .product-price {
            font-weight: bold;
            font-size: 18px;
            margin-bottom: 15px;
        }
        .product-colors {
            display: flex;
            gap: 8px;
            margin-bottom: 15px;
        }
        .color-option {
            width: 20px;
            height: 20px;
            border-radius: 50%;
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        .color-option:hover {
            transform: scale(1.2);
        }
        .add-to-cart {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.3s ease;
            text-align: center;
            text-decoration: none;
        }
        .add-to-cart:hover {
            background-color: #fff;
            color: #000;
        }
        .section-footer {
            text-align: center;
            margin-top: 40px;
        }
        .view-all-btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: transparent;
            border: 2px solid #fff;
            color: #fff;
            font-weight: bold;
            text-transform: uppercase;
            text-decoration: none;
            border-radius: 30px;
            transition: all 0.3s ease;
            letter-spacing: 1px;
        }
        .view-all-btn:hover {
            background-color: #fff;
            color: #000;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        .product-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.85);
            z-index: 1000;
            overflow-y: auto;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .product-modal.active {
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 1;
        }
        .modal-content {
            background-color: #111;
            border-radius: 10px;
            max-width: 900px;
            width: 90%;
            margin: 40px auto;
            position: relative;
            display: flex;
            flex-direction: column;
            animation: modalFadeIn 0.3s ease;
            overflow: hidden;
            max-height: 90vh;
        }
        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #333;
        }
        .modal-header h3 {
            font-size: 24px;
            font-weight: bold;
            color: #fff;
        }
        .close-modal {
            background: none;
            border: none;
            color: #999;
            font-size: 24px;
            cursor: pointer;
            transition: color 0.3s ease;
        }
        .close-modal:hover {
            color: #fff;
        }
        .modal-body {
            display: flex;
            flex-direction: column;
            padding: 0;
            overflow-y: auto;
        }

        @media (min-width: 768px) {
            .modal-body {
                flex-direction: row;
            }
        }
        .modal-image-container {
            flex: 1;
            background-color: #000;
            overflow: hidden;
            position: relative;
        }
        .modal-image {
            width: 100%;
            height: 300px;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        @media (min-width: 768px) {
            .modal-image {
                height: 400px;
            }
        }
        .modal-image:hover {
            transform: scale(1.05);
        }

        .modal-details {
            flex: 1;
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .modal-product-name {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .modal-product-category {
            color: #999;
            font-size: 16px;
            margin-bottom: 15px;
        }

        .modal-product-price {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .modal-product-description {
            color: #ccc;
            line-height: 1.6;
            margin-bottom: 20px;
            font-size: 16px;
        }

        .modal-product-features {
            margin-bottom: 20px;
        }

        .modal-product-features h4 {
            font-size: 18px;
            margin-bottom: 10px;
            color: #fff;
        }

        .modal-product-features ul {
            list-style-type: none;
            padding-left: 5px;
        }

        .modal-product-features ul li {
            position: relative;
            padding-left: 20px;
            margin-bottom: 8px;
            color: #ccc;
        }

        .modal-product-features ul li:before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #4caf50;
        }

        .modal-product-colors {
            margin-bottom: 20px;
        }

        .modal-product-colors h4 {
            font-size: 18px;
            margin-bottom: 10px;
            color: #fff;
        }

        .color-options {
            display: flex;
            gap: 10px;
        }

        .color-option-modal {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            transition: transform 0.3s ease;
            border: 2px solid transparent;
        }

        .color-option-modal:hover {
            transform: scale(1.2);
        }

        .color-option-modal.selected {
            border: 2px solid #fff;
        }

        .modal-sizes {
            margin-bottom: 20px;
        }

        .modal-sizes h4 {
            font-size: 18px;
            margin-bottom: 10px;
            color: #fff;
        }

        .size-options {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .size-option {
            width: 50px;
            height: 40px;
            background-color: #333;
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        .size-option:hover {
            background-color: #444;
        }

        .size-option.selected {
            background-color: #fff;
            color: #000;
        }

        .modal-actions {
            display: flex;
            gap: 10px;
            margin-top: auto;
        }
        .modal-add-to-cart {
            flex: 3;
            padding: 12px;
            background-color: #fff;
            color: #000;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
        }
        .modal-add-to-cart:hover {
            background-color: #f2f2f2;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        .modal-add-to-wishlist {
            flex: 1;
            padding: 12px;
            background-color: transparent;
            border: 1px solid #fff;
            color: #fff;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .modal-add-to-wishlist:hover {
            background-color: rgba(255, 255, 255, 0.1);
            transform: translateY(-3px);
        }
        .divider {
            height: 1px;
            background: linear-gradient(to right, transparent, #555, transparent);
            margin: 0 auto;
            width: 80%;
        }
        .snkrs-section {
            background-color: #0a0a0a;
        }
        .snkrs-section .section-header h2 {
            font-size: 40px;
            font-weight: 800;
            color: #f5f5f5;
        }
        .snkrs-section .product-card {
            background-color: #1a1a1a;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
        }
        .release-date {
            color: #ff3a3a;
            font-weight: bold;
            margin-bottom: 5px;
        }
        .countdown {
            margin-top: 10px;
            font-size: 14px;
            color: #aaa;
        }
        .exclusive-label {
            position: absolute;
            top: 15px;
            left: 15px;
            background-color: rgba(255, 58, 58, 0.9);
            color: #fff;
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 12px;
            font-weight: bold;
            text-transform: uppercase;
            z-index: 2;
        }
        @media (max-width: 992px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
        }
        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }           
            .section-header h2 {
                font-size: 24px;
            }         
            .modal-body {
                flex-direction: column;
            }          
            .modal-image {
                height: 250px;
            }
        }
        @media (max-width: 480px) {
            .product-grid {
                grid-template-columns: 1fr;
            }
            
            .product-image {
                height: 250px;
            }
            
            .modal-actions {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <section class="category-section" id="men">
        <div class="section-header">
            <h2>Men's Collection</h2>
            <p>Elevate your athletic performance with our cutting-edge men's footwear and apparel. Designed for maximum comfort and style.</p>
        </div>
        <div class="product-grid">
            <div class="product-card" data-product-id="mens-1">
                <div class="product-image">
                    <img src="Images/MEN1.png" alt="Men's Running Shoes">
                    <span class="product-badge">New</span>
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Air Velocity</div>
                    <div class="product-category">Men's Running Shoes</div>
                    <div class="product-price">₱1,299.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #000000;"></div>
                        <div class="color-option" style="background-color: #3a3a3a;"></div>
                        <div class="color-option" style="background-color: #2a4d9e;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
            <div class="product-card" data-product-id="mens-2">
                <div class="product-image">
                    <img src="Images/MEN2.jpg" alt="Men's Training Shoes">
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Elite Force</div>
                    <div class="product-category">Men's Training Shoes</div>
                    <div class="product-price">₱1,499.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #d82a2a;"></div>
                        <div class="color-option" style="background-color: #252525;"></div>
                        <div class="color-option" style="background-color: #ffffff;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
            <div class="product-card" data-product-id="mens-3">
                <div class="product-image">
                    <img src="Images/MEN3.jpeg" alt="Men's Basketball Shoes">
                    <span class="product-badge">Bestseller</span>
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Court Dominator</div>
                    <div class="product-category">Men's Basketball Shoes</div>
                    <div class="product-price">₱1,599.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #2a4d9e;"></div>
                        <div class="color-option" style="background-color: #000000;"></div>
                        <div class="color-option" style="background-color: #eaae00;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
        </div>
        
        <div class="section-footer">
            <a href="/men" class="view-all-btn">View All Men's Products</a>
        </div>
    </section>
    <div class="divider"></div>
    <section class="category-section" id="women">
        <div class="section-header">
            <h2>Women's Collection</h2>
            <p>Push your limits with our performance-driven women's footwear and apparel, blending innovative technology with contemporary design.</p>
        </div>
        
        <div class="product-grid">
            <div class="product-card" data-product-id="womens-1">
                <div class="product-image">
                    <img src="Images/WOMEN1.jpg" alt="Women's Running Shoes">
                    <span class="product-badge">New</span>
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Air Glide</div>
                    <div class="product-category">Women's Running Shoes</div>
                    <div class="product-price">₱3,458.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #ff4eb8;"></div>
                        <div class="color-option" style="background-color: #000000;"></div>
                        <div class="color-option" style="background-color: #ffffff;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
            <div class="product-card" data-product-id="womens-2">
                <div class="product-image">
                    <img src="Images/WOMEN2.jpg" alt="Women's Training Shoes">
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Elite Flex</div>
                    <div class="product-category">Women's Training Shoes</div>
                    <div class="product-price">₱2,139.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #6a3dbd;"></div>
                        <div class="color-option" style="background-color: #3a3a3a;"></div>
                        <div class="color-option" style="background-color: #0eb9de;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
            <div class="product-card" data-product-id="womens-3">
                <div class="product-image">
                    <img src="Images/WOMEN3.jpg" alt="Women's Lifestyle Shoes">
                    <span class="product-badge">Trending</span>
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Urban Pulse</div>
                    <div class="product-category">Women's Lifestyle Shoes</div>
                    <div class="product-price">₱3,109.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #ffffff;"></div>
                        <div class="color-option" style="background-color: #f0e9d2;"></div>
                        <div class="color-option" style="background-color: #000000;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
        </div>
        
        <div class="section-footer">
            <a href="/women" class="view-all-btn">View All Women's Products</a>
        </div>
    </section>
    
    <div class="divider"></div>
    <section class="category-section" id="kids">
        <div class="section-header">
            <h2>Kids' Collection</h2>
            <p>Durable, comfortable, and fun footwear and apparel designed for growing athletes and everyday adventures.</p>
        </div>  
        <div class="product-grid">
            <div class="product-card" data-product-id="kids-1">
                <div class="product-image">
                    <img src="Images/KIDS1.jpg" alt="Kids' Running Shoes">
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Junior Dash</div>
                    <div class="product-category">Kids' Running Shoes</div>
                    <div class="product-price">₱2,079.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #00b8ff;"></div>
                        <div class="color-option" style="background-color: #ff6b00;"></div>
                        <div class="color-option" style="background-color: #000000;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
            <div class="product-card" data-product-id="kids-2">
                <div class="product-image">
                    <img src="Images/KIDS2.jpg" alt="Kids' Basketball Shoes">
                    <span class="product-badge">Popular</span>
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Youth Slam</div>
                    <div class="product-category">Kids' Basketball Shoes</div>
                    <div class="product-price">₱1,689.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #ff3a3a;"></div>
                        <div class="color-option" style="background-color: #000000;"></div>
                        <div class="color-option" style="background-color: #3a3a3a;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
            <div class="product-card" data-product-id="kids-3">
                <div class="product-image">
                    <img src="Images/KIDS3.png" alt="Kids' Casual Shoes">
                </div>
                <div class="product-details">
                    <div class="product-name">Spike Kids Play</div>
                    <div class="product-category">Kids' Casual Shoes</div>
                    <div class="product-price">₱1,269.99</div>
                    <div class="product-colors">
                        <div class="color-option" style="background-color: #5dbe3f;"></div>
                        <div class="color-option" style="background-color: #a64dff;"></div>
                        <div class="color-option" style="background-color: #ff9e00;"></div>
                    </div>
                    <a href="#" class="add-to-cart">Add to Cart</a>
                </div>
            </div>
        </div>
        
        <div class="section-footer">
            <a href="/kids" class="view-all-btn">View All Kids' Products</a>
        </div>
    </section>
<style>
    .sale-section {
      position: relative;
      border-radius: 15px;
      padding: 50px 30px;
      margin: 60px 0;
      overflow: hidden;
      box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
      animation: fadeIn 1s ease-out;
      width: 100%;
      z-index: 1;
    }
    
    .video-background {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      z-index: -2;
      opacity: 0.6;
    }
    
    .video-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0.6) 100%);
      z-index: -1;
    }
    
    .sale-content {
      position: relative;
      z-index: 2;
      text-align: center;
      backdrop-filter: blur(3px);
      padding: 30px;
      border-radius: 10px;
      background-color: rgba(0, 0, 0, 0.4);
    }
    
    .sale-heading {
      font-size: 4rem;
      font-weight: 800;
      text-transform: uppercase;
      margin-bottom: 20px;
      background: linear-gradient(90deg, #ffffff 0%, #ffffff 50%, #ffffff 100%);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: textGlow 2s infinite alternate, titlePulse 4s infinite;
      text-shadow: 0 0 30px rgb(255, 255, 255);
      position: relative;
      display: inline-block;
    }
    
    @keyframes textGlow {
      0% {
        text-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
      }
      100% {
        text-shadow: 0 0 40px #131212, 0 0 80px rgba(0, 0, 0, 0.4);
      }
    }
    
    @keyframes titlePulse {
      0%, 100% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.05);
      }
    }
    
    .sale-description {
      color: white;
      font-size: 1.5rem;
      max-width: 800px;
      margin: 0 auto 40px;
      line-height: 1.5;
      animation: fadeInUp 1.5s ease-out;
      text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
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
    
    .sale-deals {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
      margin-bottom: 40px;
    }
    
    .sale-deal {
      background: rgba(0, 0, 0, 0.5);
      border-radius: 10px;
      padding: 20px;
      width: 280px;
      text-align: center;
      position: relative;
      overflow: hidden;
      transform: translateY(50px);
      opacity: 0;
      animation: dealSlideUp 0.8s forwards;
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
      transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }
    
    .sale-deal:hover {
      transform: translateY(-5px) scale(1.03);
      box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
      background: rgba(0, 0, 0, 0.6);
    }
    
    .sale-deal:nth-child(1) {
      animation-delay: 0.2s;
    }
    
    .sale-deal:nth-child(2) {
      animation-delay: 0.4s;
    }
    
    .sale-deal:nth-child(3) {
      animation-delay: 0.6s;
    }
    
    @keyframes dealSlideUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    .discount-label {
      position: absolute;
      top: 10px;
      right: 10px;
      background: #f95738;
      color: white;
      font-weight: bold;
      padding: 8px 12px;
      border-radius: 20px;
      z-index: 1;
      box-shadow: 0 5px 10px rgba(249, 87, 56, 0.4);
      animation: discountPulse 2s infinite;
    }
    
    @keyframes discountPulse {
      0%, 100% {
        transform: scale(1);
        box-shadow: 0 5px 10px rgba(249, 87, 56, 0.4);
      }
      50% {
        transform: scale(1.1);
        box-shadow: 0 10px 20px rgba(249, 87, 56, 0.6);
      }
    }
    
    .sale-deal img {
      width: 100%;
      height: 160px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 15px;
      transition: transform 0.5s ease;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    }
    
    .sale-deal:hover img {
      transform: scale(1.05);
    }
    
    .deal-title {
      font-size: 1.2rem;
      color: white;
      margin-bottom: 10px;
      font-weight: 600;
    }
    
    .deal-price {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
      margin-bottom: 15px;
    }
    
    .original-price {
      color: #999;
      text-decoration: line-through;
      font-size: 1rem;
    }
    
    .current-price {
      color: #f95738;
      font-size: 1.5rem;
      font-weight: bold;
    }
    
    .deal-button {
      display: inline-block;
      background: #4e4d4d;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      text-decoration: none;
      transition: all 0.3s ease;
      cursor: pointer;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      position: relative;
      overflow: hidden;
    }
    
    .deal-button:hover {
      background: #000000;
      transform: translateY(-3px);
      box-shadow: 0 7px 10px rgba(0, 0, 0, 0.2);
    }
    
    .deal-button::after {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(
        90deg, 
        rgba(255,255,255,0) 0%, 
        rgba(255,255,255,0.3) 50%, 
        rgba(255,255,255,0) 100%
      );
      transition: left 0.5s ease;
    }
    
    .deal-button:hover::after {
      left: 100%;
    }
    
    .countdown-container {
      margin-top: 20px;
      margin-bottom: 40px;
      text-align: center;
    }
    
    .countdown-title {
      font-size: 1.2rem;
      color: white;
      margin-bottom: 15px;
      animation: fadeIn 1s ease-out 0.5s backwards;
    }
    
    .countdown {
      display: flex;
      justify-content: center;
      gap: 15px;
    }
    
    .countdown-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      background: rgba(0, 0, 0, 0.5);
      padding: 15px;
      min-width: 80px;
      border-radius: 8px;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      animation: countPulse 1s infinite alternate;
      animation-delay: calc(var(--delay) * 0.2s);
      border: 1px solid rgba(255, 255, 255, 0.1);
    }
    
    @keyframes countPulse {
      to {
        transform: translateY(-5px);
        box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
      }
    }
    
    .countdown-number {
      font-size: 2rem;
      font-weight: bold;
      color: white;
    }
    
    .countdown-label {
      font-size: 0.8rem;
      color: #ccc;
      text-transform: uppercase;
      margin-top: 5px;
    }
    
    .sale-cta {
      margin-top: 40px;
      animation: ctaBounce 1s ease-out 1s backwards;
    }
    
    @keyframes ctaBounce {
      0%, 20%, 50%, 80%, 100% {
        transform: translateY(0);
      }
      40% {
        transform: translateY(-20px);
      }
      60% {
        transform: translateY(-10px);
      }
    }
    
    .sale-button {
      display: inline-block;
      background: linear-gradient(135deg, #000000 0%, #ffffff 100%);
      color: white;
      font-size: 1.2rem;
      font-weight: bold;
      padding: 15px 40px;
      border-radius: 30px;
      text-decoration: none;
      text-transform: uppercase;
      letter-spacing: 1px;
      transition: all 0.4s ease;
      cursor: pointer;
      box-shadow: 0 10px 20px rgba(255, 255, 255, 0.4);
      position: relative;
      overflow: hidden;
      z-index: 1;
    }
    
    .sale-button::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(135deg, #000000 0%, rgb(255, 255, 255) 100%);
      z-index: -1;
      transition: opacity 0.5s ease;
      opacity: 0;
    }
    
    .sale-button:hover::before {
      opacity: 1;
    }
    
    .sale-button:hover {
      transform: translateY(-5px);
      box-shadow: 0 15px 30px rgba(0, 0, 0, 0.6);
    }
    
    .sale-button::after {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(
        90deg, 
        rgba(255,255,255,0) 0%, 
        rgba(255,255,255,0.4) 50%, 
        rgba(255,255,255,0) 100%
      );
      transition: left 0.5s ease;
      z-index: -1;
    }
    
    .sale-button:hover::after {
      left: 100%;
    }
    
    /* Responsive styles */
    @media (max-width: 992px) {
      .sale-heading {
        font-size: 3rem;
      }
      
      .sale-description {
        font-size: 1.2rem;
      }
      
      .sale-deals {
        gap: 20px;
      }
    }
    
    @media (max-width: 768px) {
      .sale-heading {
        font-size: 2.5rem;
      }
      
      .countdown-item {
        min-width: 60px;
        padding: 10px;
      }
      
      .countdown-number {
        font-size: 1.5rem;
      }
      
      .sale-button {
        font-size: 1rem;
        padding: 12px 30px;
      }
    }
    
    @media (max-width: 576px) {
      .sale-section {
        padding: 40px 20px;
      }
      
      .sale-heading {
        font-size: 2rem;
      }
      
      .sale-description {
        font-size: 1rem;
      }
      
      .sale-deal {
        width: 100%;
      }
      
      .countdown {
        gap: 10px;
      }
      
      .countdown-item {
        min-width: 50px;
        padding: 8px;
      }
      
      .countdown-number {
        font-size: 1.2rem;
      }
    }
  </style>
  <section class="sale-section" id="sale">
    <video class="video-background" autoplay muted loop playsinline>
        <source src="Videos/video_20250406_203310_edit.mp4" type="video/mp4">
        <img src="/api/placeholder/1920/1080" alt="Sale Background">
      </video>
    <div class="video-overlay"></div>
    <div class="sale-content">
      <h2 class="sale-heading">Season Finale Sale</h2>
      <p class="sale-description">Grab the hottest Spike gear at unbeatable prices. Limited time offers on premium athletic wear and footwear. Don't miss out on these exclusive deals!</p>
      <div class="countdown-container">
        <h3 class="countdown-title">Sale Ends In:</h3>
        <div class="countdown">
          <div class="countdown-item" style="--delay: 0">
            <span class="countdown-number">2</span>
            <span class="countdown-label">Days</span>
          </div>
          <div class="countdown-item" style="--delay: 1">
            <span class="countdown-number">18</span>
            <span class="countdown-label">Hours</span>
          </div>
          <div class="countdown-item" style="--delay: 2">
            <span class="countdown-number">45</span>
            <span class="countdown-label">Minutes</span>
          </div>
          <div class="countdown-item" style="--delay: 3">
            <span class="countdown-number">30</span>
            <span class="countdown-label">Seconds</span>
          </div>
        </div>
      </div>
      <div class="sale-deals">
        <div class="sale-deal">
          <span class="discount-label">-40%</span>
          <img src="Images/sale1.jpeg" alt="Spike Elite Running Shoes">
          <h3 class="deal-title">Spike Elite Running Shoes</h3>
          <div class="deal-price">
            <span class="original-price">₱3,580.00</span>
            <span class="current-price">₱1,109.00</span>
          </div>
          <a href="#sale" class="deal-button">Shop Now</a>
        </div>
        
        <div class="sale-deal">
          <span class="discount-label">-35%</span>
          <img src="Images/sale2.jpg" alt="Spike Pro Basketball Jersey">
          <h3 class="deal-title">Spike Pro Basketball Jersey</h3>
          <div class="deal-price">
            <span class="original-price">₱5,490.00</span>
            <span class="current-price">₱1,458.50</span>
          </div>
          <a href="#sale" class="deal-button">Shop Now</a>
        </div>
        <div class="sale-deal">
          <span class="discount-label">-50%</span>
          <img src="Images/sale3.jpg" alt="Spike Air Training Pants">
          <h3 class="deal-title">Spike Air Training Pants</h3>
          <div class="deal-price">
            <span class="original-price">₱3,120.00</span>
            <span class="current-price">₱1,260.00</span>
          </div>
          <a href="#sale" class="deal-button">Shop Now</a>
        </div>
      </div>
      <div class="#sale">
        <a href="#sale" class="sale-button">Shop All Deals</a>
      </div>
    </div>
  </section>
  
    <div class="divider"></div>
    <section class="category-section snkrs-section" id="snkrs">
        <div class="section-header">
            <h2>SNKRS</h2>
            <p>Limited edition releases, exclusive collaborations, and the most coveted sneakers in the game. Don't miss your chance.</p>
        </div>
        
        <div class="product-grid">
            <div class="product-card" data-product-id="snkrs-1">
                <div class="product-image">
                    <img src="Images/snkr1.jpg" alt="Limited Edition Sneakers">
                    <span class="exclusive-label">Limited</span>
                </div>
                <div class="product-details">
                    <div class="release-date">Drops Apr 15</div>
                    <div class="product-name">Spike Air DN10 "Tokyo"</div>
                    <div class="product-category">Limited Edition</div>
                    <div class="product-price">₱1,999.99</div>
                    <div class="countdown">4 days remaining</div>
                    <a href="#" class="add-to-cart">Notify Me</a>
                </div>
            </div>
            <div class="product-card" data-product-id="snkrs-2">
                <div class="product-image">
                    <img src="Images/snkr2.jpg" alt="Collaboration Sneakers">
                    <span class="exclusive-label">Collab</span>
                </div>
                <div class="product-details">
                    <div class="release-date">Drops Apr 18</div>
                    <div class="product-name">Spike x Artiste "Vision"</div>
                    <div class="product-category">Artist Collaboration</div>
                    <div class="product-price">₱2,799.99</div>
                    <div class="countdown">7 days remaining</div>
                    <a href="#" class="add-to-cart">Notify Me</a>
                </div>
            </div>
            <div class="product-card" data-product-id="snkrs-3">
                <div class="product-image">
                    <img src="Images/snkr3.jpeg" alt="Retro Sneakers">
                    <span class="exclusive-label">Retro</span>
                </div>
                <div class="product-details">
                    <div class="release-date">Drops Apr 20</div>
                    <div class="product-name">Spike Classic '95</div>
                    <div class="product-category">Retro Release</div>
                    <div class="product-price">₱4,699.99</div>
                    <div class="countdown">9 days remaining</div>
                    <a href="#" class="add-to-cart">Notify Me</a>
                </div>
            </div>
        </div>
        
        <div class="section-footer">
            <a href="#snkrs" class="view-all-btn">Explore All SNKRS Releases</a>
        </div>
    </section>        
    <style>
        * {
          margin: 0;
          padding: 0;
          box-sizing: border-box;
          font-family: 'Arial', sans-serif;
        }
        
        body {
          min-height: 100vh;
          display: flex;
          flex-direction: column;
        }
        footer {
          background-color: #111;
          color: #fff;
          padding: 60px 0 30px;
          margin-top: auto;
        }
        
        .footer-content {
          max-width: 1300px;
          margin: 0 auto;
          display: flex;
          flex-wrap: wrap;
          justify-content: space-between;
          padding: 0 20px;
        }
        
        .footer-column {
          width: 16%;
          min-width: 160px;
          margin-bottom: 30px;
        }
        
        .footer-column h4 {
          font-size: 16px;
          margin-bottom: 20px;
          font-weight: 600;
          text-transform: uppercase;
          letter-spacing: 1px;
          position: relative;
        }
        
        .footer-column h4:after {
          content: '';
          position: absolute;
          left: 0;
          bottom: -8px;
          width: 30px;
          height: 2px;
          background-color: #f84c4c;
        }     
        .footer-column ul {
          list-style: none;
        }
        .footer-column ul li {
          margin-bottom: 12px;
        }
        .footer-column ul li a {
          color: #bbb;
          text-decoration: none;
          font-size: 14px;
          transition: all 0.3s ease;
        }
        .footer-column ul li a:hover {
          color: #fff;
          padding-left: 5px;
        }
        .social-media h4 {
          margin-bottom: 25px;
        }
        .social-icons {
          display: flex;
          gap: 10px;
          flex-wrap: wrap;
        }
        .social-link {
          display: flex;
          align-items: center;
          justify-content: center;
          width: 36px;
          height: 36px;
          background-color: #222;
          border-radius: 50%;
          color: #fff;
          font-size: 16px;
          transition: all 0.3s ease;
        }    
        .social-link:hover {
          background-color: #f84c4c;
          transform: translateY(-3px);
        }
        .copyright {
          text-align: center;
          padding-top: 30px;
          margin-top: 40px;
          border-top: 1px solid #222;
          font-size: 14px;
          color: #888;
        }
        @media (max-width: 768px) {
          .footer-column {
            width: 33.33%;
          }
        }     
        @media (max-width: 576px) {
          .footer-column {
            width: 50%;
          }
        }    
        @media (max-width: 480px) {
          .footer-column {
            width: 100%;
          }
        }
      </style>
        <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }   
        body {
            background-color: #000;
            color: white;
            overflow-x: hidden;
            display: flex;
            justify-content: center;
            min-height: 100vh;
        }
        .container {
            max-width: 1200px;
            width: 100%;
            margin: 0 auto;
            padding: 40px 20px;
            color: white;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        header {
            text-align: center;
            margin-bottom: 50px;
            animation: fadeInDown 1.2s ease-out;
            width: 100%; 
        }
        @keyframes titleUnderline {
            0% { width: 0; left: 50%; }
            100% { width: 80%; left: 10%; }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        .map-container {
            height: 400px;
            margin-bottom: 40px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transform: scale(0.95);
            opacity: 0;
            animation: scaleIn 0.8s 0.3s forwards;
            width: 100%;
        }       
        @keyframes scaleIn {
            from {
                transform: scale(0.95);
                opacity: 0;
            }
            to {
                transform: scale(1);
                opacity: 1;
            }
        }
        .stores-container {
            display: flex;
            justify-content: center; 
            flex-wrap: wrap;
            gap: 20px;
            perspective: 1000px;
            width: 100%; 
        }  
        .store-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            padding: 20px;
            width: calc(33.33% - 20px);
            min-width: 300px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
            animation: fadeIn 0.8s ease forwards;
            opacity: 0;
            position: relative;
            overflow: hidden;
            cursor: pointer;
            transform-style: preserve-3d;
            margin: 0 auto;
        }

        .store-card:hover {
            transform: translateY(-5px) rotateX(3deg) rotateY(3deg);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3), 
                        0 0 20px rgba(0, 0, 0, 0.3);
        }
        
        .store-card:nth-child(1) {
            animation-delay: 0.4s;
        }
        
        .store-card:nth-child(2) {
            animation-delay: 0.7s;
        }
        
        .store-card:nth-child(3) {
            animation-delay: 1s;
        }

        .store-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(
                circle at center,
                rgba(255,255,255,0.2) 0%,
                rgba(255,255,255,0) 60%
            );
            transform: scale(0);
            opacity: 0;
            transition: transform 0.3s, opacity 0.3s;
            pointer-events: none;
        }
        
        .store-card:hover::before {
            transform: scale(1);
            opacity: 1;
        }

        .store-toggle {
            position: absolute;
            opacity: 0;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            margin: 0;
            cursor: pointer;
            z-index: 10;
        }
        .store-toggle:checked ~ .store-content {
            transform: translateZ(20px);
            transition: transform 0.5s ease;
        }
        .store-toggle:checked ~ .featured-badge {
            opacity: 1;
            transform: scale(1) rotate(0deg);
            animation: badge-pulse 2s infinite;
        }
        .click-ring {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            transform: translate(-50%, -50%);
            z-index: 3;
            pointer-events: none;
        }
        
        .store-toggle:checked ~ .click-ring {
            animation: ring-expand 0.8s forwards;
        }
        
        @keyframes ring-expand {
            0% {
                width: 0;
                height: 0;
                opacity: 0.6;
            }
            100% {
                width: 300px;
                height: 300px;
                opacity: 0;
            }
        }

        .store-toggle:checked ~ .store-glow {
            opacity: 1;
            animation: glow-pulse 2s infinite;
        }

        .store-toggle:checked ~ .store-content {
            animation: card-activateEffect 0.8s forwards;
        }
        
        @keyframes card-activateEffect {
            0% {
                transform: rotateX(0deg) scale(1) translateZ(0);
            }
            30% {
                transform: rotateX(10deg) scale(1.03) translateZ(25px);
            }
            60% {
                transform: rotateX(5deg) scale(1.05) translateZ(50px);
            }
            100% {
                transform: rotateX(0deg) scale(1.05) translateZ(30px);
            }
        }

        .store-toggle:checked ~ .store-content {
            animation: float 5s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px) translateZ(30px); }
            50% { transform: translateY(-10px) translateZ(30px); }
            100% { transform: translateY(0px) translateZ(30px); }
        }

        .store-toggle:checked ~ .store-content .store-image {
            animation: image-bounce 0.8s forwards;
        }
        
        @keyframes image-bounce {
            0% {
                transform: translateY(0);
            }
            30% {
                transform: translateY(-15px);
            }
            50% {
                transform: translateY(-5px);
            }
            70% {
                transform: translateY(-10px);
            }
            100% {
                transform: translateY(-8px);
                box-shadow: 0 15px 20px rgba(0, 0, 0, 0.3);
            }
        }
        .store-toggle:checked ~ .store-content .store-name {
            animation: text-highlight 0.5s forwards;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }
        @keyframes text-highlight {
            0% {
                transform: scale(1);
                color: white;
            }
            50% {
                transform: scale(1.05);
                color: #f0f0f0;
            }
            100% {
                transform: scale(1.02);
                color: #ffffff;
            }
        }
        .store-toggle:checked ~ .store-content .view-button {
            animation: button-pulse 1.5s infinite;
            background: #000000;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
        }
        
        @keyframes button-pulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
            }
            50% {
                transform: scale(1.05);
                box-shadow: 0 0 25px rgba(0, 0, 0, 0.7);
            }
            100% {
                transform: scale(1);
                box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
            }
        }
        .store-glow {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            box-shadow: inset 0 0 30px rgba(255, 255, 255, 0.3);
            border-radius: 10px;
            opacity: 0;
            z-index: 2;
            pointer-events: none;
        }
        @keyframes glow-pulse {
            0% {
                box-shadow: inset 0 0 30px rgba(255, 255, 255, 0.3);
            }
            50% {
                box-shadow: inset 0 0 50px rgba(255, 255, 255, 0.5);
            }
            100% {
                box-shadow: inset 0 0 30px rgba(255, 255, 255, 0.3);
            }
        }
        .store-toggle:checked ~ .particles .particle {
            animation: particle-move 1s forwards;
        }
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 4;
        }
        .particle {
            position: absolute;
            width: 8px;
            height: 8px;
            background: white;
            border-radius: 50%;
            opacity: 0;
        }    
        .particle:nth-child(1) {
            top: 20%;
            left: 20%;
        }
        .particle:nth-child(2) {
            top: 20%;
            right: 20%;
        }
        .particle:nth-child(3) {
            bottom: 20%;
            left: 20%;
        }
        .particle:nth-child(4) {
            bottom: 20%;
            right: 20%;
        }
        .particle:nth-child(5) {
            top: 50%;
            left: 10%;
        }
        .particle:nth-child(6) {
            top: 50%;
            right: 10%;
        }
        @keyframes particle-move {
            0% {
                transform: scale(0);
                opacity: 0;
            }
            10% {
                transform: scale(1);
                opacity: 0.8;
            }
            100% {
                transform: scale(0);
                opacity: 0;
                top: 50%;
                left: 50%;
            }
        }
        .featured-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: linear-gradient(135deg, #ffcc00, #ff9900);
            color: black;
            font-weight: bold;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 12px;
            opacity: 0;
            transform: scale(0) rotate(45deg);
            transition: all 0.5s cubic-bezier(0.68, -0.55, 0.27, 1.55);
            z-index: 5;
            box-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
        }
        @keyframes badge-pulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
            }
            50% {
                transform: scale(1.1);
                box-shadow: 0 0 20px rgba(255, 204, 0, 0.7);
            }
            100% {
                transform: scale(1);
                box-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
            }
        }
        .store-content {
            position: relative;
            z-index: 1;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        } 
        .store-image {
            width: 100%;
            height: 180px;
            border-radius: 8px;
            object-fit: cover;
            margin-bottom: 15px;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }     
        .store-card:hover .store-image {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }    
        .store-name {
            font-size: 22px;
            margin-bottom: 10px;
            color: white;
            transition: all 0.3s ease;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
        } 
        .store-details {
            margin-bottom: 15px;
            color: #f7f7f7;
            transition: all 0.3s ease;
            transform: translateY(0);
        }
        .store-card:hover .store-details {
            transform: translateY(-3px);
        }
        .store-hours {
            color: #f7f7f7;
            font-size: 14px;
            margin-bottom: 15px;
            transition: all 0.3s ease;
            opacity: 0.8;
        }
        .store-card:hover .store-hours {
            opacity: 1;
        }
        .view-button {
            display: inline-block;
            background: #f95738;
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .view-button:hover {
            background: #e24327;
            transform: translateY(-3px);
            box-shadow: 0 7px 10px rgba(0, 0, 0, 0.2);
        }
        
        .view-button::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                90deg, 
                rgba(255,255,255,0) 0%, 
                rgba(255,255,255,0.3) 50%, 
                rgba(255,255,255,0) 100%
            );
            transition: left 0.5s ease;
        }
        
        .view-button:hover::after {
            left: 100%;
        }

        @keyframes scrollIn {
            from { 
                transform: translateY(100px);
                opacity: 0;
            }
            to { 
                transform: translateY(0);
                opacity: 1;
            }
        }
        @media (max-width: 992px) {
            .stores-container {
                justify-content: center;
            }
            
            .store-card {
                width: calc(50% - 20px);
            }
        }
        @media (max-width: 768px) {
            .store-card {
                width: 100%;
                min-width: 250px;
            }
        }
    </style>
    <div class="container" id="findStore">
            <div class="map-container">
                <img src="Images/Screenshot (100).png" alt="Map of Nike Stores in CDO" style="width: 100%; height: 100%; object-fit: cover;">
            </div>
            <div class="stores-container">
                <div class="store-card">
                    <input type="checkbox" class="store-toggle" id="store1">
                    <div class="click-ring"></div>
                    <div class="store-glow"></div>
                    <div class="featured-badge">FEATURED</div>
                    <div class="particles">
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                    </div>
                    <div class="store-content">
                        <img src="Images/nike centrio.jpg" alt="Nike CDO Centrio Mall" class="store-image">
                        <h2 class="store-name">Spike CDO Centrio Mall</h2>
                        <p class="store-details">Located at the heart of CDO, our flagship store offers the latest Spike collections including basketball, running, and lifestyle products.</p>
                        <p class="store-hours">
                            <strong>Operating Hours:</strong><br>
                            Monday - Sunday: 10:00 AM - 9:00 PM
                        </p>
                        <label for="store1" class="view-button">View Store Details</label>
                    </div>
                </div>  
                <div class="store-card">
                    <input type="checkbox" class="store-toggle" id="store2">
                    <div class="click-ring"></div>
                    <div class="store-glow"></div>
                    <div class="featured-badge">FEATURED</div>
                    <div class="particles">
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                    </div>
                    <div class="store-content">
                        <img src="Images/sm downtown.jpg" alt="Nike Factory Store - SM CDO Downtown Premier" class="store-image">
                        <h2 class="store-name">Spike Factory Store - SM CDO Downtown Premier</h2>
                        <p class="store-details">Our outlet store offering great deals on Spike products, perfect for athletes and fashion enthusiasts looking for quality sportswear.</p>
                        <p class="store-hours">
                            <strong>Operating Hours:</strong><br>
                            Monday - Sunday: 10:00 AM - 9:00 PM
                        </p>
                        <label for="store2" class="view-button">View Store Details</label>
                    </div>
                </div>
                <div class="store-card">
                    <input type="checkbox" class="store-toggle" id="store3">
                    <div class="click-ring"></div>
                    <div class="store-glow"></div>
                    <div class="featured-badge">FEATURED</div>
                    <div class="particles">
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                        <div class="particle"></div>
                    </div>
                    <div class="store-content">
                        <img src="Images/nike ketkai.jpg" alt="Nike Concept Store - Limketkai Center" class="store-image">
                        <h2 class="store-name">Spike Concept Store - Limketkai Center</h2>
                        <p class="store-details">Experience Spike's innovative products and technologies in our concept store, featuring specialized zones for different sports.</p>
                        <p class="store-hours">
                            <strong>Operating Hours:</strong><br>
                            Monday - Sunday: 10:00 AM - 9:00 PM
                        </p>
                        <label for="store3" class="view-button">View Store Details</label>
                    </div>
                </div>
            </div>
        </div>
      <footer>
        <div class="footer-content">
          <div class="footer-column">
            <h4>Products</h4>
            <ul>
              <li><a href="/shoes">Shoes</a></li>
              <li><a href="/clothing">Clothing</a></li>
              <li><a href="/accessories">Accessories</a></li>
              <li><a href="/new-releases">New Releases</a></li>
              <li><a href="/best-sellers">Best Sellers</a></li>
              <li><a href="/sale">Sale</a></li>
            </ul>
          </div>
          <div class="footer-column">
            <h4>Sports</h4>
            <ul>
              <li><a href="/running">Running</a></li>
              <li><a href="/basketball">Basketball</a></li>
              <li><a href="/soccer">Soccer</a></li>
              <li><a href="/training">Training & Gym</a></li>
              <li><a href="/tennis">Tennis</a></li>
              <li><a href="/golf">Golf</a></li>
            </ul>
          </div>
          <div class="footer-column">
            <h4>Collections</h4>
            <ul>
              <li><a href="/spike-air">Spike Air</a></li>
              <li><a href="/spike-elite">Spike Elite</a></li>
              <li><a href="/spike-pro">Spike Pro</a></li>
              <li><a href="/spike-originals">Spike Originals</a></li>
              <li><a href="/customization">Customization</a></li>
            </ul>
          </div>
          <div class="footer-column">
            <h4>Support</h4>
            <ul>
              <li><a href="/help">Help</a></li>
              <li><a href="/shipping">Shipping & Delivery</a></li>
              <li><a href="/returns">Returns</a></li>
              <li><a href="/sizing">Sizing Charts</a></li>
              <li><a href="/contact">Contact Us</a></li>
            </ul>
          </div>
          <div class="footer-column">
            <h4>About Spike</h4>
            <ul>
              <li><a href="/about">Our Story</a></li>
              <li><a href="/careers">Careers</a></li>
              <li><a href="/news">News</a></li>
              <li><a href="/sustainability">Sustainability</a></li>
              <li><a href="/investors">Investors</a></li>
            </ul>
          </div>
          <div class="footer-column social-media">
            <h4>Follow Us</h4>
            <div class="social-icons">
              <a href="#" class="social-link"><i class="fa fa-facebook"></i></a>
              <a href="#" class="social-link"><i class="fa fa-twitter"></i></a>
              <a href="#" class="social-link"><i class="fa fa-instagram"></i></a>
              <a href="#" class="social-link"><i class="fa fa-instagram"></i></a>
            </div>
          </div>
        </div>
        <div class="copyright">
          © 2025 Spike Athletics. All Rights Reserved.
        </div>
      </footer>
