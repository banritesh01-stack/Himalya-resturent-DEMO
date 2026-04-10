<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Himalayan Bites | Authentic Nepali Restaurant</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { font-family: 'Poppins', sans-serif; background: #0a0a0a; color: #f5f5f5; overflow-x: hidden; }
    a { text-decoration: none; color: inherit; }

    /* NAVBAR */
    nav { position: fixed; top: 0; width: 100%; padding: 1.2rem 8%; display: flex; justify-content: space-between; align-items: center; z-index: 100; background: rgba(10,10,10,0.9); backdrop-filter: blur(10px); border-bottom: 1px solid rgba(201,160,71,0.15); transition: 0.3s; }
    .logo { font-family: 'Playfair Display', serif; font-size: 1.6rem; color: #c9a047; }
    .logo span { color: #fff; }
    nav ul { display: flex; gap: 2.5rem; list-style: none; }
    nav ul a { font-size: 0.9rem; font-weight: 500; color: #ccc; transition: 0.3s; letter-spacing: 1px; text-transform: uppercase; }
    nav ul a:hover { color: #c9a047; }
    .nav-btn { background: #c9a047; color: #0a0a0a !important; padding: 10px 22px; border-radius: 30px; font-weight: 600 !important; }
    .nav-btn:hover { background: #e8b84b !important; color: #0a0a0a !important; }

    /* HERO */
    .hero { height: 100vh; display: flex; align-items: center; justify-content: center; text-align: center; position: relative; background: linear-gradient(rgba(0,0,0,0.65), rgba(0,0,0,0.65)), url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=1600') center/cover no-repeat; }
    .hero-content { max-width: 800px; padding: 0 2rem; animation: fadeUp 1.2s ease; }
    .hero-tag { font-size: 0.85rem; letter-spacing: 4px; text-transform: uppercase; color: #c9a047; margin-bottom: 1.5rem; }
    .hero h1 { font-family: 'Playfair Display', serif; font-size: 5rem; line-height: 1.1; margin-bottom: 1.5rem; }
    .hero h1 span { color: #c9a047; }
    .hero p { font-size: 1.1rem; color: #ccc; margin-bottom: 2.5rem; line-height: 1.8; }
    .hero-btns { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }
    .btn-primary { background: #c9a047; color: #0a0a0a; padding: 14px 36px; border-radius: 30px; font-weight: 600; font-size: 0.95rem; transition: 0.3s; }
    .btn-primary:hover { background: #e8b84b; transform: translateY(-3px); box-shadow: 0 10px 30px rgba(201,160,71,0.3); }
    .btn-outline { border: 1.5px solid #c9a047; color: #c9a047; padding: 14px 36px; border-radius: 30px; font-weight: 600; font-size: 0.95rem; transition: 0.3s; }
    .btn-outline:hover { background: rgba(201,160,71,0.1); transform: translateY(-3px); }
    .scroll-indicator { position: absolute; bottom: 2rem; left: 50%; transform: translateX(-50%); animation: bounce 2s infinite; color: #c9a047; font-size: 1.5rem; }

    /* SECTIONS */
    section { padding: 100px 8%; }
    .section-tag { font-size: 0.8rem; letter-spacing: 4px; text-transform: uppercase; color: #c9a047; margin-bottom: 1rem; }
    .section-title { font-family: 'Playfair Display', serif; font-size: 3rem; margin-bottom: 1.5rem; }
    .section-title span { color: #c9a047; }
    .section-subtitle { color: #999; font-size: 1rem; line-height: 1.8; max-width: 600px; }

    /* ABOUT */
    .about { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
    .about-img { position: relative; }
    .about-img img { width: 100%; border-radius: 16px; height: 500px; object-fit: cover; }
    .about-badge { position: absolute; bottom: -20px; right: -20px; background: #c9a047; color: #0a0a0a; padding: 20px; border-radius: 16px; text-align: center; }
    .about-badge .num { font-size: 2.5rem; font-weight: 700; display: block; }
    .about-badge p { font-size: 0.8rem; font-weight: 600; }
    .about-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-top: 2rem; }
    .stat { background: rgba(201,160,71,0.08); border: 1px solid rgba(201,160,71,0.15); padding: 1.2rem; border-radius: 12px; }
    .stat .num { font-size: 1.8rem; font-weight: 700; color: #c9a047; }
    .stat p { font-size: 0.85rem; color: #999; }

    /* MENU */
    .menu-section { background: #0f0f0f; }
    .menu-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3rem; }
    .menu-tabs { display: flex; gap: 0.5rem; margin-bottom: 2.5rem; }
    .tab { padding: 10px 24px; border-radius: 30px; border: 1px solid rgba(201,160,71,0.2); color: #999; font-size: 0.85rem; cursor: pointer; transition: 0.3s; background: transparent; font-family: inherit; }
    .tab.active, .tab:hover { background: #c9a047; color: #0a0a0a; border-color: #c9a047; font-weight: 600; }
    .menu-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
    .menu-card { background: #1a1a1a; border-radius: 16px; overflow: hidden; border: 1px solid rgba(255,255,255,0.05); transition: 0.3s; }
    .menu-card:hover { transform: translateY(-8px); border-color: rgba(201,160,71,0.3); box-shadow: 0 20px 40px rgba(0,0,0,0.3); }
    .menu-card img { width: 100%; height: 200px; object-fit: cover; transition: 0.5s; }
    .menu-card:hover img { transform: scale(1.05); }
    .menu-card-body { padding: 1.2rem; }
    .menu-card-body h3 { font-size: 1.1rem; margin-bottom: 0.4rem; }
    .menu-card-body p { font-size: 0.85rem; color: #999; margin-bottom: 1rem; line-height: 1.6; }
    .menu-card-footer { display: flex; justify-content: space-between; align-items: center; }
    .price { font-size: 1.2rem; font-weight: 700; color: #c9a047; }
    .add-btn { background: rgba(201,160,71,0.15); color: #c9a047; border: 1px solid rgba(201,160,71,0.3); padding: 8px 16px; border-radius: 20px; font-size: 0.8rem; cursor: pointer; font-family: inherit; transition: 0.3s; }
    .add-btn:hover { background: #c9a047; color: #0a0a0a; }

    /* FEATURES */
    .features-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 2rem; margin-top: 3rem; }
    .feature { text-align: center; padding: 2rem; background: rgba(201,160,71,0.05); border-radius: 16px; border: 1px solid rgba(201,160,71,0.1); transition: 0.3s; }
    .feature:hover { background: rgba(201,160,71,0.1); transform: translateY(-5px); }
    .feature i { font-size: 2.5rem; color: #c9a047; margin-bottom: 1rem; }
    .feature h3 { margin-bottom: 0.5rem; font-size: 1.1rem; }
    .feature p { font-size: 0.85rem; color: #999; line-height: 1.7; }

    /* GALLERY */
    .gallery-grid { display: grid; grid-template-columns: repeat(3, 1fr); grid-template-rows: repeat(2, 220px); gap: 1rem; margin-top: 3rem; }
    .gallery-item { border-radius: 12px; overflow: hidden; }
    .gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: 0.5s; }
    .gallery-item:hover img { transform: scale(1.08); }
    .gallery-item:first-child { grid-row: span 2; }

    /* TESTIMONIALS */
    .testimonials { background: #0f0f0f; }
    .testimonials-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; margin-top: 3rem; }
    .testimonial { background: #1a1a1a; padding: 2rem; border-radius: 16px; border: 1px solid rgba(255,255,255,0.05); }
    .stars { color: #c9a047; margin-bottom: 1rem; font-size: 0.9rem; }
    .testimonial p { font-size: 0.95rem; color: #ccc; line-height: 1.8; margin-bottom: 1.5rem; font-style: italic; }
    .reviewer { display: flex; align-items: center; gap: 1rem; }
    .reviewer-avatar { width: 44px; height: 44px; border-radius: 50%; background: #c9a047; display: flex; align-items: center; justify-content: center; font-weight: 700; color: #0a0a0a; }
    .reviewer-info h4 { font-size: 0.95rem; }
    .reviewer-info p { font-size: 0.8rem; color: #999; }

    /* RESERVATION */
    .reservation { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; }
    .reservation-form { background: #1a1a1a; padding: 2.5rem; border-radius: 20px; border: 1px solid rgba(201,160,71,0.15); }
    .form-group { margin-bottom: 1.2rem; }
    .form-group label { font-size: 0.85rem; color: #999; display: block; margin-bottom: 0.5rem; }
    .form-group input, .form-group select { width: 100%; background: #0a0a0a; border: 1px solid rgba(201,160,71,0.2); padding: 12px 16px; border-radius: 10px; color: #f5f5f5; font-family: inherit; font-size: 0.9rem; transition: 0.3s; }
    .form-group input:focus, .form-group select:focus { outline: none; border-color: #c9a047; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .form-group select option { background: #1a1a1a; }
    .submit-btn { width: 100%; background: #c9a047; color: #0a0a0a; padding: 14px; border-radius: 30px; font-weight: 700; font-size: 1rem; cursor: pointer; border: none; font-family: inherit; transition: 0.3s; margin-top: 0.5rem; }
    .submit-btn:hover { background: #e8b84b; transform: translateY(-2px); }

    /* CONTACT BAR */
    .contact-bar { background: #c9a047; padding: 2rem 8%; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem; }
    .contact-bar .item { display: flex; align-items: center; gap: 1rem; }
    .contact-bar i { font-size: 1.5rem; color: #0a0a0a; }
    .contact-bar h4 { color: #0a0a0a; font-size: 0.8rem; text-transform: uppercase; letter-spacing: 1px; }
    .contact-bar p { color: #3a2800; font-weight: 600; }

    /* FOOTER */
    footer { background: #050505; padding: 3rem 8% 1.5rem; }
    .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 3rem; margin-bottom: 3rem; }
    .footer-logo { font-family: 'Playfair Display', serif; font-size: 1.8rem; color: #c9a047; margin-bottom: 1rem; }
    .footer-about { font-size: 0.85rem; color: #666; line-height: 1.8; }
    .footer-col h4 { color: #c9a047; font-size: 0.85rem; text-transform: uppercase; letter-spacing: 2px; margin-bottom: 1.2rem; }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 0.6rem; }
    .footer-col ul a { font-size: 0.85rem; color: #666; transition: 0.3s; }
    .footer-col ul a:hover { color: #c9a047; }
    .footer-bottom { border-top: 1px solid #1a1a1a; padding-top: 1.5rem; display: flex; justify-content: space-between; align-items: center; }
    .footer-bottom p { font-size: 0.8rem; color: #444; }
    .social-links { display: flex; gap: 1rem; }
    .social-links a { width: 36px; height: 36px; border-radius: 50%; border: 1px solid #333; display: flex; align-items: center; justify-content: center; color: #666; font-size: 0.85rem; transition: 0.3s; }
    .social-links a:hover { border-color: #c9a047; color: #c9a047; }

    /* ANIMATIONS */
    @keyframes fadeUp { from { opacity: 0; transform: translateY(40px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes bounce { 0%, 100% { transform: translateX(-50%) translateY(0); } 50% { transform: translateX(-50%) translateY(-10px); } }
    .reveal { opacity: 0; transform: translateY(40px); transition: all 0.8s ease; }
    .reveal.active { opacity: 1; transform: translateY(0); }

    /* RESPONSIVE */
    @media (max-width: 768px) {
      .hero h1 { font-size: 3rem; }
      .about, .reservation { grid-template-columns: 1fr; }
      .about-badge { right: 10px; }
      .gallery-grid { grid-template-columns: 1fr 1fr; grid-template-rows: auto; }
      .gallery-item:first-child { grid-row: span 1; }
      .footer-grid { grid-template-columns: 1fr; }
      nav ul { display: none; }
      .section-title { font-size: 2rem; }
    }
  </style>
</head>
<body>

  <!-- NAVBAR -->
  <nav>
    <div class="logo">Himalayan<span>Bites</span></div>
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#menu">Menu</a></li>
      <li><a href="#gallery">Gallery</a></li>
      <li><a href="#reservation">Reserve</a></li>
      <li><a href="#reservation" class="nav-btn">Book a Table</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <header class="hero">
    <div class="hero-content">
      <p class="hero-tag">✦ Authentic Nepali Cuisine ✦</p>
      <h1>A Taste of the <span>Himalayas</span></h1>
      <p>Experience the rich flavors of Nepal, crafted with love and traditional recipes passed down through generations.</p>
      <div class="hero-btns">
        <a href="#menu" class="btn-primary">Explore Menu</a>
        <a href="#reservation" class="btn-outline">Reserve a Table</a>
      </div>
    </div>
    <div class="scroll-indicator"><i class="fas fa-chevron-down"></i></div>
  </header>

  <!-- ABOUT -->
  <section id="about">
    <div class="about reveal">
      <div class="about-img">
        <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?w=800" alt="Restaurant interior">
        <div class="about-badge">
          <span class="num">15+</span>
          <p>Years of Excellence</p>
        </div>
      </div>
      <div class="about-content">
        <p class="section-tag">Our Story</p>
        <h2 class="section-title">Where Tradition Meets <span>Flavor</span></h2>
        <p class="section-subtitle">Himalayan Bites was born from a passion for sharing Nepal's rich culinary heritage. Every dish tells a story of mountain villages, ancient spices, and family traditions.</p>
        <div class="about-stats">
          <div class="stat"><div class="num">200+</div><p>Menu Items</p></div>
          <div class="stat"><div class="num">50K+</div><p>Happy Customers</p></div>
          <div class="stat"><div class="num">12</div><p>Expert Chefs</p></div>
          <div class="stat"><div class="num">4.9★</div><p>Average Rating</p></div>
        </div>
      </div>
    </div>
  </section>

  <!-- FEATURES -->
  <section style="padding-top: 0;">
    <div class="reveal">
      <div class="features-grid">
        <div class="feature">
          <i class="fas fa-leaf"></i>
          <h3>Fresh Ingredients</h3>
          <p>Sourced daily from local farms and imported spices straight from Nepal.</p>
        </div>
        <div class="feature">
          <i class="fas fa-fire"></i>
          <h3>Traditional Recipes</h3>
          <p>Authentic recipes passed down through generations of Nepali families.</p>
        </div>
        <div class="feature">
          <i class="fas fa-truck"></i>
          <h3>Fast Delivery</h3>
          <p>Hot and fresh delivery to your doorstep within 30 minutes.</p>
        </div>
        <div class="feature">
          <i class="fas fa-star"></i>
          <h3>5-Star Experience</h3>
          <p>Award-winning service and ambiance that transports you to Nepal.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- MENU -->
  <section id="menu" class="menu-section">
    <div class="reveal">
      <div class="menu-header">
        <div>
          <p class="section-tag">Our Menu</p>
          <h2 class="section-title">Signature <span>Dishes</span></h2>
        </div>
        <a href="#" class="btn-outline" style="white-space: nowrap;">Full Menu →</a>
      </div>
      <div class="menu-tabs">
        <button class="tab active">All</button>
        <button class="tab">Starters</button>
        <button class="tab">Mains</button>
        <button class="tab">Desserts</button>
        <button class="tab">Drinks</button>
      </div>
      <div class="menu-grid">
        <div class="menu-card">
          <img src="https://images.unsplash.com/photo-1534422298391-e4f8c172dddb?w=400" alt="Momo">
          <div class="menu-card-body">
            <h3>Steamed Momo</h3>
            <p>Traditional Nepali dumplings filled with spiced meat, served with tomato achar.</p>
            <div class="menu-card-footer">
              <span class="price">Rs. 280</span>
              <button class="add-btn">+ Add</button>
            </div>
          </div>
        </div>
        <div class="menu-card">
          <img src="https://images.unsplash.com/photo-1565557623262-b51c2513a641?w=400" alt="Dal Bhat">
          <div class="menu-card-body">
            <h3>Dal Bhat Tarkari</h3>
            <p>The heart of Nepali cuisine — lentil soup, rice, and seasonal vegetables.</p>
            <div class="menu-card-footer">
              <span class="price">Rs. 350</span>
              <button class="add-btn">+ Add</button>
            </div>
          </div>
        </div>
        <div class="menu-card">
          <img src="https://images.unsplash.com/photo-1567188040759-fb8a883dc6d8?w=400" alt="Thakali">
          <div class="menu-card-body">
            <h3>Thakali Set</h3>
            <p>A premium set meal from the Thakali community with rich flavors and variety.</p>
            <div class="menu-card-footer">
              <span class="price">Rs. 550</span>
              <button class="add-btn">+ Add</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- GALLERY -->
  <section id="gallery">
    <div class="reveal">
      <p class="section-tag">Gallery</p>
      <h2 class="section-title">Food & <span>Ambiance</span></h2>
      <div class="gallery-grid">
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=800" alt="Gallery 1"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?w=400" alt="Gallery 2"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1540189549336-e6e99c3679fe?w=400" alt="Gallery 3"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1567620905732-2d1ec7ab7445?w=400" alt="Gallery 4"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1476224203421-9ac39bcb3327?w=400" alt="Gallery 5"></div>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section class="testimonials">
    <div class="reveal">
      <p class="section-tag" style="text-align:center;">Testimonials</p>
      <h2 class="section-title" style="text-align:center;">What Our <span>Guests Say</span></h2>
      <div class="testimonials-grid">
        <div class="testimonial">
          <div class="stars">★★★★★</div>
          <p>"The momos here are absolutely incredible. Best Nepali food I've had outside of Kathmandu. The ambiance is warm and welcoming!"</p>
          <div class="reviewer">
            <div class="reviewer-avatar">RK</div>
            <div class="reviewer-info"><h4>Raj Kumar</h4><p>Food Blogger</p></div>
          </div>
        </div>
        <div class="testimonial">
          <div class="stars">★★★★★</div>
          <p>"Dal Bhat Tarkari brought back memories of my trip to Nepal. Authentic flavors, generous portions, and amazing service!"</p>
          <div class="reviewer">
            <div class="reviewer-avatar">SP</div>
            <div class="reviewer-info"><h4>Sunita Pradhan</h4><p>Regular Customer</p></div>
          </div>
        </div>
        <div class="testimonial">
          <div class="stars">★★★★★</div>
          <p>"Perfect place for family gatherings. The Thakali set is a must-try. The staff is incredibly friendly and knowledgeable."</p>
          <div class="reviewer">
            <div class="reviewer-avatar">AM</div>
            <div class="reviewer-info"><h4>Aarav Malla</h4><p>Verified Diner</p></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- RESERVATION -->
  <section id="reservation">
    <div class="reservation reveal">
      <div>
        <p class="section-tag">Reservations</p>
        <h2 class="section-title">Book Your <span>Table</span></h2>
        <p class="section-subtitle">Reserve your spot and enjoy an unforgettable dining experience. We accommodate groups of all sizes.</p>
        <div style="margin-top: 2rem; display: flex; flex-direction: column; gap: 1rem;">
          <div style="display: flex; align-items: center; gap: 1rem; color: #999;">
            <i class="fas fa-map-marker-alt" style="color: #c9a047; width: 20px;"></i>
            <span>Thamel, Kathmandu, Nepal</span>
          </div>
          <div style="display: flex; align-items: center; gap: 1rem; color: #999;">
            <i class="fas fa-clock" style="color: #c9a047; width: 20px;"></i>
            <span>Mon–Sun: 10:00 AM – 10:00 PM</span>
          </div>
          <div style="display: flex; align-items: center; gap: 1rem; color: #999;">
            <i class="fas fa-phone" style="color: #c9a047; width: 20px;"></i>
            <span>+977 01-4567890</span>
          </div>
        </div>
      </div>
      <div class="reservation-form">
        <h3 style="margin-bottom: 1.5rem; font-family: 'Playfair Display', serif; font-size: 1.5rem;">Make a Reservation</h3>
        <div class="form-row">
          <div class="form-group"><label>First Name</label><input type="text" placeholder="Ritesh"></div>
          <div class="form-group"><label>Last Name</label><input type="text" placeholder="Ban"></div>
        </div>
        <div class="form-group"><label>Email</label><input type="email" placeholder="you@example.com"></div>
        <div class="form-row">
          <div class="form-group"><label>Date</label><input type="date"></div>
          <div class="form-group"><label>Time</label><input type="time"></div>
        </div>
        <div class="form-group">
          <label>Guests</label>
          <select>
            <option>1 Person</option>
            <option>2 People</option>
            <option selected>3-4 People</option>
            <option>5-6 People</option>
            <option>7+ People</option>
          </select>
        </div>
        <button class="submit-btn">Reserve Now</button>
      </div>
    </div>
  </section>

  <!-- CONTACT BAR -->
  <div class="contact-bar">
    <div class="item"><i class="fas fa-map-marker-alt"></i><div><h4>Location</h4><p>Thamel, Kathmandu</p></div></div>
    <div class="item"><i class="fas fa-clock"></i><div><h4>Hours</h4><p>10:00 AM – 10:00 PM</p></div></div>
    <div class="item"><i class="fas fa-phone"></i><div><h4>Reservations</h4><p>+977 01-4567890</p></div></div>
    <div class="item"><i class="fas fa-envelope"></i><div><h4>Email</h4><p>hello@himalayanbites.com</p></div></div>
  </div>

  <!-- FOOTER -->
  <footer>
    <div class="footer-grid">
      <div>
        <div class="footer-logo">HimalayanBites</div>
        <p class="footer-about">Bringing the authentic taste of Nepal to your table. Every dish is crafted with love, tradition, and the finest ingredients.</p>
      </div>
      <div class="footer-col">
        <h4>Quick Links</h4>
        <ul>
          <li><a href="#about">About Us</a></li>
          <li><a href="#menu">Our Menu</a></li>
          <li><a href="#gallery">Gallery</a></li>
          <li><a href="#reservation">Reservations</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Follow Us</h4>
        <ul>
          <li><a href="#">Instagram</a></li>
          <li><a href="#">Facebook</a></li>
          <li><a href="#">TripAdvisor</a></li>
          <li><a href="#">Google Maps</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>© 2026 Himalayan Bites. All rights reserved.</p>
      <div class="social-links">
        <a href="#"><i class="fab fa-instagram"></i></a>
        <a href="#"><i class="fab fa-facebook-f"></i></a>
        <a href="#"><i class="fab fa-twitter"></i></a>
      </div>
    </div>
  </footer>

  <script>
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) entry.target.classList.add('active');
      });
    }, { threshold: 0.1 });
    reveals.forEach(r => observer.observe(r));

    document.querySelectorAll('.tab').forEach(tab => {
      tab.addEventListener('click', () => {
        document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
        tab.classList.add('active');
      });
    });
  </script>
</body>
</html>

