<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Raw-yal Craft</title>
<style>
    body {
        font-family: 'Poppins', sans-serif;
        margin: 0;
        background: #f5f5f0;
        color: #333;
    }

    header {
        text-align: center;
        padding: 40px 20px;
        background: #fff;
        box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        position: sticky;
        top: 0;
        z-index: 10;
    }

    /* Animated Title */
    h1 {
        font-size: 3em;
        animation: colorShift 6s infinite;
    }

    @keyframes colorShift {
        0% { color: red; }
        33% { color: gold; }
        66% { color: green; }
        100% { color: red; }
    }

    nav {
        margin-top: 20px;
    }

    nav a {
        margin: 0 15px;
        text-decoration: none;
        color: #333;
        font-weight: 600;
        transition: color 0.3s;
    }

    nav a:hover {
        color: #555;
    }

    section {
        display: none;
        padding: 50px 20px;
        max-width: 900px;
        margin: 0 auto;
        background: #fff;
        box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        border-radius: 8px;
        margin-top: 30px;
        animation: fadeIn 0.5s ease-in-out;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    section.active {
        display: block;
    }

    .services-list {
        list-style: none;
        padding: 0;
    }

    .services-list li {
        margin-bottom: 10px;
        font-size: 1.1em;
    }

    .membership-form input, 
    .membership-form button {
        padding: 10px;
        margin-top: 10px;
        width: 100%;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 1em;
    }

    .membership-form button {
        background: #333;
        color: white;
        cursor: pointer;
    }

    .gallery-container {
        display: flex;
        flex-wrap: wrap;
        gap: 15px;
    }

    .gallery-container img {
        width: 200px;
        height: 200px;
        object-fit: cover;
        border-radius: 8px;
        box-shadow: 0 2px 6px rgba(0,0,0,0.2);
    }

    .upload-btn {
        margin: 20px 0;
    }

    footer {
        text-align: center;
        padding: 20px;
        margin-top: 40px;
        background: #fff;
        box-shadow: 0 -2px 8px rgba(0,0,0,0.05);
    }
</style>
</head>
<body>

<header>
    <h1>Raw-yal Craft</h1>
    <nav>
        <a href="#" onclick="showSection('home')">Home</a>
        <a href="#" onclick="showSection('about')">About</a>
        <a href="#" onclick="showSection('services')">Services</a>
        <a href="#" onclick="showSection('membership')">Membership</a>
        <a href="#" onclick="showSection('gallery')">Gallery</a>
        <a href="#" onclick="showSection('contact')">Contact</a>
    </nav>
</header>

<!-- HOME -->
<section id="home" class="active">
    <h2>Welcome to Raw-yal Craft</h2>
    <p>Where creativity meets craftsmanship. We specialize in creating custom art pieces, handcrafted leather goods, beautiful landscaping designs, and elegant refurbishments that breathe life into your space. Discover art that tells a story — your story.</p>
</section>

<!-- ABOUT -->
<section id="about">
    <h2>About Us</h2>
    <p><strong>Raw-yal Craft</strong> is a creative studio passionate about handmade excellence. From detailed leather crafts to artistic refurbishments and outdoor landscaping, our goal is to blend art with everyday living. We serve both individual and corporate clients, offering bespoke designs crafted with love, precision, and cultural flair.</p>
</section>

<!-- SERVICES -->
<section id="services">
    <h2>Our Services</h2>
    <ul class="services-list">
        <li><strong>Leather Crafts & Designs:</strong> Custom handbags, belts, and decor with authentic craftsmanship.</li>
        <li><strong>Landscaping:</strong> Transforming outdoor spaces into natural works of art.</li>
        <li><strong>Refurbishment:</strong> Restoring furniture and decor with artistic touches.</li>
        <li><strong>Arts & Crafts:</strong> Handmade art, paintings, and decorative creations.</li>
    </ul>
</section>

<!-- MEMBERSHIP -->
<section id="membership">
    <h2>Join Our Membership</h2>
    <p>Become part of the Raw-yal family and enjoy exclusive discounts, early access to new collections, and personalized design offers.</p>
    <form class="membership-form" onsubmit="joinMembership(event)">
        <input type="text" id="name" placeholder="Full Name" required />
        <input type="email" id="email" placeholder="Email Address" required />
        <button type="submit">Join Now</button>
    </form>
    <p id="join-msg" style="color:green;font-weight:600;"></p>
</section>

<!-- GALLERY -->
<section id="gallery">
    <h2>Gallery</h2>
    <p>Browse through our artistic creations or upload your favorite Raw-yal Craft moments!</p>
    <input type="file" id="upload" class="upload-btn" accept="image/*" onchange="uploadImage(event)">
    <div class="gallery-container" id="galleryContainer"></div>
</section>

<!-- CONTACT -->
<section id="contact">
    <h2>Contact Us</h2>
    <p>Have questions or custom project requests? We’d love to hear from you.</p>
    <p><strong>Email:</strong> <a href="mailto:otshepengevens@gmail.com">otshepengevens@gmail.com</a></p>
</section>

<footer>
    <p>&copy; <span id="year"></span> Raw-yal Craft. All rights reserved.</p>
</footer>

<script>
    function showSection(id) {
        document.querySelectorAll('section').forEach(sec => sec.classList.remove('active'));
        document.getElementById(id).classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function joinMembership(e) {
        e.preventDefault();
        const name = document.getElementById('name').value.trim();
        document.getElementById('join-msg').textContent = `Thank you, ${name}! You’ve successfully joined Raw-yal Craft’s membership.`;
        e.target.reset();
    }

    function uploadImage(event) {
        const file = event.target.files[0];
        if (!file) return;
        const reader = new FileReader();
        reader.onload = function(e) {
            const img = document.createElement('img');
            img.src = e.target.result;
            document.getElementById('galleryContainer').appendChild(img);
        }
        reader.readAsDataURL(file);
    }

    document.getElementById("year").textContent = new Date().getFullYear();
</script>

</body>
</html>
