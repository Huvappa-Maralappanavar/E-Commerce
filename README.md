<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AudioHub - Premium Audio Store</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background-color: #f8f9fa;
            color: #333;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            cursor: pointer;
        }
        
        .logo i {
            margin-right: 10px;
        }
        
        /* Navigation */
        nav {
            display: flex;
            align-items: center;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            align-items: center;
        }
        
        .nav-links li {
            margin-left: 1.5rem;
            display: flex;
            align-items: center;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            display: flex;
            align-items: center;
        }
        
        .nav-links a:hover, .nav-links a.active {
            background: rgba(255,255,255,0.1);
        }
        
        /* Cart Icon */
        .cart-link {
            position: relative;
            display: flex;
            align-items: center;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: #ff4757;
            color: white;
            border-radius: 50%;
            padding: 3px 8px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Main Content */
        main {
            padding: 2rem 0;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        
        /* Page Sections */
        .page-section {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .active-section {
            display: block;
        }
        
        /* Homepage Styles */
        .hero-section {
            text-align: center;
            padding: 4rem 2rem;
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            border-radius: 15px;
            color: white;
            margin-bottom: 3rem;
        }
        
        .hero-title {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero-subtitle {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .cta-button {
            background: white;
            color: #6e8efb;
            padding: 1rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        .featured-section {
            margin: 3rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 2rem;
            font-size: 2rem;
            color: #333;
            position: relative;
        }
        
        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            margin: 0.5rem auto 0;
            border-radius: 2px;
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        
        /* Product Card */
        .product-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
            cursor: pointer;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
        }
        
        .product-image-container {
            height: 200px;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            background: #f5f5f5;
        }
        
        .product-image {
            max-width: 80%;
            max-height: 80%;
            object-fit: contain;
            transition: transform 0.3s ease;
        }
        
        .product-info {
            padding: 1.5rem;
        }
        
        .product-title {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }
        
        .product-price {
            font-size: 1.2rem;
            color: #6e8efb;
            font-weight: 700;
        }
        
        /* Products Page */
        .products-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
        }
        
        /* Product Page */
        .product-detail {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        
        .product-gallery {
            position: relative;
        }
        
        .main-image {
            width: 100%;
            height: 400px;
            object-fit: contain;
            background: #f5f5f5;
            border-radius: 10px;
        }
        
        .product-content {
            padding: 2rem;
        }
        
        .product-brand {
            color: #6e8efb;
            font-weight: 600;
            margin-bottom: 1rem;
            display: block;
        }
        
        .product-description {
            line-height: 1.6;
            margin: 2rem 0;
            color: #666;
        }
        
        .add-to-cart-lg {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 5px;
            font-size: 1.1rem;
            cursor: pointer;
            width: 100%;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        
        .add-to-cart-lg:hover {
            opacity: 0.9;
        }
        
        /* Cart Page */
        .cart-page {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 2rem;
        }
        
        .cart-items-section {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .cart-item {
            display: flex;
            padding: 1.5rem;
            border-bottom: 1px solid #eee;
        }
        
        .cart-item-image {
            width: 120px;
            height: 120px;
            object-fit: contain;
            margin-right: 1.5rem;
            background: #f5f5f5;
            border-radius: 5px;
        }
        
        .cart-item-details {
            flex: 1;
        }
        
        .cart-item-title {
            font-weight: 600;
            margin-bottom: 0.5rem;
        }
        
        .cart-item-price {
            color: #6e8efb;
            font-weight: 600;
        }
        
        .cart-item-quantity {
            display: flex;
            align-items: center;
            margin-top: 0.5rem;
        }
        
        .quantity-btn {
            background: #f5f5f5;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            font-weight: bold;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .quantity-value {
            margin: 0 15px;
            font-weight: 600;
        }
        
        .remove-item {
            background: none;
            border: none;
            color: #ff4757;
            cursor: pointer;
            margin-left: auto;
            align-self: flex-start;
            font-weight: 600;
        }
        
        .cart-summary {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            height: fit-content;
        }
        
        .summary-title {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #333;
        }
        
        .summary-item {
            display: flex;
            justify-content: space-between;
            margin: 1rem 0;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }
        
        .summary-total {
            font-weight: 700;
            font-size: 1.2rem;
            margin-top: 1.5rem;
        }
        
        .checkout-btn {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            border: none;
            padding: 1rem;
            border-radius: 5px;
            font-size: 1.1rem;
            cursor: pointer;
            width: 100%;
            margin-top: 2rem;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .checkout-btn:hover {
            opacity: 0.9;
        }
        
        /* Checkout Form */
        .checkout-form {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            margin-top: 2rem;
        }
        
        .form-group {
            margin-bottom: 1.5rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #333;
        }
        
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 0.8rem 1rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            border-color: #6e8efb;
            outline: none;
            box-shadow: 0 0 0 3px rgba(110, 142, 251, 0.2);
        }
        
        .form-group textarea {
            min-height: 100px;
            resize: vertical;
        }
        
        /* You Page */
        .account-container {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 2rem;
        }
        
        .account-nav {
            background: white;
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            height: fit-content;
        }
        
        .nav-item {
            padding: 1rem;
            margin: 0.5rem 0;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .nav-item.active {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
        }
        
        .account-content {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .order-card {
            border: 1px solid #eee;
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
        }
        
        .order-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }
        
        .order-status {
            color: #28a745;
            font-weight: 600;
        }
        
        .order-product {
            display: flex;
            align-items: center;
            margin: 1rem 0;
        }
        
        .order-product img {
            width: 80px;
            height: 80px;
            object-fit: contain;
            margin-right: 1rem;
            background: #f5f5f5;
            border-radius: 5px;
            padding: 0.5rem;
        }
        
        .reward-card {
            background: #f9f9f9;
            padding: 1.5rem;
            border-radius: 10px;
            margin-bottom: 1rem;
        }
        
        .reward-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: #6e8efb;
            margin-top: 0.5rem;
        }
        
        /* About Page */
        .about-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        
        .about-image {
            width: 100%;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .about-content h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: #333;
        }
        
        .about-content p {
            line-height: 1.8;
            color: #666;
            margin-bottom: 1.5rem;
        }
        
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .team-member {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .team-member img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 1rem;
            border: 5px solid #f5f5f5;
        }
        
        .team-member h3 {
            margin-bottom: 0.5rem;
            color: #333;
        }
        
        .team-member p {
            color: #6e8efb;
            font-weight: 600;
        }
        
        /* Contact Page */
        .contact-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        .contact-info {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .contact-info h2 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: #333;
        }
        
        .contact-details {
            margin-bottom: 2rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .contact-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            margin-right: 1rem;
        }
        
        .contact-text h3 {
            font-size: 1.1rem;
            margin-bottom: 0.3rem;
            color: #333;
        }
        
        .contact-text p, .contact-text a {
            color: #666;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .contact-text a:hover {
            color: #6e8efb;
        }
        
        .contact-map {
            height: 100%;
            min-height: 400px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .contact-map iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .contact-form {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            grid-column: 1 / -1;
            margin-top: 2rem;
        }
        
        .contact-form h2 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: #333;
            text-align: center;
        }
        
        .submit-btn {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
            font-weight: 600;
        }
        
        .submit-btn:hover {
            opacity: 0.9;
            transform: translateY(-2px);
        }
        
        /* Footer */
        footer {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            color: white;
            padding: 3rem 2rem;
            text-align: center;
        }
        
        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            text-align: left;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            position: relative;
            display: inline-block;
        }
        
        .footer-column h3:after {
            content: '';
            position: absolute;
            left: 0;
            bottom: -8px;
            width: 50px;
            height: 3px;
            background: white;
            border-radius: 3px;
        }
        
        .footer-column p {
            line-height: 1.6;
            margin-bottom: 1rem;
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
            display: block;
        }
        
        .footer-links a:hover {
            transform: translateX(5px);
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background: white;
            color: #6e8efb;
            transform: translateY(-3px);
        }
        
        .copyright {
            margin-top: 3rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255,255,255,0.1);
        }
        
        /* Responsive Styles */
        @media (max-width: 1024px) {
            .product-detail,
            .cart-page,
            .account-container,
            .about-section,
            .contact-section {
                grid-template-columns: 1fr;
            }
            
            .account-nav,
            .about-image {
                order: -1;
            }
            
            .contact-map {
                min-height: 300px;
            }
        }
        
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                padding: 1rem;
            }
            
            .logo {
                margin-bottom: 1rem;
            }
            
            nav {
                width: 100%;
                justify-content: space-between;
            }
            
            .nav-links {
                width: 100%;
                justify-content: space-around;
                margin-top: 1rem;
            }
            
            .nav-links li {
                margin-left: 0;
            }
            
            .cart-icon {
                margin-left: 1rem;
            }
            
            .hero-title {
                font-size: 2rem;
            }
            
            .hero-subtitle {
                font-size: 1rem;
            }
        }
        
        @media (max-width: 480px) {
            .product-grid,
            .products-container,
            .team-grid {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                font-size: 1.5rem;
            }
            
            .cart-item {
                flex-direction: column;
            }
            
            .cart-item-image {
                margin-bottom: 1rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="logo" onclick="showSection('homePage')">
            <i class="fas fa-headphones"></i>
            <span>AudioHub</span>
        </div>
        <nav>
            <ul class="nav-links">
                <li><a href="#" class="active" onclick="showSection('homePage')">Home</a></li>
                <li><a href="#" onclick="showSection('productsPage')">Products</a></li>
                <li><a href="#" onclick="showSection('aboutPage')">About</a></li>
                <li><a href="#" onclick="showSection('contactPage')">Contact</a></li>
                <li><a href="#" onclick="showSection('youPage')">You</a></li>
                <li>
                    <a href="#" onclick="showSection('cartPage')" class="cart-link">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count">0</span>
                    </a>
                </li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Home Page -->
        <section id="homePage" class="page-section active-section">
            <div class="container">
                <div class="hero-section">
                    <h1 class="hero-title">Experience Premium Sound</h1>
                    <p class="hero-subtitle">Discover our curated collection of high-end audio devices that deliver exceptional sound quality and comfort</p>
                    <a href="#" class="cta-button" onclick="showSection('productsPage')">Shop Now</a>
                </div>

                <div class="featured-section">
                    <h2 class="section-title">Featured Products</h2>
                    <div class="product-grid" id="featuredProducts">
                        <!-- Featured products will be loaded here -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Products Page -->
        <section id="productsPage" class="page-section">
            <div class="container">
                <h2 class="section-title">Our Products</h2>
                <div class="products-container" id="productsContainer">
                    <!-- All products will be loaded here -->
                </div>
            </div>
        </section>

        <!-- Product Detail Page -->
        <section id="productDetailPage" class="page-section">
            <div class="container">
                <div class="product-detail" id="productDetail">
                    <!-- Product details will be loaded here -->
                </div>
            </div>
        </section>

        <!-- Cart Page -->
        <section id="cartPage" class="page-section">
            <div class="container">
                <div class="cart-page">
                    <div class="cart-items-section">
                        <h2>Your Cart</h2>
                        <div id="cartItemsContainer">
                            <!-- Cart items will be loaded here -->
                        </div>
                        
                        <!-- Checkout Form -->
                        <div class="checkout-form" id="checkoutForm">
                            <h2>Shipping Details</h2>
                            <div class="form-group">
                                <label for="name">Full Name</label>
                                <input type="text" id="name" required>
                            </div>
                            <div class="form-group">
                                <label for="phone">Phone Number</label>
                                <input type="tel" id="phone" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Email Address</label>
                                <input type="email" id="email" required>
                            </div>
                            <div class="form-group">
                                <label for="address">Shipping Address</label>
                                <textarea id="address" required></textarea>
                            </div>
                            <div class="form-group">
                                <label for="payment">Payment Method</label>
                                <select id="payment" required>
                                    <option value="">Select Payment</option>
                                    <option value="cod">Cash on Delivery</option>
                                    <option value="upi">UPI Payment</option>
                                </select>
                            </div>
                        </div>
                    </div>
                    
                    <div class="cart-summary">
                        <h2 class="summary-title">Order Summary</h2>
                        <div class="summary-item">
                            <span>Subtotal:</span>
                            <span id="cartSubtotal">₹0</span>
                        </div>
                        <div class="summary-item">
                            <span>Shipping:</span>
                            <span>₹99</span>
                        </div>
                        <div class="summary-item summary-total">
                            <span>Total:</span>
                            <span id="cartTotal">₹99</span>
                        </div>
                        <button class="checkout-btn" onclick="proceedToWhatsApp()">Proceed to WhatsApp</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- You Page -->
        <section id="youPage" class="page-section">
            <div class="container">
                <div class="account-container">
                    <div class="account-nav">
                        <div class="nav-item active" onclick="showAccountSection('orders')">
                            <i class="fas fa-box"></i> Your Orders
                        </div>
                        <div class="nav-item" onclick="showAccountSection('buyAgain')">
                            <i class="fas fa-redo"></i> Buy Again
                        </div>
                        <div class="nav-item" onclick="showAccountSection('rewards')">
                            <i class="fas fa-gift"></i> Rewards
                        </div>
                        <div class="nav-item" onclick="showAccountSection('account')">
                            <i class="fas fa-user"></i> Account
                        </div>
                    </div>
                    
                    <div class="account-content" id="accountContent">
                        <!-- Content will be loaded dynamically -->
                    </div>
                </div>
            </div>
        </section>

        <!-- About Page -->
        <section id="aboutPage" class="page-section">
            <div class="container">
                <div class="about-section">
                    <div class="about-content">
                        <h2 class="section-title">About AudioHub</h2>
                        <p>Founded in 2020, AudioHub is dedicated to bringing you the finest audio experiences. We believe that great sound should be accessible to everyone, and we carefully curate our collection to ensure the highest quality products.</p>
                        <p>Our team of audio enthusiasts tests every product to ensure it meets our strict standards for sound quality, comfort, and durability. We partner with the best brands in the industry to bring you cutting-edge technology at competitive prices.</p>
                        <p>Whether you're a casual listener or an audiophile, we have the perfect audio solution for you. Our knowledgeable staff is always available to help you find exactly what you need.</p>
                    </div>
                    <img src="https://images.unsplash.com/photo-1558379850-823f103f866a" alt="About AudioHub" class="about-image">
                </div>

                <div class="team-section">
                    <h2 class="section-title">Our Team</h2>
                    <div class="team-grid">
                        <div class="team-member">
                            <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Team Member">
                            <h3>Rajesh Kumar</h3>
                            <p>Founder & CEO</p>
                        </div>
                        <div class="team-member">
                            <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Team Member">
                            <h3>Priya Sharma</h3>
                            <p>Product Specialist</p>
                        </div>
                        <div class="team-member">
                            <img src="https://randomuser.me/api/portraits/men/67.jpg" alt="Team Member">
                            <h3>Amit Patel</h3>
                            <p>Customer Support</p>
                        </div>
                        <div class="team-member">
                            <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Team Member">
                            <h3>Neha Gupta</h3>
                            <p>Marketing Manager</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Page -->
        <section id="contactPage" class="page-section">
            <div class="container">
                <div class="contact-section">
                    <div class="contact-info">
                        <h2 class="section-title">Contact Us</h2>
                        <div class="contact-details">
                            <div class="contact-item">
                                <div class="contact-icon">
                                    <i class="fas fa-map-marker-alt"></i>
                                </div>
                                <div class="contact-text">
                                    <h3>Address</h3>
                                    <p>123 Audio Street, Mumbai, India 400001</p>
                                </div>
                            </div>
                            <div class="contact-item">
                                <div class="contact-icon">
                                    <i class="fas fa-phone-alt"></i>
                                </div>
                                <div class="contact-text">
                                    <h3>Phone</h3>
                                    <p><a href="tel:+919876543210">+91 98765 43210</a></p>
                                </div>
                            </div>
                            <div class="contact-item">
                                <div class="contact-icon">
                                    <i class="fas fa-envelope"></i>
                                </div>
                                <div class="contact-text">
                                    <h3>Email</h3>
                                    <p><a href="mailto:info@audiohub.com">info@audiohub.com</a></p>
                                </div>
                            </div>
                        </div>
                        <div class="social-links">
                            <a href="#"><i class="fab fa-facebook-f"></i></a>
                            <a href="#"><i class="fab fa-twitter"></i></a>
                            <a href="#"><i class="fab fa-instagram"></i></a>
                            <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        </div>
                    </div>
                    <div class="contact-map">
                        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3771.715682416813!2d72.8322143149006!3d19.03398768711249!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3be7ced3a31e03fd%3A0x5bbc6bcf2e6a3a0e!2sGateway%20Of%20India%20Mumbai!5e0!3m2!1sen!2sin!4v1625060000000!5m2!1sen!2sin" allowfullscreen="" loading="lazy"></iframe>
                    </div>
                    <div class="contact-form">
                        <h2 class="section-title">Send Us a Message</h2>
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="contactName">Your Name</label>
                                <input type="text" id="contactName" required>
                            </div>
                            <div class="form-group">
                                <label for="contactEmail">Email Address</label>
                                <input type="email" id="contactEmail" required>
                            </div>
                            <div class="form-group">
                                <label for="contactMessage">Message</label>
                                <textarea id="contactMessage" required></textarea>
                            </div>
                            <button type="submit" class="submit-btn">Send Message</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>AudioHub</h3>
                    <p>Your premier destination for high-quality audio devices. We offer the best selection of headphones, earbuds, and speakers.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#" onclick="showSection('homePage')">Home</a></li>
                        <li><a href="#" onclick="showSection('productsPage')">Products</a></li>
                        <li><a href="#" onclick="showSection('aboutPage')">About Us</a></li>
                        <li><a href="#" onclick="showSection('contactPage')">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Help</h3>
                    <ul class="footer-links">
                        <li><a href="#">FAQs</a></li>
                        <li><a href="#">Shipping Policy</a></li>
                        <li><a href="#">Returns & Refunds</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 AudioHub. All Rights Reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Configuration
        const WHATSAPP_NUMBER = "9620067026"; // Replace with your WhatsApp number
        
        // State Management
        let state = {
            cart: JSON.parse(localStorage.getItem("cart")) || [],
            products: [
                {
                    id: 1,
                    title: "Wireless Earbuds Pro",
                    price: 599,
                    description: "Premium sound quality with active noise cancellation and 24hr battery life. Features IPX4 water resistance and touch controls.",
                    image: "https://images.unsplash.com/photo-1590658268037-6bf12165a8df",
                    category: "earbuds",
                    featured: true
                },
                {
                    id: 2,
                    title: "AirPods Max",
                    price: 899,
                    description: "High-fidelity audio with dynamic head tracking and spatial audio. Premium design with breathable knit mesh canopy.",
                    image: "https://images.unsplash.com/photo-1613047508032-2aee1c24e72d",
                    category: "airpods",
                    featured: true
                },
                {
                    id: 3,
                    title: "Noise Cancelling Headphones",
                    price: 499,
                    description: "Industry-leading noise cancellation with 30hr battery life. Premium comfort with plush ear cushions.",
                    image: "https://images.unsplash.com/photo-1505740420928-5e560c06d30e",
                    category: "headphones",
                    featured: true
                },
                {
                    id: 4,
                    title: "Bluetooth Speaker",
                    price: 699,
                    description: "Portable wireless speaker with 20hr battery life and IPX7 waterproof rating. Delivers rich, room-filling sound.",
                    image: "https://images.unsplash.com/photo-1572569511254-d8f925fe2cbb",
                    category: "speakers",
                    featured: false
                }
            ],
            orders: [
                {
                    id: 1001,
                    date: "31 March 2023",
                    status: "Delivered",
                    items: [
                        {id: 1, title: "Wireless Earbuds Pro", price: 7999, quantity: 1},
                        {id: 4, title: "Bluetooth Speaker", price: 12999, quantity: 1}
                    ],
                    total: 20998
                },
                {
                    id: 1002,
                    date: "15 March 2023",
                    status: "Delivered",
                    items: [
                        {id: 3, title: "Noise Cancelling Headphones", price: 29999, quantity: 1}
                    ],
                    total: 29999
                }
            ],
            rewards: {
                cashback: 1245,
                offers: 3,
                scratchCards: 2
            }
        };

        // DOM Elements
        const elements = {
            cartCount: document.querySelector(".cart-count"),
            cartItemsContainer: document.getElementById("cartItemsContainer"),
            cartSubtotal: document.getElementById("cartSubtotal"),
            cartTotal: document.getElementById("cartTotal"),
            accountContent: document.getElementById("accountContent")
        };

        // Navigation Functions
        function showSection(sectionId) {
            // Update active nav link
            document.querySelectorAll('.nav-links a').forEach(link => {
                link.classList.remove('active');
                if (link.textContent === sectionId.replace('Page', '') || 
                    (sectionId === 'cartPage' && link.querySelector('.cart-icon'))) {
                    link.classList.add('active');
                }
            });
            
            // Show selected section
            document.querySelectorAll('.page-section').forEach(section => {
                section.classList.remove('active-section');
            });
            document.getElementById(sectionId).classList.add('active-section');
            
            // Load appropriate content
            if (sectionId === 'productsPage') renderAllProducts();
            if (sectionId === 'homePage') renderFeaturedProducts();
            if (sectionId === 'cartPage') renderCartPage();
            if (sectionId === 'youPage') showAccountSection('orders');
            
            // Scroll to top
            window.scrollTo(0, 0);
        }

        function showProductPage(productId) {
            // Update nav to show Products as active
            document.querySelectorAll('.nav-links a').forEach(link => {
                link.classList.remove('active');
                if (link.textContent === 'Products') link.classList.add('active');
            });
            
            // Show product detail page
            document.querySelectorAll('.page-section').forEach(section => {
                section.classList.remove('active-section');
            });
            document.getElementById('productDetailPage').classList.add('active-section');
            
            // Render product details
            renderProductDetails(productId);
            
            // Scroll to top
            window.scrollTo(0, 0);
        }

        // Rendering Functions
        function renderFeaturedProducts() {
            const featured = state.products.filter(p => p.featured);
            const container = document.getElementById('featuredProducts');
            
            container.innerHTML = featured.map(product => `
                <div class="product-card" onclick="showProductPage(${product.id})">
                    <div class="product-image-container">
                        <img src="${product.image}" class="product-image" alt="${product.title}">
                    </div>
                    <div class="product-info">
                        <h3 class="product-title">${product.title}</h3>
                        <p class="product-price">₹${product.price.toLocaleString('en-IN')}</p>
                    </div>
                </div>
            `).join('');
        }

        function renderAllProducts() {
            const container = document.getElementById('productsContainer');
            
            container.innerHTML = state.products.map(product => `
                <div class="product-card" onclick="showProductPage(${product.id})">
                    <div class="product-image-container">
                        <img src="${product.image}" class="product-image" alt="${product.title}">
                    </div>
                    <div class="product-info">
                        <h3 class="product-title">${product.title}</h3>
                        <p class="product-price">₹${product.price.toLocaleString('en-IN')}</p>
                    </div>
                </div>
            `).join('');
        }

        function renderProductDetails(productId) {
            const product = state.products.find(p => p.id === productId);
            const container = document.getElementById('productDetail');
            
            container.innerHTML = `
                <div class="product-gallery">
                    <img src="${product.image}" class="main-image" alt="${product.title}">
                </div>
                <div class="product-content">
                    <span class="product-brand">Premium Audio</span>
                    <h1>${product.title}</h1>
                    <p class="product-price">₹${product.price.toLocaleString('en-IN')}</p>
                    <p class="product-description">${product.description}</p>
                    <button class="add-to-cart-lg" onclick="addToCart(${product.id})">
                        <i class="fas fa-cart-plus"></i> Add to Cart
                    </button>
                </div>
            `;
        }

        function renderCartPage() {
            if (state.cart.length === 0) {
                elements.cartItemsContainer.innerHTML = `
                    <div style="text-align: center; padding: 3rem;">
                        <h3>Your cart is empty</h3>
                        <p>Continue shopping to add items to your cart</p>
                        <button class="cta-button" onclick="showSection('productsPage')" style="margin-top: 1rem;">
                            Shop Now
                        </button>
                    </div>
                `;
                document.getElementById('checkoutForm').style.display = 'none';
                elements.cartSubtotal.textContent = "₹0";
                elements.cartTotal.textContent = "₹99";
                return;
            }
            
            elements.cartItemsContainer.innerHTML = state.cart.map(item => `
                <div class="cart-item" data-id="${item.id}">
                    <img src="${item.image}" class="cart-item-image" alt="${item.title}">
                    <div class="cart-item-details">
                        <h3 class="cart-item-title">${item.title}</h3>
                        <p class="cart-item-price">₹${item.price.toLocaleString('en-IN')}</p>
                        <div class="cart-item-quantity">
                            <button class="quantity-btn" onclick="updateQuantity(${item.id}, -1)">-</button>
                            <span class="quantity-value">${item.quantity}</span>
                            <button class="quantity-btn" onclick="updateQuantity(${item.id}, 1)">+</button>
                        </div>
                    </div>
                    <button class="remove-item" onclick="removeFromCart(${item.id})">
                        <i class="fas fa-trash"></i> Remove
                    </button>
                </div>
            `).join('');
            
            document.getElementById('checkoutForm').style.display = 'block';
            updateCartTotals();
        }

        function showAccountSection(section) {
            // Update navigation
            document.querySelectorAll('.nav-item').forEach(item => 
                item.classList.remove('active'));
            event.target.classList.add('active');

            // Load content
            let html = '';
            
            switch(section) {
                case 'orders':
                    html = `<h2>Your Orders</h2>`;
                    
                    if (state.orders.length === 0) {
                        html += `
                            <div style="text-align: center; padding: 2rem;">
                                <p>You haven't placed any orders yet</p>
                                <button class="cta-button" onclick="showSection('productsPage')" style="margin-top: 1rem;">
                                    Start Shopping
                                </button>
                            </div>
                        `;
                    } else {
                        state.orders.forEach(order => {
                            html += `
                                <div class="order-card">
                                    <div class="order-header">
                                        <div>
                                            <p><strong>Order #${order.id}</strong></p>
                                            <p>Placed on ${order.date}</p>
                                            <p>Total: ₹${order.total.toLocaleString('en-IN')}</p>
                                        </div>
                                        <span class="order-status">${order.status}</span>
                                    </div>
                                    ${order.items.map(item => `
                                        <div class="order-product">
                                            <img src="${state.products.find(p => p.id === item.id).image}" alt="${item.title}">
                                            <div>
                                                <h3>${item.title}</h3>
                                                <p>Quantity: ${item.quantity}</p>
                                                <p>Price: ₹${item.price.toLocaleString('en-IN')}</p>
                                            </div>
                                        </div>
                                    `).join('')}
                                </div>
                            `;
                        });
                    }
                    break;
                
                case 'rewards':
                    html = `
                        <h2>Your Rewards</h2>
                        <div class="reward-card">
                            <h3>Cashback Balance</h3>
                            <p>Available to use on your next purchase</p>
                            <p class="reward-value">₹${state.rewards.cashback.toLocaleString('en-IN')}</p>
                        </div>
                        <div class="reward-card">
                            <h3>Active Offers</h3>
                            <p>Special discounts available</p>
                            <p class="reward-value">${state.rewards.offers}</p>
                        </div>
                        <div class="reward-card">
                            <h3>Scratch Cards</h3>
                            <p>Unused scratch cards</p>
                            <p class="reward-value">${state.rewards.scratchCards}</p>
                        </div>
                    `;
                    break;
                
                case 'buyAgain':
                    html = `
                        <h2>Buy Again</h2>
                        <div style="text-align: center; padding: 2rem;">
                            <p>See what others are reordering</p>
                            <button class="cta-button" onclick="showSection('productsPage')" style="margin-top: 1rem;">
                                View Products
                            </button>
                        </div>
                    `;
                    break;
                
                case 'account':
                    html = `
                        <h2>Account Settings</h2>
                        <div style="margin-top: 2rem;">
                            <p><strong>Name:</strong> Customer Name</p>
                            <p><strong>Email:</strong> customer@example.com</p>
                            <p><strong>Phone:</strong> +91 98765 43210</p>
                            <button class="cta-button" style="margin-top: 2rem;">
                                Edit Profile
                            </button>
                        </div>
                    `;
                    break;
            }

            elements.accountContent.innerHTML = html;
        }

        // Cart Functions
        function addToCart(productId) {
            const product = state.products.find(p => p.id === productId);
            
            if (!product) return;
            
            const existingItem = state.cart.find(item => item.id === productId);
            
            if (existingItem) {
                existingItem.quantity++;
            } else {
                state.cart.push({
                    ...product,
                    quantity: 1
                });
            }
            
            updateCart();
            
            // Show feedback
            alert(`${product.title} added to cart!`);
        }

        function updateQuantity(productId, change) {
            const item = state.cart.find(item => item.id === productId);
            
            if (!item) return;
            
            item.quantity += change;
            
            if (item.quantity < 1) {
                removeFromCart(productId);
            } else {
                updateCart();
            }
        }

        function removeFromCart(productId) {
            state.cart = state.cart.filter(item => item.id !== productId);
            updateCart();
        }

        function updateCart() {
            localStorage.setItem("cart", JSON.stringify(state.cart));
            updateCartUI();
            
            // If on cart page, refresh the view
            if (document.getElementById('cartPage').classList.contains('active-section')) {
                renderCartPage();
            }
        }

        function updateCartUI() {
            // Update cart count
            const totalItems = state.cart.reduce((sum, item) => sum + item.quantity, 0);
            elements.cartCount.textContent = totalItems;
        }

        function updateCartTotals() {
            const subtotal = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const total = subtotal + 99; // Add shipping
            
            elements.cartSubtotal.textContent = `₹${subtotal.toLocaleString('en-IN')}`;
            elements.cartTotal.textContent = `₹${total.toLocaleString('en-IN')}`;
        }

        function proceedToWhatsApp() {
            if (state.cart.length === 0) {
                alert("Your cart is empty!");
                return;
            }
            
            // Validate form
            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const email = document.getElementById('email').value;
            const address = document.getElementById('address').value;
            const payment = document.getElementById('payment').value;
            
            if (!name || !phone || !email || !address || !payment) {
                alert("Please fill all the details!");
                return;
            }
            
            // Create order summary
            const itemsText = state.cart.map(item => 
                `- ${item.title} (Qty: ${item.quantity}) - ₹${item.price.toLocaleString('en-IN')}`
            ).join('\n');
            
            const subtotal = state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const total = subtotal + 99;
            
            // Create WhatsApp message
            const message = `📦 *New Order Request* 📦
            
👤 *Customer Details:*
Name: ${name}
Phone: ${phone}
Email: ${email}
Address: ${address}
Payment Method: ${payment === 'cod' ? 'Cash on Delivery' : 'UPI Payment'}

📋 *Order Items:*
${itemsText}

💰 *Order Summary:*
Subtotal: ₹${subtotal.toLocaleString('en-IN')}
Shipping: ₹99
Total: ₹${total.toLocaleString('en-IN')}
            `;
            
            // Encode message for WhatsApp URL
            const encodedMessage = encodeURIComponent(message);
            
            // Open WhatsApp with pre-filled message
            window.open(`https://wa.me/${WHATSAPP_NUMBER}?text=${encodedMessage}`, '_blank');
            
            // Create order record
            const newOrder = {
                id: Math.floor(Math.random() * 9000) + 1000,
                date: new Date().toLocaleDateString('en-GB', { day: 'numeric', month: 'long', year: 'numeric' }),
                status: "Processing",
                items: [...state.cart],
                total: total,
                customer: { name, phone, email, address }
            };
            
            // Add to orders
            state.orders.unshift(newOrder);
            
            // Clear cart
            state.cart = [];
            updateCart();
            
            // Show success
            alert("Order request sent successfully via WhatsApp!");
            
            // Go to orders page
            showSection('youPage');
            showAccountSection('orders');
        }

        // Contact Form Submission
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('contactName').value;
            const email = document.getElementById('contactEmail').value;
            const message = document.getElementById('contactMessage').value;
            
            alert(`Thank you for your message, ${name}! We will contact you soon at ${email}.`);
            this.reset();
        });

        // Initialize the app
        function init() {
            renderFeaturedProducts();
            updateCartUI();
        }

        init();
    </script>
</body>
</html>
