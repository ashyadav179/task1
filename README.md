<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Landing Page</title>
  <style>
    /* Reset default margin & padding */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
    }

    /* Navigation bar */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: transparent;
      padding: 15px 50px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      transition: background 0.3s ease, box-shadow 0.3s ease;
      z-index: 1000;
    }

    nav.scrolled {
      background: #333;
      box-shadow: 0px 4px 8px rgba(0,0,0,0.3);
    }

    nav .logo {
      font-size: 24px;
      font-weight: bold;
      color: white;
    }

    nav ul {
      list-style: none;
      display: flex;
      gap: 20px;
    }

    nav ul li {
      display: inline-block;
    }

    nav ul li a {
      text-decoration: none;
      color: white;
      font-size: 18px;
      padding: 8px 15px;
      transition: 0.3s;
    }

    nav ul li a:hover {
      background: #ff9800;
      border-radius: 5px;
    }

    /* Hero Section */
    header {
      height: 100vh;
      background: url('https://picsum.photos/1920/1080') no-repeat center center/cover;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      text-align: center;
    }

    header h1 {
      font-size: 3rem;
    }

    /* Content Sections */
    section {
      padding: 100px 20px;
      text-align: center;
    }

    section:nth-child(even) {
      background: #f4f4f4;
    }

    section:nth-child(odd) {
      background: #e2e2e2;
    }

    /* Responsive */
    @media (max-width: 768px) {
      nav ul {
        flex-direction: column;
        background: #333;
        position: absolute;
        top: 60px;
        right: 0;
        width: 200px;
        display: none;
      }

      nav ul.show {
        display: flex;
      }

      nav .menu-toggle {
        display: block;
        cursor: pointer;
        font-size: 22px;
        color: white;
      }
    }

    .menu-toggle {
      display: none;
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <nav>
    <div class="logo">MyLogo</div>
    <div class="menu-toggle">☰</div>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- Hero Section -->
  <header id="home">
    <h1>Welcome to My Responsive Landing Page</h1>
  </header>

  <!-- Sections -->
  <section id="about">
    <h2>About Us</h2>
    <p>This is the about section.</p>
  </section>

  <section id="services">
    <h2>Our Services</h2>
    <p>This is the services section.</p>
  </section>

  <section id="contact">
    <h2>Contact Us</h2>
    <p>This is the contact section.</p>
  </section>

  <script>
    // Change navbar style when scrolling
    window.addEventListener("scroll", function() {
      const nav = document.querySelector("nav");
      nav.classList.toggle("scrolled", window.scrollY > 50);
    });

    // Toggle menu for mobile
    const menuToggle = document.querySelector(".menu-toggle");
    const navLinks = document.querySelector("nav ul");

    menuToggle.addEventListener("click", () => {
      navLinks.classList.toggle("show");
    });
  </script>
</body>
</html>

