
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KVM Pro Ug - Content Creator Platform</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        /* Add watermark styles */
        .watermark {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 24px;
            color: #808080; /* grayish font */
            font-weight: bold;
            z-index: -1; /* Ensure watermark is behind other elements */
        }
        
        /* Add header box styles */
        .header-box {
            background-color: #ADD8E6; /* light blue */
            width: 100%;
            height: 60px;
            display: flex;
            justify-content: space-around;
            align-items: center;
            font-size: 18px;
            font-weight: bold;
        }
        
        /* Add header links styles */
        .header-links {
            text-decoration: none;
            color: #000; /* black */
            position: relative;
        }
        
        /* Add header links hover styles */
        .header-links:hover {
            text-decoration: underline;
            color: #337ab7; /* blue */
        }
        
        /* Add pop-up animation styles */
        .pop-up {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(255, 255, 255, 0.5);
            display: none;
            justify-content: center;
            align-items: center;
            animation: pop-up 0.5s ease-in-out;
        }
        
        .pop-up.show {
            display: flex;
        }
        
        @keyframes pop-up {
            0% {
                transform: scale(0);
            }
            100% {
                transform: scale(1);
            }
        }
        
        /* Add search bar styles */
        .search-bar {
            padding: 10px;
            border: none;
            border-radius: 5px;
            width: 200px;
            height: 30px;
            font-size: 16px;
        }
        
        /* Add login form styles */
        .login-form {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: #fff;
            padding: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            width: 300px;
            height: 200px;
            display: none;
        }
        
        .login-form.show {
            display: block;
        }
        
        /* Add logout button styles */
        .logout-btn {
            background-color: #337ab7; /* blue */
            color: #fff; /* white */
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
        
        .logout-btn:hover {
            background-color: #23527c; /* darker blue */
        }
    </style>
</head>
<body>
    <header>
        <div class="header-box">
            <a href="#" class="header-links">Home</a>
            <a href="#" class="header-links">Explore</a>
            <a href="#" class="header-links">Upload</a>
            <a href="#" class="header-links">Chats</a>
            <a href="#" class="header-links">Comments</a>
            <a href="#" class="header-links">Live Activity</a>
            <input type="search" class="search-bar" placeholder="Search...">
            <button class="logout-btn" id="logout-btn">Logout</button>
            <button class="login-btn" id="login-btn" style="display: none;">Login</button>
        </div>
    </header>
    <main>
        <!-- Add content here -->
        <featured-content></featured-content>
        <latest-uploads></latest-uploads>
        <call-to-action></call-to-action>
        <!-- Add watermark element -->
        <div class="watermark">Vincent Edits ug Website</div>
        <!-- Add pop-up element -->
        <div class="pop-up">
            <h1>Category Selected!</h1>
            <p>This is a pop-up message.</p>
        </div>
        <!-- Add login form element -->
        <div class="login-form">
            <h2>Login to KVM Pro Ug</h2>
            <form>
                <label for="username">Username
