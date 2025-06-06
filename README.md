<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Landing Page</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            padding-top: 60px; /* Space for fixed header */
        }

        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #333;
            color: white;
            display: flex;
            justify-content: space-around;
            align-items: center;
            height: 60px;
            z-index: 1000;
            transition: background-color 0.3s ease;
        }

        .navbar.scrolled {
            background-color: #555;
        }

        .navbar a {
            color: white;
            text-decoration: none;
            padding: 15px 20px;
            display: block;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        .navbar a:hover {
            background-color: #777;
            color: #ffcc00;
        }

        .content-section {
            height: 800px; /* To enable scrolling */
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2em;
            color: #333;
            background-color: #f4f4f4;
            border-bottom: 1px solid #ddd;
        }

        .content-section:nth-child(even) {
            background-color: #e2e2e2;
        }

        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                height: auto;
            }

            .navbar a {
                width: 100%;
                text-align: center;
                padding: 10px 0;
            }

            .navbar.scrolled {
                background-color: #555;
            }
        }
    </style>
</head>
<body>

    <nav class="navbar" id="mainNavbar">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#contact">Contact</a>
    </nav>

    <div id="home" class="content-section">
        <h2>Home Section</h2>
    </div>
    <div id="about" class="content-section">
        <h2>About Section</h2>
    </div>
    <div id="services" class="content-section">
        <h2>Services Section</h2>
    </div>
    <div id="contact" class="content-section">
        <h2>Contact Section</h2>
    </div>

    <script>
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('mainNavbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });
    </script>

</body>
</html>
