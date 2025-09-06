<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KVM Pro Ug - Content Creator Platform</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        /* Existing styles ... */
        /* ... (unchanged, see your previous code above) ... */

        /* Lower third password style */
        .lowerthird {
            background: rgba(0,0,0,0.7);
            color: #fff;
            padding: 8px 12px;
            border-radius: 8px;
            font-size: 16px;
            width: 100%;
            margin-top: 6px;
            box-sizing: border-box;
            text-align: center;
        }
        /* Hide login when logged in */
        .hide { display: none !important; }
    </style>
</head>
<body>
    <header>
        <div class="header-box">
            <!-- Logo image -->
            <img src="https://yt3.googleusercontent.com/cwou45QPyPWeA5QqGm7pJoDkvgzz2fMRv4nPtoyrBSKjPhmm1PLBwovCa7N0pkeol4dOqTie=s160-c-k-c0x00ffffff-no-rj" alt="KVM Pro Ug Logo" class="logo">
            <a href="#" class="header-links">Home</a>
            <a href="#" class="header-links">Explore</a>
            <a href="#" class="header-links">Upload</a>
            <a href="#" class="header-links">Chats</a>
            <a href="#" class="header-links">Comments</a>
            <a href="#" class="header-links">Live Activity</a>
            <input type="search" class="search-bar" placeholder="Search...">
            <button class="logout-btn" id="logout-btn" style="display:none;">Logout</button>
            <button class="login-btn" id="login-btn">Login</button>
        </div>
    </header>
    <main>
        <!-- ... featured-content, latest-uploads, call-to-action ... -->
        <!-- Existing sections unchanged ... -->

        <!-- Watermark, pop-up, etc. unchanged ... -->

        <!-- Login form (updated) -->
        <div class="login-form" id="login-form">
            <h2>Login to KVM Pro Ug</h2>
            <form id="user-login-form" autocomplete="off" onsubmit="return false;">
                <label for="username">Username</label>
                <input type="text" id="username" name="username" required placeholder="Enter username"><br><br>
                <label for="password">Password</label>
                <div class="lowerthird">
                    <input type="password" id="password" name="password" required placeholder="Enter password" style="border:none;background:transparent;color:#fff;width:90%;">
                </div>
                <span id="login-error" style="color:red;display:none;">Wrong password. You are locked out!</span>
                <br>
                <button type="submit" class="logout-btn" style="background:#337ab7;">Login</button>
            </form>
        </div>
    </main>
    <script>
    // LOGIN LOGIC
    const correctUsername = "user"; // Change as needed
    const correctPassword = "kvm123"; // Change as needed

    let lockedOut = false;
    let loggedIn = false;

    const loginForm = document.getElementById("login-form");
    const loginBtn = document.getElementById("login-btn");
    const logoutBtn = document.getElementById("logout-btn");
    const userForm = document.getElementById("user-login-form");
    const loginError = document.getElementById("login-error");

    // Show login form
    loginBtn.onclick = function() {
        loginForm.classList.add("show");
        loginBtn.style.display = "none";
    };

    // Handle login
    userForm.onsubmit = function() {
        if (lockedOut) return false;
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;
        if (username === correctUsername && password === correctPassword) {
            loggedIn = true;
            loginForm.classList.remove("show");
            logoutBtn.style.display = "";
            loginBtn.style.display = "none";
        } else {
            // Wrong password, lock user out
            lockedOut = true;
            loginError.style.display = "inline";
            setTimeout(() => {
                loginForm.classList.remove("show");
                loginBtn.style.display = "";
            }, 2000);
        }
        return false;
    };

    // Handle logout
    logoutBtn.onclick = function() {
        loggedIn = false;
        loginBtn.style.display = "";
        logoutBtn.style.display = "none";
    };

    // Optional: Show login form at start
    // loginForm.classList.add("show");
    </script>
</body>
</html>
