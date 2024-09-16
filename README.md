<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AlHabeeby International Group of Schools</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: url('background-image.jpg') no-repeat center center fixed;
            background-size: cover;
            color: #fff;
            text-align: center;
        }
        .header, .introduction, .news, .contact-info, .form-container {
            max-width: 800px;
            margin: auto;
            padding: 20px;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 10px;
        }
        .logo {
            max-width: 200px;
        }
        .button {
            display: inline-block;
            padding: 10px 20px;
            margin: 10px;
            background-color: #007BFF;
            color: white;
            text-decoration: none;
            border-radius: 5px;
            font-size: 16px;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .news-item {
            margin-bottom: 20px;
        }
        .news-title {
            font-size: 1.5em;
            margin-bottom: 10px;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>

    <div id="home">
        <div class="header">
            <img src="logo.png" alt="AlHabeeby International Group of Schools Logo" class="logo">
            <h1>Welcome to AlHabeeby International Group of Schools, Ede</h1>
            <a href="#" onclick="showPage('signup');" class="button">Sign Up</a>
            <a href="#" onclick="showPage('login');" class="button">Login</a>
        </div>

        <div class="introduction">
            <h2>About Us</h2>
            <p>AlHabeeby International Group of Schools, Ede, is dedicated to providing quality education in a nurturing environment. Our mission is to develop students into well-rounded individuals who are prepared for the future. We offer a range of academic programs and extracurricular activities designed to engage and inspire.</p>
        </div>

        <div class="news">
            <h2>Latest News</h2>
            <div class="news-item">
                <h3 class="news-title">New Science Lab Opening</h3>
                <p>We are excited to announce the opening of our new state-of-the-art science laboratory. This new facility will enhance our students' learning experiences with modern equipment and interactive learning tools.</p>
            </div>
            <div class="news-item">
                <h3 class="news-title">Sports Day 2024</h3>
                <p>Our annual Sports Day is just around the corner! Students will have the opportunity to participate in various athletic events and showcase their talents. Join us for a day of fun and competition.</p>
            </div>
        </div>

        <div class="contact-info">
            <p>Address: Atidade Street, Sawmill ALlāhu Lateef, Ede, Osun State</p>
            <p>Email: <a href="mailto:info@alhabeebyigs.com">info@alhabeebyigs.com</a></p>
            <p>Phone: <a href="tel:+2348169545009">+2348169545009</a></p>
        </div>
    </div>

    <div id="signup" class="hidden form-container">
        <h1>Sign Up</h1>
        <form id="signupForm">
            <label for="signupName">Name:</label>
            <input type="text" id="signupName" name="name" required>
            <br>
            <label for="signupEmail">Email:</label>
            <input type="email" id="signupEmail" name="email" required>
            <br>
            <label for="signupPassword">Password:</label>
            <input type="password" id="signupPassword" name="password" required>
            <br>
            <button type="submit">Sign Up</button>
        </form>
        <button onclick="showPage('home');" class="button">Back to Home</button>
    </div>

    <div id="login" class="hidden form-container">
        <h1>Login</h1>
        <form id="loginForm">
            <label for="loginEmail">Email:</label>
            <input type="email" id="loginEmail" name="email" required>
            <br>
            <label for="loginPassword">Password:</label>
            <input type="password" id="loginPassword" name="password" required>
            <br>
            <button type="submit">Login</button>
        </form>
        <button onclick="showPage('home');" class="button">Back to Home</button>
    </div>

    <div id="student-info" class="hidden">
        <h1>Student Information</h1>
        <p>Name: <span id="studentName">[Student Name]</span></p>
        <h2>Scores</h2>
        <ul>
            <li>Mathematics: <span id="scoreMath">[Score]</span></li>
            <li>English: <span id="scoreEnglish">[Score]</span></li>
            <li>Science: <span id="scoreScience">[Score]</span></li>
            <li>History: <span id="scoreHistory">[Score]</span></li>
            <li>Geography: <span id="scoreGeography">[Score]</span></li>
            <li>Literature: <span id="scoreLiterature">[Score]</span></li>
            <li>Art: <span id="scoreArt">[Score]</span></li>
            <li>Music: <span id="scoreMusic">[Score]</span></li>
            <li>Physical Education: <span id="scorePE">[Score]</span></li>
        </ul>
        <button onclick="showPage('home');" class="button">Back to Home</button>
    </div>

    <script>
        function showPage(page) {
            document.getElementById('home').classList.add('hidden');
            document.getElementById('signup').classList.add('hidden');
            document.getElementById('login').classList.add('hidden');
            document.getElementById('student-info').classList.add('hidden');
            document.getElementById(page).classList.remove('hidden');
        }

        // Handle Sign Up
        document.getElementById('signupForm').addEventListener('submit', function(e) {
            e.preventDefault();
            // Simulate successful sign-up
            localStorage.setItem('signedUp', 'true');
            showPage('student-info');
        });

        // Handle Login
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            if (!localStorage.getItem('signedUp')) {
                alert('Please sign up first.');
                return;
            }
            showPage('student-info');
        });

        // Display student info if logged in
        if (localStorage.getItem('signedUp')) {
            showPage('student-info');
        }
    </script>
</body>
</html>
