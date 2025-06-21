<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WAQAS | Luxury Cosmetics</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --rose-quartz: #F7CAC9;
            --pearl: #F4F4F4;
            --champagne: #D4AF37;
            --mauve: #AE8E8C;
            --plum: #6B3FA0;
            --charcoal: #333333;
            --taupe: #8A7F80;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        body {
            background-color: var(--pearl);
            color: var(--charcoal);
            overflow-x: hidden;
        }

        /* Header Styles */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.05);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 300;
            color: var(--plum);
            letter-spacing: 2px;
        }

        .logo span {
            font-weight: 600;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 2rem;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--charcoal);
            font-weight: 500;
            font-size: 0.9rem;
            letter-spacing: 1px;
            transition: color 0.3s;
            position: relative;
        }

        nav ul li a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 1px;
            bottom: -5px;
            left: 0;
            background-color: var(--champagne);
            transition: width 0.3s;
        }

        nav ul li a:hover {
            color: var(--mauve);
        }

        nav ul li a:hover:after {
            width: 100%;
        }

        .nav-icons {
            display: flex;
            align-items: center;
        }

        .nav-icons a {
            color: var(--charcoal);
            margin-left: 1.5rem;
            font-size: 1.1rem;
            transition: color 0.3s;
        }

        .nav-icons a:hover {
            color: var(--plum);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--plum);
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 0.6rem;
            font-weight: bold;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(247, 202, 201, 0.2), rgba(244, 244, 244, 0.8)), 
                        url('https://images.unsplash.com/photo-1522335789203-aabd1fc54bc9?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 10%;
            margin-top: 70px;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 300;
            margin-bottom: 1.5rem;
            color: var(--charcoal);
            letter-spacing: 3px;
        }

        .hero p {
            font-size: 1.1rem;
            max-width: 600px;
            margin-bottom: 2.5rem;
            color: var(--taupe);
            line-height: 1.6;
        }

        .btn {
            padding: 12px 30px;
            background-color: var(--plum);
            color: white;
            border: none;
            border-radius: 30px;
            font-size: 0.9rem;
            letter-spacing: 1px;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-weight: 500;
        }

        .btn:hover {
            background-color: var(--champagne);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(107, 63, 160, 0.2);
        }

        /* Categories Section */
        .categories {
            padding: 5rem 10%;
            text-align: center;
        }

        .section-title {
            font-size: 2rem;
            font-weight: 300;
            margin-bottom: 3rem;
            color: var(--charcoal);
            position: relative;
            display: inline-block;
        }

        .section-title:after {
            content: '';
            position: absolute;
            width: 50%;
            height: 1px;
            bottom: -10px;
            left: 25%;
            background-color: var(--champagne);
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .category-card {
            position: relative;
            height: 400px;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .category-card:hover {
            transform: translateY(-10px);
        }

        .category-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .category-card:hover .category-img {
            transform: scale(1.05);
        }

        .category-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0, 0, 0, 0.7), transparent);
            padding: 2rem;
            color: white;
            text-align: left;
        }

        .category-overlay h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            font-weight: 400;
        }

        .category-overlay p {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-bottom: 1rem;
        }

        /* Featured Products */
        .featured {
            padding: 5rem 10%;
            background-color: white;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .product-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: all 0.3s;
            position: relative;
        }

        .product-card:hover {
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px);
        }

        .product-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--plum);
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.7rem;
            font-weight: 500;
        }

        .product-img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-category {
            color: var(--taupe);
            font-size: 0.8rem;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .product-title {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .product-price {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--charcoal);
            margin-bottom: 1rem;
        }

        .product-rating {
            color: var(--champagne);
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        .add-to-cart {
            width: 100%;
            padding: 10px;
            background-color: var(--rose-quartz);
            color: var(--charcoal);
            border: none;
            border-radius: 5px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s;
        }

        .add-to-cart:hover {
            background-color: var(--plum);
            color: white;
        }

        /* Newsletter */
        .newsletter {
            padding: 5rem 10%;
            background-color: var(--rose-quartz);
            text-align: center;
        }

        .newsletter p {
            max-width: 600px;
            margin: 0 auto 2rem;
            color: var(--charcoal);
        }

        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }

        .newsletter-form input {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 30px 0 0 30px;
            font-size: 0.9rem;
        }

        .newsletter-form button {
            padding: 15px 25px;
            background-color: var(--plum);
            color: white;
            border: none;
            border-radius: 0 30px 30px 0;
            cursor: pointer;
            font-size: 0.9rem;
            font-weight: 500;
            transition: background-color 0.3s;
        }

        .newsletter-form button:hover {
            background-color: var(--champagne);
        }

        /* Footer */
        footer {
            background-color: var(--charcoal);
            color: white;
            padding: 5rem 10% 2rem;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .footer-col h3 {
            font-size: 1.2rem;
            font-weight: 500;
            margin-bottom: 1.5rem;
            position: relative;
        }

        .footer-col h3:after {
            content: '';
            position: absolute;
            width: 40px;
            height: 1px;
            bottom: -8px;
            left: 0;
            background-color: var(--champagne);
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col ul li {
            margin-bottom: 0.8rem;
        }

        .footer-col ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s;
            font-size: 0.9rem;
        }

        .footer-col ul li a:hover {
            color: var(--rose-quartz);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            color: white;
            background-color: rgba(255, 255, 255, 0.1);
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 0.3s;
        }

        .social-links a:hover {
            background-color: var(--plum);
            transform: translateY(-3px);
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 2rem;
            text-align: center;
            font-size: 0.8rem;
            color: #999;
        }

        /* Shopping Cart Sidebar */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -400px;
            width: 400px;
            height: 100vh;
            background-color: white;
            box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
            z-index: 1001;
            transition: right 0.3s;
            padding: 2rem;
            overflow-y: auto;
        }

        .cart-sidebar.active {
            right: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .cart-header h2 {
            font-size: 1.5rem;
            font-weight: 400;
        }

        .close-cart {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--taupe);
        }

        .cart-items {
            margin-bottom: 2rem;
        }

        .cart-item {
            display: flex;
            margin-bottom: 1.5rem;
            padding-bottom: 1.5rem;
            border-bottom: 1px solid #eee;
        }

        .cart-item-img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 5px;
            margin-right: 1rem;
        }

        .cart-item-details {
            flex: 1;
        }

        .cart-item-title {
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .cart-item-price {
            font-size: 0.9rem;
            color: var(--taupe);
            margin-bottom: 0.5rem;
        }

        .cart-item-quantity {
            display: flex;
            align-items: center;
        }

        .quantity-btn {
            width: 25px;
            height: 25px;
            background-color: #f5f5f5;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .quantity {
            margin: 0 10px;
        }

        .remove-item {
            color: var(--taupe);
            font-size: 0.8rem;
            cursor: pointer;
            margin-top: 0.5rem;
            display: inline-block;
        }

        .cart-total {
            margin-bottom: 2rem;
            padding-top: 1rem;
            border-top: 1px solid #eee;
        }

        .cart-total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .cart-total-row.total {
            font-weight: 600;
            font-size: 1.1rem;
            margin-top: 1rem;
        }

        .checkout-btn {
            width: 100%;
            padding: 15px;
            background-color: var(--plum);
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: 500;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .checkout-btn:hover {
            background-color: var(--champagne);
        }

        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }

        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        /* Responsive Styles */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .category-grid {
                grid-template-columns: 1fr;
            }

            .cart-sidebar {
                width: 100%;
                right: -100%;
            }

            .newsletter-form {
                flex-direction: column;
            }

            .newsletter-form input {
                border-radius: 30px;
                margin-bottom: 1rem;
            }

            .newsletter-form button {
                border-radius: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="logo">WAQAS</div>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Skincare</a></li>
                <li><a href="#">Makeup</a></li>
                <li><a href="#">Fragrance</a></li>
                <li><a href="#">About</a></li>
            </ul>
        </nav>
        <div class="nav-icons">
            <a href="#"><i class="fas fa-search"></i></a>
            <a href="#"><i class="fas fa-user"></i></a>
            <a href="#" class="cart-icon">
                <i class="fas fa-shopping-bag"></i>
                <span class="cart-count">0</span>
            </a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1>Elevate Your Beauty Ritual</h1>
        <p>Discover our luxurious collection of clean, high-performance skincare, makeup, and fragrances crafted to enhance your natural beauty.</p>
        <button class="btn">Shop Now</button>
    </section>

    <!-- Categories Section -->
    <section class="categories">
        <h2 class="section-title">Our Collections</h2>
        <div class="category-grid">
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1571781926291-c477ebfd024b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Skincare" class="category-img">
                <div class="category-overlay">
                    <h3>Skincare</h3>
                    <p>Nourish and rejuvenate your skin with our science-backed formulations</p>
                    <button class="btn">Explore</button>
                </div>
            </div>
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1522337360788-8b13dee7a37e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Makeup" class="category-img">
                <div class="category-overlay">
                    <h3>Makeup</h3>
                    <p>Enhance your natural beauty with our high-performance cosmetics</p>
                    <button class="btn">Explore</button>
                </div>
            </div>
            <div class="category-card">
                <img src="https://images.unsplash.com/photo-1592945403244-b3fbafd7f539?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Fragrance" class="category-img">
                <div class="category-overlay">
                    <h3>Fragrance</h3>
                    <p>Signature scents that evoke emotion and create lasting impressions</p>
                    <button class="btn">Explore</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products -->
    <section class="featured">
        <h2 class="section-title">Best Sellers</h2>
        <div class="product-grid">
            <div class="product-card">
                <span class="product-badge">Bestseller</span>
                <img src="https://images.unsplash.com/photo-1556228578-8c89e6adf883?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Hydrating Serum" class="product-img">
                <div class="product-info">
                    <p class="product-category">Skincare</p>
                    <h3 class="product-title">Luminous Hydrating Serum</h3>
                    <p class="product-price">$68.00</p>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <span>(142)</span>
                    </div>
                    <button class="add-to-cart" data-id="1" data-name="Luminous Hydrating Serum" data-price="68.00" data-image="https://images.unsplash.com/photo-1556228578-8c89e6adf883?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1596755094514-f87e34085b2c?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Lipstick" class="product-img">
                <div class="product-info">
                    <p class="product-category">Makeup</p>
                    <h3 class="product-title">Velvet Matte Lipstick</h3>
                    <p class="product-price">$32.00</p>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="far fa-star"></i>
                        <span>(89)</span>
                    </div>
                    <button class="add-to-cart" data-id="2" data-name="Velvet Matte Lipstick" data-price="32.00" data-image="https://images.unsplash.com/photo-1596755094514-f87e34085b2c?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <span class="product-badge">New</span>
                <img src="https://images.unsplash.com/photo-1615368144592-6a8a1f43f0d3?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Perfume" class="product-img">
                <div class="product-info">
                    <p class="product-category">Fragrance</p>
                    <h3 class="product-title">Nocturne Eau de Parfum</h3>
                    <p class="product-price">$120.00</p>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <span>(56)</span>
                    </div>
                    <button class="add-to-cart" data-id="3" data-name="Nocturne Eau de Parfum" data-price="120.00" data-image="https://images.unsplash.com/photo-1615368144592-6a8a1f43f0d3?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80">Add to Cart</button>
                </div>
            </div>
            <div class="product-card">
                <img src="https://images.unsplash.com/photo-1571781926291-c477ebfd024b?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80" alt="Eye Cream" class="product-img">
                <div class="product-info">
                    <p class="product-category">Skincare</p>
                    <h3 class="product-title">Revitalizing Eye Cream</h3>
                    <p class="product-price">$52.00</p>
                    <div class="product-rating">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star-half-alt"></i>
                        <span>(76)</span>
                    </div>
                    <button class="add-to-cart" data-id="4" data-name="Revitalizing Eye Cream" data-price="52.00" data-image="https://images.unsplash.com/photo-1571781926291-c477ebfd024b?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80">Add to Cart</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <h2 class="section-title">Join Our Community</h2>
        <p>Subscribe to receive exclusive offers, beauty tips, and early access to new products.</p>
        <form class="newsletter-form">
            <input type="email" placeholder="Your email address" required>
            <button type="submit">Subscribe</button>
        </form>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-grid">
            <div class="footer-col">
                <h3>Shop</h3>
                <ul>
                    <li><a href="#">Skincare</a></li>
                    <li><a href="#">Makeup</a></li>
                    <li><a href="#">Fragrance</a></li>
                    <li><a href="#">Best Sellers</a></li>
                    <li><a href="#">New Arrivals</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h3>About</h3>
                <ul>
                    <li><a href="#">Our Story</a></li>
                    <li><a href="#">Ingredients</a></li>
                    <li><a href="#">Sustainability</a></li>
                    <li><a href="#">Press</a></li>
                    <li><a href="#">Careers</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h3>Help</h3>
                <ul>
                    <li><a href="#">Contact Us</a></li>
                    <li><a href="#">FAQs</a></li>
                    <li><a href="#">Shipping & Returns</a></li>
                    <li><a href="#">Track Order</a></li>
                    <li><a href="#">Gift Cards</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h3>Connect</h3>
                <p>Follow us for beauty inspiration and updates.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-pinterest-p"></i></a>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2023 WAQAS Cosmetics. All rights reserved. | <a href="#">Privacy Policy</a> | <a href="#">Terms of Service</a></p>
        </div>
    </footer>

    <!-- Shopping Cart Sidebar -->
    <div class="cart-sidebar">
        <div class="cart-header">
            <h2>Your Bag</h2>
            <button class="close-cart">&times;</button>
        </div>
        <div class="cart-items">
            <!-- Cart items will be added here dynamically -->
        </div>
        <div class="cart-total">
            <div class="cart-total-row">
                <span>Subtotal</span>
                <span class="subtotal">$0.00</span>
            </div>
            <div class="cart-total-row">
                <span>Shipping</span>
                <span>Calculated at checkout</span>
            </div>
            <div class="cart-total-row total">
                <span>Total</span>
                <span class="total-price">$0.00</span>
            </div>
        </div>
        <button class="checkout-btn">Proceed to Checkout</button>
    </div>
    <div class="overlay"></div>

    <script>
        // Shopping Cart Functionality
        document.addEventListener('DOMContentLoaded', function() {
            const cartIcon = document.querySelector('.cart-icon');
            const cartSidebar = document.querySelector('.cart-sidebar');
            const closeCart = document.querySelector('.close-cart');
            const overlay = document.querySelector('.overlay');
            const addToCartBtns = document.querySelectorAll('.add-to-cart');
            const cartItemsContainer = document.querySelector('.cart-items');
            const cartCount = document.querySelector('.cart-count');
            const subtotalEl = document.querySelector('.subtotal');
            const totalPriceEl = document.querySelector('.total-price');

            let cart = [];

            // Toggle Cart
            cartIcon.addEventListener('click', () => {
                cartSidebar.classList.add('active');
                overlay.classList.add('active');
            });

            closeCart.addEventListener('click', () => {
                cartSidebar.classList.remove('active');
                overlay.classList.remove('active');
            });

            overlay.addEventListener('click', () => {
                cartSidebar.classList.remove('active');
                overlay.classList.remove('active');
            });

            // Add to Cart
            addToCartBtns.forEach(btn => {
                btn.addEventListener('click', addToCart);
            });

            function addToCart(e) {
                const btn = e.target;
                const id = btn.getAttribute('data-id');
                const name = btn.getAttribute('data-name');
                const price = btn.getAttribute('data-price');
                const image = btn.getAttribute('data-image');

                // Check if item already in cart
                const existingItem = cart.find(item => item.id === id);

                if (existingItem) {
                    existingItem.quantity += 1;
                } else {
                    cart.push({
                        id,
                        name,
                        price,
                        image,
                        quantity: 1
                    });
                }

                updateCart();
                cartSidebar.classList.add('active');
                overlay.classList.add('active');

                // Add animation
                btn.textContent = 'Added!';
                setTimeout(() => {
                    btn.textContent = 'Add to Cart';
                }, 1000);
            }

            // Update Cart
            function updateCart() {
                renderCartItems();
                renderSubtotal();
                renderCartCount();
            }

            // Render Cart Items
            function renderCartItems() {
                cartItemsContainer.innerHTML = '';

                if (cart.length === 0) {
                    cartItemsContainer.innerHTML = '<p>Your bag is empty</p>';
                    return;
                }

                cart.forEach(item => {
                    const cartItemEl = document.createElement('div');
                    cartItemEl.classList.add('cart-item');
                    cartItemEl.innerHTML = `
                        <img src="${item.image}" alt="${item.name}" class="cart-item-img">
                        <div class="cart-item-details">
                            <h3 class="cart-item-title">${item.name}</h3>
                            <p class="cart-item-price">$${item.price}</p>
                            <div class="cart-item-quantity">
                                <button class="quantity-btn minus" data-id="${item.id}">-</button>
                                <span class="quantity">${item.quantity}</span>
                                <button class="quantity-btn plus" data-id="${item.id}">+</button>
                            </div>
                            <span class="remove-item" data-id="${item.id}">Remove</span>
                        </div>
                    `;
                    cartItemsContainer.appendChild(cartItemEl);
                });

                // Add event listeners to quantity buttons
                document.querySelectorAll('.quantity-btn.minus').forEach(btn => {
                    btn.addEventListener('click', decreaseQuantity);
                });

                document.querySelectorAll('.quantity-btn.plus').forEach(btn => {
                    btn.addEventListener('click', increaseQuantity);
                });

                document.querySelectorAll('.remove-item').forEach(btn => {
                    btn.addEventListener('click', removeItem);
                });
            }

            // Render Subtotal
            function renderSubtotal() {
                let subtotal = 0;
                cart.forEach(item => {
                    subtotal += item.price * item.quantity;
                });
                subtotalEl.textContent = `$${subtotal.toFixed(2)}`;
                totalPriceEl.textContent = `$${subtotal.toFixed(2)}`;
            }

            // Render Cart Count
            function renderCartCount() {
                let count = 0;
                cart.forEach(item => {
                    count += item.quantity;
                });
                cartCount.textContent = count;
            }

            // Quantity Functions
            function decreaseQuantity(e) {
                const id = e.target.getAttribute('data-id');
                const item = cart.find(item => item.id === id);

                if (item.quantity > 1) {
                    item.quantity -= 1;
                } else {
                    cart = cart.filter(item => item.id !== id);
                }

                updateCart();
            }

            function increaseQuantity(e) {
                const id = e.target.getAttribute('data-id');
                const item = cart.find(item => item.id === id);
                item.quantity += 1;
                updateCart();
            }

            function removeItem(e) {
                const id = e.target.getAttribute('data-id');
                cart = cart.filter(item => item.id !== id);
                updateCart();
            }
        });
    </script>
</body>
</html>
