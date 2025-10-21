<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Living Threads - Preserving Maasai Heritage</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Merienda:wght@400;700&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Nautilus+Pompilius&display=swap" rel="stylesheet">
    <style>
        /* CSS Variables for Theming */
        :root {
            --primary: #6A1B9A;
            --secondary: #8E24AA;
            --accent: #9C27B0;
            --background: #FFF8F0;
            --text: #333333;
            --light-text: #FFFFFF;
            --header-bg: #FFFFFF;
            --card-bg: #FFFFFF;
            --shadow: rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
            --footer-bg: #6A1B9A;
        }

        .dark-theme {
            --primary: #8E24AA;
            --secondary: #9C27B0;
            --accent: #AB47BC;
            --background: #1E1B18;
            --text: #F5F5F5;
            --light-text: #F5F5F5;
            --header-bg: #2D2430;
            --card-bg: #2A2520;
            --shadow: rgba(0, 0, 0, 0.3);
            --footer-bg: #4A148C;
        }

        /* Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: var(--transition);
        }

        body {
            font-family: 'Nautilus Pompilius', cursive;
            background-color: var(--background);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
            font-size: 18px;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: 'Merienda', cursive;
            font-weight: 700;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background-color: var(--header-bg);
            padding: 15px 0;
            box-shadow: 0 2px 10px var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 60px;
        }

        .header-left {
            display: flex;
            align-items: center;
            gap: 15px;
            height: 100%;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            height: 100%;
        }

        .logo h1 {
            font-size: 1.8rem;
            color: var(--primary);
            line-height: 1;
            font-family: 'Merienda', cursive;
        }

        .logo-icon {
            font-size: 2.5rem; /* Increased size */
            color: var(--primary);
            line-height: 1;
        }

        /* Hamburger Menu */
        .hamburger-menu {
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text);
            height: 100%;
            display: flex;
            align-items: center;
        }

        /* Search Bar */
        .search-bar {
            display: flex;
            align-items: center;
            background-color: var(--background);
            border-radius: 20px;
            padding: 8px 15px;
            width: 300px;
            box-shadow: 0 2px 5px var(--shadow);
        }

        .search-bar input {
            border: none;
            background: transparent;
            width: 100%;
            padding: 5px 10px;
            color: var(--text);
            outline: none;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 16px;
        }

        .search-bar i {
            color: var(--text);
        }

        .header-right {
            display: flex;
            align-items: center;
            gap: 20px;
            height: 100%;
        }

        .header-icon {
            font-size: 1.2rem;
            cursor: pointer;
            color: var(--text);
        }

        .theme-toggle {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text);
        }

        /* Navigation Menu */
        .nav-menu {
            position: fixed;
            top: 90px;
            left: 0;
            width: 250px;
            height: calc(100vh - 90px);
            background-color: var(--header-bg);
            box-shadow: 2px 0 10px var(--shadow);
            transform: translateX(-100%);
            transition: transform 0.3s ease;
            z-index: 99;
            overflow-y: auto;
            padding: 20px 0;
        }

        .nav-menu.active {
            transform: translateX(0);
        }

        .nav-menu ul {
            list-style: none;
            padding: 0;
        }

        .nav-menu li {
            border-bottom: 1px solid rgba(0,0,0,0.1);
        }

        .nav-menu a {
            display: block;
            padding: 15px 20px;
            text-decoration: none;
            color: var(--text);
            font-weight: 500;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .nav-menu a:hover {
            background-color: var(--primary);
            color: white;
        }

        /* Page Styles */
        .page {
            display: none;
            min-height: calc(100vh - 120px);
            padding: 40px 0;
        }

        .active-page {
            display: block;
        }

        /* Login Page */
        .login-container {
            max-width: 500px;
            margin: 0 auto;
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px var(--shadow);
            animation: slideIn 0.5s ease;
        }

        @keyframes slideIn {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .form-title {
            text-align: center;
            margin-bottom: 25px;
            color: var(--primary);
            font-family: 'Merienda', cursive;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            font-family: 'Nautilus Pompilius', cursive;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: var(--background);
            color: var(--text);
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 16px;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary);
        }

        .language-toggle {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

        .lang-btn {
            padding: 5px 10px;
            background: none;
            border: 1px solid var(--primary);
            border-radius: 5px;
            cursor: pointer;
            color: var(--text);
            font-family: 'Nautilus Pompilius', cursive;
        }

        .lang-btn.active {
            background-color: var(--primary);
            color: var(--light-text);
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 500;
            text-align: center;
            text-decoration: none;
            transition: var(--transition);
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px var(--shadow);
        }

        .btn-purple {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 500;
            text-align: center;
            text-decoration: none;
            transition: var(--transition);
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .btn-purple:hover {
            background-color: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px var(--shadow);
        }

        .form-footer {
            text-align: center;
            margin-top: 20px;
            font-family: 'Nautilus Pompilius', cursive;
        }

        .social-login {
            margin-top: 20px;
            text-align: center;
            font-family: 'Nautilus Pompilius', cursive;
        }

        .social-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 15px;
        }

        .social-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: var(--background);
            color: var(--text);
            font-size: 1.2rem;
            border: 1px solid #ddd;
            cursor: pointer;
        }

        .social-btn:hover {
            background-color: var(--primary);
            color: white;
        }

        /* Home Page */
        .hero {
            text-align: center;
            padding: 60px 0;
            animation: fadeIn 1s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--primary);
            font-family: 'Merienda', cursive;
        }

        .hero p {
            font-size: 1.4rem;
            max-width: 700px;
            margin: 0 auto 30px;
            font-family: 'Nautilus Pompilius', cursive;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .feature-card {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px var(--shadow);
            text-align: center;
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-icon {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .feature-card h3 {
            font-family: 'Merienda', cursive;
            margin-bottom: 15px;
        }

        .feature-card p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .impact-tracker {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px var(--shadow);
            margin-top: 40px;
        }

        .impact-tracker h2 {
            font-family: 'Merienda', cursive;
        }

        .impact-tracker p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .impact-form {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 20px;
        }

        .impact-list {
            list-style: none;
        }

        .impact-item {
            padding: 10px 15px;
            background-color: var(--background);
            margin-bottom: 10px;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        /* Know More Page */
        .cultural-section {
            margin-bottom: 40px;
        }

        .cultural-section h2 {
            color: var(--primary);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary);
            font-family: 'Merienda', cursive;
        }

        .cultural-section p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
            margin-bottom: 15px;
        }

        .media-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .media-item {
            background-color: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px var(--shadow);
        }

        .media-item img, .media-item video {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .media-caption {
            padding: 15px;
        }

        .media-caption h3 {
            font-family: 'Merienda', cursive;
            margin-bottom: 10px;
        }

        .media-caption p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 16px;
        }

        .faq-item {
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow: hidden;
        }

        .faq-question {
            padding: 15px;
            background-color: var(--card-bg);
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .faq-answer {
            padding: 0 15px;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .faq-answer.active {
            padding: 15px;
            max-height: 500px;
        }

        /* Forum Page */
        .forum-intro {
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: 0 5px 15px var(--shadow);
            text-align: center;
        }

        .forum-intro h1 {
            font-family: 'Merienda', cursive;
        }

        .forum-intro p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .join-prompt {
            font-size: 1.2rem;
            margin: 20px 0;
            color: var(--primary);
            font-weight: 500;
            font-family: 'Nautilus Pompilius', cursive;
        }

        .forum-topics {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .topic-card {
            background-color: var(--card-bg);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 15px var(--shadow);
            cursor: pointer;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 100%;
        }

        .topic-card:hover {
            transform: translateY(-5px);
        }

        .topic-card h3 {
            font-family: 'Merienda', cursive;
            margin-bottom: 10px;
        }

        .topic-card p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 16px;
            margin-bottom: 15px;
        }

        .topic-card .btn-purple {
            margin-top: auto;
        }

        .discussion-form {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px var(--shadow);
            margin-bottom: 30px;
        }

        .discussion-form h2 {
            font-family: 'Merienda', cursive;
            margin-bottom: 15px;
        }

        .discussions-container {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px var(--shadow);
        }

        .discussions-container h2 {
            font-family: 'Merienda', cursive;
            margin-bottom: 15px;
        }

        .discussion-item {
            padding: 15px;
            border-bottom: 1px solid #ddd;
            margin-bottom: 15px;
        }

        .discussion-item h3 {
            font-family: 'Merienda', cursive;
            margin-bottom: 10px;
        }

        .discussion-item p {
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .discussion-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 0.9rem;
            color: #777;
            font-family: 'Nautilus Pompilius', cursive;
        }

        .discussion-topic {
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 5px;
        }

        /* Chatbot */
        .chatbot-container {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
        }

        .chatbot-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 5px 15px var(--shadow);
        }

        .chatbot-window {
            position: absolute;
            bottom: 70px;
            right: 0;
            width: 350px;
            height: 450px;
            background-color: var(--card-bg);
            border-radius: 10px;
            box-shadow: 0 5px 25px var(--shadow);
            display: none;
            flex-direction: column;
        }

        .chatbot-header {
            padding: 15px;
            background-color: var(--primary);
            color: white;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-family: 'Merienda', cursive;
        }

        .chatbot-messages {
            flex: 1;
            padding: 15px;
            overflow-y: auto;
        }

        .message {
            margin-bottom: 15px;
            padding: 10px 15px;
            border-radius: 18px;
            max-width: 80%;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 16px;
        }

        .bot-message {
            background-color: var(--background);
            align-self: flex-start;
            border-bottom-left-radius: 5px;
        }

        .user-message {
            background-color: var(--primary);
            color: white;
            align-self: flex-end;
            margin-left: auto;
            border-bottom-right-radius: 5px;
        }

        .chatbot-input {
            display: flex;
            padding: 15px;
            border-top: 1px solid #ddd;
        }

        .chatbot-input input {
            flex: 1;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 20px;
            margin-right: 10px;
            background-color: var(--background);
            color: var(--text);
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 16px;
        }

        .chatbot-input button {
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
        }

        /* Footer */
        footer {
            background-color: var(--footer-bg);
            padding: 30px 0;
            margin-top: 50px;
        }

        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 30px;
        }

        .footer-section {
            flex: 1;
            min-width: 250px;
        }

        .footer-section h3 {
            margin-bottom: 15px;
            color: white;
            font-family: 'Merienda', cursive;
        }

        .footer-section p, .footer-section a {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 10px;
            display: block;
            text-decoration: none;
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        .footer-section a:hover {
            color: white;
        }

        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 15px;
        }

        .social-icons a {
            font-size: 1.5rem;
        }

        .footer-bottom {
            text-align: center;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            color: rgba(255, 255, 255, 0.8);
            font-family: 'Nautilus Pompilius', cursive;
            font-size: 18px;
        }

        /* Login Page Specific Styles */
        .login-page footer {
            display: none;
        }

        /* Error Message */
        .error-message {
            color: #ff3860;
            font-size: 14px;
            margin-top: 5px;
            display: none;
            font-family: 'Nautilus Pompilius', cursive;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-wrap: wrap;
            }
            
            .search-bar {
                width: 100%;
                margin: 10px 0;
                order: 3;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .chatbot-window {
                width: 300px;
            }
            
            .footer-content {
                flex-direction: column;
            }
            
            .nav-menu {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header for Home, Know More, and Forum Pages -->
    <header id="main-header">
        <div class="container header-content">
            <div class="header-left">
                <div class="hamburger-menu">
                    <i class="fas fa-bars"></i>
                </div>
                <div class="logo">
                    <span class="logo-icon">≅</span>
                    <h1>Living Threads</h1>
                </div>
            </div>
            
            <div class="search-bar">
                <i class="fas fa-search"></i>
                <input type="text" placeholder="Search...">
            </div>
            
            <div class="header-right">
                <i class="fas fa-user-circle header-icon"></i>
                <i class="fas fa-bell header-icon"></i>
                <button class="theme-toggle" id="themeToggle">🌙</button>
            </div>
        </div>
    </header>

    <!-- Navigation Menu -->
    <nav class="nav-menu" id="navMenu">
        <ul>
            <li><a href="#" class="nav-link" data-page="home">Home</a></li>
            <li><a href="#" class="nav-link" data-page="knowmore">Know More</a></li>
            <li><a href="#" class="nav-link" data-page="forum">Community Forum</a></li>
            <li><a href="#" class="nav-link" data-page="login">Login</a></li>
            <li><a href="#" class="nav-link" data-page="knowmore" data-section="songs">Traditional Songs</a></li>
            <li><a href="#" class="nav-link" data-page="knowmore" data-section="ceremonies">Ceremonies</a></li>
            <li><a href="#" class="nav-link" data-page="knowmore" data-section="daily-life">Daily Life</a></li>
            <li><a href="#" class="nav-link" data-page="knowmore" data-section="faq">FAQs</a></li>
            <li><a href="#">Cultural Resources</a></li>
            <li><a href="#">Events</a></li>
            <li><a href="#">Gallery</a></li>
            <li><a href="#">Contact</a></li>
            <li><a href="#">Support</a></li>
            <li><a href="#">Privacy Policy</a></li>
        </ul>
    </nav>

    <!-- Pages -->
    <main class="container">
        <!-- Login Page -->
        <section id="login" class="page active-page login-page">
            <div class="login-container">
                <h2 class="form-title">Welcome to Living Threads</h2>
                
                <div class="language-toggle">
                    <button class="lang-btn active" data-lang="en">English</button>
                    <button class="lang-btn" data-lang="sw">Kiswahili</button>
                    <button class="lang-btn" data-lang="maa">Maa</button>
                </div>
                
                <form id="loginForm">
                    <div class="form-group">
                        <label for="email" data-lang="en">Email Address</label>
                        <input type="email" id="email" class="form-control" placeholder="Enter your email" data-placeholder-en="Enter your email" data-placeholder-sw="Weka barua pepe yako" data-placeholder-maa="Ingiza enkop email">
                        <div class="error-message" id="emailError">Please enter a valid email address</div>
                    </div>
                    <div class="form-group">
                        <label for="password" data-lang="en">Password</label>
                        <input type="password" id="password" class="form-control" placeholder="Enter your password" data-placeholder-en="Enter your password" data-placeholder-sw="Weka nenosiri lako" data-placeholder-maa="Ingiza enkop password">
                        <div class="error-message" id="passwordError">Password is required</div>
                    </div>
                    <button type="submit" class="btn btn-block">Login</button>
                </form>
                
                <div class="form-footer">
                    <p data-lang="en">Don't have an account? <a href="#" id="showSignup">Sign up</a></p>
                </div>
                
                <div class="social-login">
                    <p data-lang="en">Or continue with</p>
                    <div class="social-buttons">
                        <div class="social-btn">
                            <i class="fab fa-google"></i>
                        </div>
                        <div class="social-btn">
                            <i class="fab fa-apple"></i>
                        </div>
                        <div class="social-btn">
                            <i class="fab fa-facebook-f"></i>
                        </div>
                    </div>
                </div>
                
                <form id="signupForm" style="display: none;">
                    <div class="form-group">
                        <label for="fullName" data-lang="en">Full Name</label>
                        <input type="text" id="fullName" class="form-control" placeholder="Enter your full name" data-placeholder-en="Enter your full name" data-placeholder-sw="Weka jina lako kamili" data-placeholder-maa="Ingiza enkarna olkiteng">
                    </div>
                    <div class="form-group">
                        <label for="signupEmail" data-lang="en">Email Address</label>
                        <input type="email" id="signupEmail" class="form-control" placeholder="Enter your email" data-placeholder-en="Enter your email" data-placeholder-sw="Weka barua pepe yako" data-placeholder-maa="Ingiza enkop email">
                        <div class="error-message" id="signupEmailError">Please enter a valid email address</div>
                    </div>
                    <div class="form-group">
                        <label for="signupPassword" data-lang="en">Password</label>
                        <input type="password" id="signupPassword" class="form-control" placeholder="Create a password" data-placeholder-en="Create a password" data-placeholder-sw="Tengeneza nenosiri" data-placeholder-maa="Enkarna password">
                        <div class="error-message" id="signupPasswordError">Password must be at least 6 characters</div>
                    </div>
                    <div class="form-group">
                        <label for="confirmPassword" data-lang="en">Confirm Password</label>
                        <input type="password" id="confirmPassword" class="form-control" placeholder="Confirm your password" data-placeholder-en="Confirm your password" data-placeholder-sw="Thibitisha nenosiri lako" data-placeholder-maa="Thibitisha enkop password">
                        <div class="error-message" id="confirmPasswordError">Passwords do not match</div>
                    </div>
                    <button type="submit" class="btn btn-block">Sign Up</button>
                </form>
                
                <div class="form-footer" id="signupFooter" style="display: none;">
                    <p data-lang="en">Already have an account? <a href="#" id="showLogin">Login</a></p>
                </div>
            </div>
        </section>

        <!-- Home Page -->
        <section id="home" class="page">
            <div class="hero">
                <h1 data-lang="en">Preserving Maasai Heritage</h1>
                <p data-lang="en">Living Threads is a digital platform dedicated to preserving and promoting the intangible cultural heritage of the Maasai community through stories, songs, and shared knowledge.</p>
                <a href="#" class="btn nav-link" data-page="knowmore">Learn More</a>
            </div>
            
            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">🎵</div>
                    <h3 data-lang="en">Traditional Songs</h3>
                    <p data-lang="en">Discover and learn traditional Maasai songs with lyrics and meanings.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📖</div>
                    <h3 data-lang="en">Oral Stories</h3>
                    <p data-lang="en">Listen to elders narrate stories passed down through generations.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">👥</div>
                    <h3 data-lang="en">Community Forum</h3>
                    <p data-lang="en">Connect with other Maasai students and share cultural knowledge.</p>
                </div>
            </div>
            
            <div class="impact-tracker">
                <h2 data-lang="en">Cultural Impact Tracker</h2>
                <p data-lang="en">Track your contributions to preserving Maasai culture</p>
                
                <div class="impact-form">
                    <input type="text" id="activityInput" class="form-control" placeholder="Enter a cultural activity" data-placeholder-en="Enter a cultural activity" data-placeholder-sw="Weka shughuli ya kitamaduni" data-placeholder-maa="Ingiza enkitokitin kitamaduni">
                    <button id="addActivity" class="btn">Add Activity</button>
                </div>
                
                <div id="impactStats">
                    <p data-lang="en">Total Activities: <span id="totalActivities">0</span></p>
                </div>
                
                <ul class="impact-list" id="activitiesList">
                    <!-- Activities will be added here dynamically -->
                </ul>
            </div>
        </section>

        <!-- Know More Page -->
        <section id="knowmore" class="page">
            <h1 data-lang="en">Understanding Maasai Culture</h1>
            
            <div class="cultural-section" id="songs-section">
                <h2 data-lang="en">Traditional Songs and Stories</h2>
                <p data-lang="en">Maasai oral traditions include songs for different occasions - from celebrations to rites of passage. These songs carry historical narratives and cultural values.</p>
                
                <div class="media-container">
                    <div class="media-item">
                        <img src="https://i.ytimg.com/vi/3BaKQuUYKik/maxresdefault.jpg" alt="Maasai Singing Performance">
                        <div class="media-caption">
                            <h3 data-lang="en">Esimen Song</h3>
                            <p data-lang="en">A traditional Maasai song performed during ceremonies by community members</p>
                            <a href="https://www.youtube.com/watch?v=3BaKQuUYKik" target="_blank" class="btn" style="margin-top: 10px;">Watch Video</a>
                        </div>
                    </div>
                    <div class="media-item">
                        <img src="https://i.ytimg.com/vi/SzTyn3qxi8s/maxresdefault.jpg" alt="Maasai Traditional Dance">
                        <div class="media-caption">
                            <h3 data-lang="en">Traditional Dance</h3>
                            <p data-lang="en">Maasai women performing the Adumu or "jumping dance" during a celebration</p>
                            <a href="https://www.youtube.com/watch?v=SzTyn3qxi8s" target="_blank" class="btn" style="margin-top: 10px;">Watch Video</a>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="cultural-section" id="ceremonies-section">
                <h2 data-lang="en">Ceremonies and Rites of Passage</h2>
                <p data-lang="en">Maasai culture is rich with ceremonies that mark important life transitions, such as Eunoto (warrior graduation) and Enkipaata (initiation).</p>
                
                <div class="media-container">
                    <div class="media-item">
                        <img src="https://www.aljazeera.com/wp-content/uploads/2023/08/33RJ8RR-highres-1692603733.jpg?fit=1170%2C780" alt="Maasai Ceremony">
                        <div class="media-caption">
                            <h3 data-lang="en">Eunoto Ceremony</h3>
                            <p data-lang="en">The graduation of Morans to junior elders, a significant rite of passage</p>
                        </div>
                    </div>
                    <div class="media-item">
                        <img src="https://www.shutterstock.com/image-photo/traditional-african-handmade-colorful-beads-260nw-1367289704.jpg" alt="Maasai Beadwork">
                        <div class="media-caption">
                            <h3 data-lang="en">Traditional Beadwork</h3>
                            <p data-lang="en">Intricate beadwork that communicates social status and cultural identity</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="cultural-section" id="daily-life-section">
                <h2 data-lang="en">Daily Life and Traditions</h2>
                <p data-lang="en">Beyond ceremonies, Maasai culture encompasses daily practices, traditional attire, and community living that have been preserved for generations.</p>
                
                <div class="media-container">
                    <div class="media-item">
                        <img src="https://altezzatravel.com/upload/medialibrary/a6a/mgxn73vzkxw19bjn53wyizvwttg1zab3.webp" alt="Maasai Attire">
                        <div class="media-caption">
                            <h3 data-lang="en">Traditional Attire</h3>
                            <p data-lang="en">The distinctive red shuka and elaborate jewelry worn by Maasai people</p>
                        </div>
                    </div>
                    <div class="media-item">
                        <img src="https://kairi.co.ke/wp-content/uploads/2024/07/manyatta-houses-maasai-village-visit.webp" alt="Maasai Village">
                        <div class="media-caption">
                            <h3 data-lang="en">Community Living</h3>
                            <p data-lang="en">Traditional Manyatta homes and community structures in a Maasai village</p>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="cultural-section" id="faq-section">
                <h2 data-lang="en">Frequently Asked Questions</h2>
                
                <div class="faq-item">
                    <div class="faq-question">
                        <span data-lang="en">What are the core values of Maasai culture?</span>
                        <span>+</span>
                    </div>
                    <div class="faq-answer">
                        <p data-lang="en">The Maasai value respect for elders, courage, community responsibility, and harmony with nature. These values are passed down through oral traditions and daily practices.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">
                        <span data-lang="en">How is Maasai beadwork significant?</span>
                        <span>+</span>
                    </div>
                    <div class="faq-answer">
                        <p data-lang="en">Maasai beadwork is not just decorative; it communicates social status, age, and marital status. Different colors have specific meanings in their cultural context.</p>
                    </div>
                </div>
                
                <div class="faq-item">
                    <div class="faq-question">
                        <span data-lang="en">Why is preserving intangible heritage important?</span>
                        <span>+</span>
                    </div>
                    <div class="faq-answer">
                        <p data-lang="en">Intangible heritage like songs, stories, and ceremonies forms the living memory of a culture. When these are lost, cultural identity and continuity are threatened.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Community Forum -->
        <section id="forum" class="page">
            <div class="forum-intro">
                <h1 data-lang="en">Community Forum</h1>
                <p data-lang="en">Share your thoughts, ask questions, and connect with other Maasai students. Let's preserve our heritage together.</p>
                <p><i class="privacy-icon">🔒</i> <span data-lang="en">Your discussions are private and respectful of our cultural values.</span></p>
                <div class="join-prompt">
                    <p data-lang="en">Would you like to join the discussion?</p>
                    <button class="btn-purple" id="joinDiscussionBtn">Join Discussion</button>
                </div>
            </div>
            
            <div class="forum-topics">
                <div class="topic-card">
                    <h3 data-lang="en">Cultural Practices & Traditions</h3>
                    <p data-lang="en">Discuss traditional ceremonies, songs, and daily practices</p>
                    <button class="btn-purple join-topic-btn" data-topic="Cultural Practices">Join Discussion</button>
                </div>
                <div class="topic-card">
                    <h3 data-lang="en">Community Values & Respect</h3>
                    <p data-lang="en">Share insights on Maasai values and their modern relevance</p>
                    <button class="btn-purple join-topic-btn" data-topic="Community Values">Join Discussion</button>
                </div>
                <div class="topic-card">
                    <h3 data-lang="en">Youth & Cultural Learning</h3>
                    <p data-lang="en">How can young people stay connected to their heritage?</p>
                    <button class="btn-purple join-topic-btn" data-topic="Youth Learning">Join Discussion</button>
                </div>
                <div class="topic-card">
                    <h3 data-lang="en">Elders' Wisdom & Oral Traditions</h3>
                    <p data-lang="en">Stories and knowledge passed down through generations</p>
                    <button class="btn-purple join-topic-btn" data-topic="Elders Wisdom">Join Discussion</button>
                </div>
            </div>
            
            <div class="discussion-form" id="discussionForm" style="display: none;">
                <h2 data-lang="en">Share Your Thoughts</h2>
                <form id="newDiscussion">
                    <div class="form-group">
                        <label for="discussionTopic" data-lang="en">Discussion Topic</label>
                        <input type="text" id="discussionTopic" class="form-control" readonly>
                    </div>
                    <div class="form-group">
                        <input type="text" id="discussionTitle" class="form-control" placeholder="Discussion title" data-placeholder-en="Discussion title" data-placeholder-sw="Kichwa cha mjadala" data-placeholder-maa="Enkutuk enkitokitin">
                    </div>
                    <div class="form-group">
                        <textarea id="discussionContent" class="form-control" rows="4" placeholder="What would you like to share?" data-placeholder-en="What would you like to share?" data-placeholder-sw="Ungependa kushare nini?" data-placeholder-maa="Ake eng'eno ilo ing'ada?"></textarea>
                    </div>
                    <div class="form-group">
                        <label>
                            <input type="checkbox" id="anonymousPost">
                            <span data-lang="en">Post anonymously</span>
                        </label>
                    </div>
                    <button type="submit" class="btn">Post Discussion</button>
                </form>
            </div>
            
            <div class="discussions-container" id="discussionsContainer">
                <h2 data-lang="en">Recent Discussions</h2>
                <!-- Discussions will be added here dynamically -->
            </div>
        </section>
    </main>

    <!-- Chatbot -->
    <div class="chatbot-container">
        <div class="chatbot-icon" id="chatbotToggle">💬</div>
        <div class="chatbot-window" id="chatbotWindow">
            <div class="chatbot-header">
                <h3>Living Threads Assistant</h3>
                <button id="closeChatbot">✕</button>
            </div>
            <div class="chatbot-messages" id="chatbotMessages">
                <div class="message bot-message">
                    Hello! How can I help you learn about Maasai culture today?
                </div>
            </div>
            <div class="chatbot-input">
                <input type="text" id="chatbotInput" placeholder="Type your question...">
                <button id="sendMessage">➤</button>
            </div>
        </div>
    </div>

    <!-- Footer (not shown on login page) -->
    <footer id="main-footer">
        <div class="container footer-content">
            <div class="footer-section">
                <h3>Living Threads</h3>
                <p>Preserving and promoting Maasai intangible cultural heritage through digital innovation.</p>
                <div class="social-icons">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Contact Us</h3>
                <p><i class="fas fa-envelope"></i> info@livingthreads.org</p>
                <p><i class="fas fa-phone"></i> +254 700 123 456</p>
                <p><i class="fas fa-map-marker-alt"></i> Nairobi, Kenya</p>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <a href="#" class="nav-link" data-page="home">Home</a>
                <a href="#" class="nav-link" data-page="knowmore">Know More</a>
                <a href="#" class="nav-link" data-page="forum">Community Forum</a>
                <a href="#" class="nav-link" data-page="login">Login</a>
            </div>
        </div>
        <div class="container footer-bottom">
            <p>&copy; 2023 Living Threads - Preserving Maasai Intangible Heritage. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // DOM Elements
        const themeToggle = document.getElementById('themeToggle');
        const navLinks = document.querySelectorAll('.nav-link');
        const pages = document.querySelectorAll('.page');
        const langButtons = document.querySelectorAll('.lang-btn');
        const loginForm = document.getElementById('loginForm');
        const signupForm = document.getElementById('signupForm');
        const showSignup = document.getElementById('showSignup');
        const showLogin = document.getElementById('showLogin');
        const chatbotToggle = document.getElementById('chatbotToggle');
        const chatbotWindow = document.getElementById('chatbotWindow');
        const closeChatbot = document.getElementById('closeChatbot');
        const sendMessage = document.getElementById('sendMessage');
        const chatbotInput = document.getElementById('chatbotInput');
        const chatbotMessages = document.getElementById('chatbotMessages');
        const addActivity = document.getElementById('addActivity');
        const activityInput = document.getElementById('activityInput');
        const activitiesList = document.getElementById('activitiesList');
        const totalActivities = document.getElementById('totalActivities');
        const newDiscussion = document.getElementById('newDiscussion');
        const discussionsContainer = document.getElementById('discussionsContainer');
        const faqQuestions = document.querySelectorAll('.faq-question');
        const hamburgerMenu = document.querySelector('.hamburger-menu');
        const navMenu = document.getElementById('navMenu');
        const mainFooter = document.getElementById('main-footer');
        const joinDiscussionBtn = document.getElementById('joinDiscussionBtn');
        const discussionForm = document.getElementById('discussionForm');
        const joinTopicButtons = document.querySelectorAll('.join-topic-btn');
        const discussionTopic = document.getElementById('discussionTopic');

        // Error message elements
        const emailError = document.getElementById('emailError');
        const passwordError = document.getElementById('passwordError');
        const signupEmailError = document.getElementById('signupEmailError');
        const signupPasswordError = document.getElementById('signupPasswordError');
        const confirmPasswordError = document.getElementById('confirmPasswordError');

        // Current language
        let currentLang = 'en';
        let isLoggedIn = false;

        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            // Load saved theme
            const savedTheme = localStorage.getItem('theme');
            if (savedTheme === 'dark') {
                document.body.classList.add('dark-theme');
                themeToggle.textContent = '☀️';
            }
            
            // Check if user is logged in
            const savedLogin = localStorage.getItem('isLoggedIn');
            if (savedLogin === 'true') {
                isLoggedIn = true;
                // Show home page instead of login
                document.getElementById('login').classList.remove('active-page');
                document.getElementById('home').classList.add('active-page');
                updateFooter();
            }
            
            // Load saved activities
            loadActivities();
            
            // Load saved discussions
            loadDiscussions();
            
            // Load chatbot history
            loadChatHistory();
            
            // Set up language placeholders
            updatePlaceholders();
            
            // Set footer visibility based on current page
            updateFooter();
        });

        // Email validation function
        function isValidEmail(email) {
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        }

        // Join Discussion Button
        joinDiscussionBtn.addEventListener('click', function() {
            if (!isLoggedIn) {
                alert('Please log in to join discussions');
                return;
            }
            
            discussionTopic.value = 'General Discussion';
            discussionForm.style.display = 'block';
            joinDiscussionBtn.style.display = 'none';
            discussionForm.scrollIntoView({ behavior: 'smooth' });
        });

        // Handle topic-specific join buttons
        joinTopicButtons.forEach(button => {
            button.addEventListener('click', function() {
                if (!isLoggedIn) {
                    alert('Please log in to join discussions');
                    return;
                }
                
                const topic = this.getAttribute('data-topic');
                discussionTopic.value = topic;
                discussionForm.style.display = 'block';
                joinDiscussionBtn.style.display = 'none';
                discussionForm.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Update footer based on current page
        function updateFooter() {
            const activePage = document.querySelector('.active-page');
            
            if (activePage && activePage.id === 'login') {
                mainFooter.style.display = 'none';
            } else {
                mainFooter.style.display = 'block';
            }
        }

        // Hamburger menu toggle
        hamburgerMenu.addEventListener('click', function() {
            navMenu.classList.toggle('active');
        });

        // Close menu when clicking outside
        document.addEventListener('click', function(event) {
            if (!event.target.closest('.nav-menu') && !event.target.closest('.hamburger-menu')) {
                navMenu.classList.remove('active');
            }
        });

        // Theme Toggle
        themeToggle.addEventListener('click', function() {
            document.body.classList.toggle('dark-theme');
            if (document.body.classList.contains('dark-theme')) {
                localStorage.setItem('theme', 'dark');
                themeToggle.textContent = '☀️';
            } else {
                localStorage.setItem('theme', 'light');
                themeToggle.textContent = '🌙';
            }
        });

        // Navigation
        navLinks.forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                
                // Check if user is logged in for non-login pages
                const targetPage = this.getAttribute('data-page');
                if (targetPage !== 'login' && !isLoggedIn) {
                    alert('Please log in to access this page');
                    return;
                }
                
                const targetSection = this.getAttribute('data-section');
                
                // Hide all pages
                pages.forEach(page => {
                    page.classList.remove('active-page');
                });
                
                // Show target page
                document.getElementById(targetPage).classList.add('active-page');
                
                // Scroll to specific section if specified
                if (targetSection) {
                    setTimeout(() => {
                        const section = document.getElementById(targetSection + '-section');
                        if (section) {
                            section.scrollIntoView({ behavior: 'smooth' });
                        }
                    }, 100);
                }
                
                // Update footer visibility
                updateFooter();
                
                // Close navigation menu
                navMenu.classList.remove('active');
            });
        });

        // Language Toggle
        langButtons.forEach(button => {
            button.addEventListener('click', function() {
                // Remove active class from all buttons
                langButtons.forEach(btn => btn.classList.remove('active'));
                
                // Add active class to clicked button
                this.classList.add('active');
                
                // Update current language
                currentLang = this.getAttribute('data-lang');
                
                // Update all text elements with data-lang attribute
                updateLanguageText();
                
                // Update placeholders
                updatePlaceholders();
            });
        });

        // Update language text
        function updateLanguageText() {
            const textElements = document.querySelectorAll('[data-lang]');
            textElements.forEach(element => {
                // For this demo, we're just toggling between English and placeholders
                // In a real implementation, you would have translations for all text
                if (currentLang !== 'en') {
                    const originalText = element.textContent;
                    element.setAttribute('data-original', originalText);
                    
                    // Simple demonstration of language change
                    if (currentLang === 'sw') {
                        if (originalText.includes('Welcome')) element.textContent = 'Karibu Living Threads';
                        else if (originalText.includes('Email Address')) element.textContent = 'Barua Pepe';
                        else if (originalText.includes('Password')) element.textContent = 'Nenosiri';
                        // Add more translations as needed
                    } else if (currentLang === 'maa') {
                        if (originalText.includes('Welcome')) element.textContent = 'Supa Living Threads';
                        else if (originalText.includes('Email Address')) element.textContent = 'Enkop Email';
                        else if (originalText.includes('Password')) element.textContent = 'Enkop Password';
                        // Add more translations as needed
                    }
                } else {
                    // Restore original English text
                    const originalText = element.getAttribute('data-original');
                    if (originalText) {
                        element.textContent = originalText;
                    }
                }
            });
        }

        // Update form placeholders based on language
        function updatePlaceholders() {
            const inputs = document.querySelectorAll('[data-placeholder-en]');
            inputs.forEach(input => {
                const placeholderKey = `data-placeholder-${currentLang}`;
                input.placeholder = input.getAttribute(placeholderKey) || input.getAttribute('data-placeholder-en');
            });
        }

        // Login/Signup Form Toggle
        showSignup.addEventListener('click', function(e) {
            e.preventDefault();
            loginForm.style.display = 'none';
            signupForm.style.display = 'block';
            showSignup.parentElement.style.display = 'none';
            document.getElementById('signupFooter').style.display = 'block';
        });

        showLogin.addEventListener('click', function(e) {
            e.preventDefault();
            signupForm.style.display = 'none';
            loginForm.style.display = 'block';
            document.getElementById('signupFooter').style.display = 'none';
            showSignup.parentElement.style.display = 'block';
        });

        // Form Submissions
        loginForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Reset error messages
            emailError.style.display = 'none';
            passwordError.style.display = 'none';
            
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            
            let isValid = true;
            
            // Validate email
            if (!isValidEmail(email)) {
                emailError.style.display = 'block';
                isValid = false;
            }
            
            // Validate password
            if (password.length === 0) {
                passwordError.style.display = 'block';
                isValid = false;
            }
            
            if (isValid) {
                // Simulate successful login
                isLoggedIn = true;
                localStorage.setItem('isLoggedIn', 'true');
                
                // Redirect to home page
                pages.forEach(page => {
                    page.classList.remove('active-page');
                });
                document.getElementById('home').classList.add('active-page');
                updateFooter();
            }
        });

        signupForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Reset error messages
            signupEmailError.style.display = 'none';
            signupPasswordError.style.display = 'none';
            confirmPasswordError.style.display = 'none';
            
            const email = document.getElementById('signupEmail').value;
            const password = document.getElementById('signupPassword').value;
            const confirmPassword = document.getElementById('confirmPassword').value;
            
            let isValid = true;
            
            // Validate email
            if (!isValidEmail(email)) {
                signupEmailError.style.display = 'block';
                isValid = false;
            }
            
            // Validate password
            if (password.length < 6) {
                signupPasswordError.style.display = 'block';
                isValid = false;
            }
            
            // Validate password confirmation
            if (password !== confirmPassword) {
                confirmPasswordError.style.display = 'block';
                isValid = false;
            }
            
            if (isValid) {
                // Simulate successful signup and login
                isLoggedIn = true;
                localStorage.setItem('isLoggedIn', 'true');
                
                // Redirect to home page
                pages.forEach(page => {
                    page.classList.remove('active-page');
                });
                document.getElementById('home').classList.add('active-page');
                updateFooter();
            }
        });

        // Chatbot Functionality
        chatbotToggle.addEventListener('click', function() {
            chatbotWindow.style.display = 'flex';
        });

        closeChatbot.addEventListener('click', function() {
            chatbotWindow.style.display = 'none';
        });

        sendMessage.addEventListener('click', sendChatMessage);
        chatbotInput.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                sendChatMessage();
            }
        });

        function sendChatMessage() {
            const message = chatbotInput.value.trim();
            if (message === '') return;
            
            // Add user message
            addMessageToChat(message, 'user');
            chatbotInput.value = '';
            
            // Generate bot response
            setTimeout(() => {
                let response = "I'm here to help you learn about Maasai culture. How can I assist you today?";
                
                if (message.toLowerCase().includes('song') || message.toLowerCase().includes('music')) {
                    response = "Maasai songs are an important part of our culture. They are used in ceremonies, storytelling, and daily life. Would you like to learn about a specific type of song?";
                } else if (message.toLowerCase().includes('story') || message.toLowerCase().includes('elder')) {
                    response = "Oral storytelling is how Maasai history and values are passed down. Elders share wisdom through narratives that often feature animals and nature.";
                } else if (message.toLowerCase().includes('ceremony') || message.toLowerCase().includes('eunoto') || message.toLowerCase().includes('enkipaata')) {
                    response = "Maasai ceremonies mark important life transitions. Eunoto is the warrior graduation ceremony, and Enkipaata is the initiation for young boys.";
                } else if (message.toLowerCase().includes('bead') || message.toLowerCase().includes('jewelry')) {
                    response = "Maasai beadwork is not just decorative - different colors and patterns communicate social status, age, and marital status.";
                }
                
                addMessageToChat(response, 'bot');
                saveChatHistory();
            }, 1000);
        }

        function addMessageToChat(message, sender) {
            const messageDiv = document.createElement('div');
            messageDiv.classList.add('message');
            messageDiv.classList.add(sender === 'user' ? 'user-message' : 'bot-message');
            messageDiv.textContent = message;
            
            chatbotMessages.appendChild(messageDiv);
            chatbotMessages.scrollTop = chatbotMessages.scrollHeight;
        }

        function saveChatHistory() {
            const messages = [];
            document.querySelectorAll('.message').forEach(msg => {
                messages.push({
                    text: msg.textContent,
                    type: msg.classList.contains('user-message') ? 'user' : 'bot'
                });
            });
            localStorage.setItem('chatHistory', JSON.stringify(messages));
        }

        function loadChatHistory() {
            const savedChat = localStorage.getItem('chatHistory');
            if (savedChat) {
                const messages = JSON.parse(savedChat);
                // Skip the first message (the initial bot greeting)
                for (let i = 1; i < messages.length; i++) {
                    addMessageToChat(messages[i].text, messages[i].type);
                }
            }
        }

        // Impact Tracker
        addActivity.addEventListener('click', function() {
            const activity = activityInput.value.trim();
            if (activity === '') return;
            
            addActivityToList(activity);
            activityInput.value = '';
            
            // Update total
            updateActivityCount();
            
            // Save to localStorage
            saveActivities();
        });

        function addActivityToList(activity) {
            const li = document.createElement('li');
            li.classList.add('impact-item');
            li.innerHTML = `
                <span>${activity}</span>
                <button class="delete-activity">×</button>
            `;
            
            li.querySelector('.delete-activity').addEventListener('click', function() {
                li.remove();
                updateActivityCount();
                saveActivities();
            });
            
            activitiesList.appendChild(li);
        }

        function updateActivityCount() {
            totalActivities.textContent = activitiesList.children.length;
        }

        function saveActivities() {
            const activities = [];
            activitiesList.querySelectorAll('.impact-item span').forEach(item => {
                activities.push(item.textContent);
            });
            localStorage.setItem('culturalActivities', JSON.stringify(activities));
        }

        function loadActivities() {
            const savedActivities = localStorage.getItem('culturalActivities');
            if (savedActivities) {
                const activities = JSON.parse(savedActivities);
                activities.forEach(activity => {
                    addActivityToList(activity);
                });
                updateActivityCount();
            }
        }

        // Forum Discussions
        newDiscussion.addEventListener('submit', function(e) {
            e.preventDefault();
            const topic = document.getElementById('discussionTopic').value;
            const title = document.getElementById('discussionTitle').value;
            const content = document.getElementById('discussionContent').value;
            const anonymous = document.getElementById('anonymousPost').checked;
            
            if (title.trim() === '' || content.trim() === '') return;
            
            addDiscussionToList(topic, title, content, anonymous);
            
            // Reset form
            document.getElementById('discussionTitle').value = '';
            document.getElementById('discussionContent').value = '';
            document.getElementById('anonymousPost').checked = false;
            discussionForm.style.display = 'none';
            joinDiscussionBtn.style.display = 'block';
            
            // Save discussions
            saveDiscussions();
        });

        function addDiscussionToList(topic, title, content, anonymous) {
            const discussionDiv = document.createElement('div');
            discussionDiv.classList.add('discussion-item');
            
            const author = anonymous ? 'Anonymous' : 'User';
            const timestamp = new Date().toLocaleDateString();
            
            discussionDiv.innerHTML = `
                <div class="discussion-meta">
                    <span>${author}</span>
                    <span>${timestamp}</span>
                </div>
                <div class="discussion-topic">
                    <strong>Topic:</strong> ${topic}
                </div>
                <h3>${title}</h3>
                <p>${content}</p>
            `;
            
            discussionsContainer.appendChild(discussionDiv);
        }

        function saveDiscussions() {
            const discussions = [];
            discussionsContainer.querySelectorAll('.discussion-item').forEach(item => {
                const meta = item.querySelector('.discussion-meta');
                const topic = item.querySelector('.discussion-topic').textContent.replace('Topic:', '').trim();
                const author = meta.children[0].textContent;
                const date = meta.children[1].textContent;
                const title = item.querySelector('h3').textContent;
                const content = item.querySelector('p').textContent;
                
                discussions.push({
                    topic: topic,
                    author: author,
                    date: date,
                    title: title,
                    content: content
                });
            });
            localStorage.setItem('forumDiscussions', JSON.stringify(discussions));
        }

        function loadDiscussions() {
            const savedDiscussions = localStorage.getItem('forumDiscussions');
            if (savedDiscussions) {
                const discussions = JSON.parse(savedDiscussions);
                discussions.forEach(discussion => {
                    addDiscussionToList(
                        discussion.topic,
                        discussion.title, 
                        discussion.content, 
                        discussion.author === 'Anonymous'
                    );
                });
            }
        }

        // FAQ Accordion
        faqQuestions.forEach(question => {
            question.addEventListener('click', function() {
                const answer = this.nextElementSibling;
                const isActive = answer.classList.contains('active');
                
                // Close all answers
                document.querySelectorAll('.faq-answer').forEach(ans => {
                    ans.classList.remove('active');
                });
                
                // Reset all icons
                document.querySelectorAll('.faq-question span:last-child').forEach(icon => {
                    icon.textContent = '+';
                });
                
                // If this answer wasn't active, open it
                if (!isActive) {
                    answer.classList.add('active');
                    this.querySelector('span:last-child').textContent = '−';
                }
            });
        });
    </script>
</body>
</html>
