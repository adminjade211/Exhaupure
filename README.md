<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>ExhauPure - Innovating Clean Air for Urban Futures</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    * {margin: 0; padding: 0; box-sizing: border-box; font-family: "Segoe UI", Tahoma, sans-serif;}
    body {background: radial-gradient(ellipse at center, #0b0e13 0%, #050608 100%); color: white; overflow-x: hidden;}
    header {
      display: flex; justify-content: space-between; align-items: center;
      padding: 2rem 5%; backdrop-filter: blur(20px);
      background: rgba(15, 20, 25, 0.2);
      border-bottom: 1px solid rgba(0, 255, 153, 0.2);
      position: fixed; top: 0; width: 100%; z-index: 1000;
    }
    header h1 {font-size: 1.8rem; color: #00ffb3;}
    nav a {
      margin-left: 2rem; color: #fff; text-decoration: none; font-weight: 500;
      transition: color 0.3s;
    }
    nav a:hover {color: #00ffb3;}

    /* HERO */
    .hero {
      height: 100vh; display: flex; flex-direction: column; justify-content: center;
      align-items: center; padding-top: 80px; text-align: center;
    }
    .glass-panel {
      backdrop-filter: blur(30px);
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(0, 255, 179, 0.25);
      padding: 3rem;
      border-radius: 20px;
      max-width: 800px;
      box-shadow: 0 0 20px rgba(0, 255, 179, 0.2);
      animation: fadeIn 1.2s ease;
    }
    .hero h2 {font-size: 3rem; margin-bottom: 1rem; color: #00ffb3;}
    .hero p {font-size: 1.2rem; margin-bottom: 2rem; opacity: 0.8;}
    .cta {
      background: #00ffb3; color: #000;
      padding: 0.9rem 2rem; border: none; border-radius: 25px;
      cursor: pointer; font-weight: bold; font-size: 1rem;
      transition: transform 0.3s;
    }
    .cta:hover {transform: scale(1.05);}

    /* PRODUCT ANIMATION */
    .product-animation {
      margin-top: 3rem; display: flex; justify-content: center; align-items: center; position: relative;
    }
    .exhaust {
      width: 150px; height: 150px; border-radius: 50%;
      background: linear-gradient(145deg, #1c1f25, #0a0d10);
      border: 4px solid #00ffb3;
      box-shadow: 0 0 30px rgba(0, 255, 179, 0.3);
      display: flex; justify-content: center; align-items: center; position: relative;
    }
    .exhaust::before {
      content: "";
      position: absolute;
      width: 120%;
      height: 4px;
      background: linear-gradient(to right, red, blue);
      animation: flow 3s linear infinite;
    }
    @keyframes flow {
      0% { transform: translateX(-150px); opacity: 0; }
      50% { opacity: 1; }
      100% { transform: translateX(150px); opacity: 0; }
    }

    /* MODAL OVERLAY */
    .overlay {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(5, 8, 12, 0.9);
      backdrop-filter: blur(20px);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 2000;
      animation: fadeIn 0.5s ease forwards;
    }
    .overlay.active {display: flex;}
    .modal {
      max-width: 1000px;
      padding: 2rem;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(0, 255, 179, 0.25);
      border-radius: 20px;
      box-shadow: 0 0 20px rgba(0, 255, 179, 0.2);
      text-align: center;
      position: relative;
      animation: slideUp 0.6s ease;
    }
    .close-btn {
      position: absolute;
      top: 20px;
      right: 20px;
      font-size: 1.5rem;
      background: transparent;
      border: none;
      color: #00ffb3;
      cursor: pointer;
    }
    .modal h2 {color: #00ffb3; font-size: 2.5rem; margin-bottom: 1rem;}
    .modal p {opacity: 0.85; margin-bottom: 2rem;}
    .component-diagram {
      display: flex; justify-content: center; flex-wrap: wrap; gap: 2rem; margin-top: 2rem;
    }
    .component {
      backdrop-filter: blur(15px);
      background: rgba(255, 255, 255, 0.05);
      padding: 1rem 1.5rem;
      border-radius: 15px;
      border: 1px solid rgba(0, 255, 179, 0.25);
      width: 200px;
      text-align: center;
      transition: transform 0.3s;
    }
    .component:hover {transform: translateY(-5px);}
    .component h4 {color: #00ffb3; margin-bottom: 0.5rem;}
    .overlay img {
      width: 300px;
      margin: 0 auto;
      display: block;
      filter: drop-shadow(0 0 15px #00ffb3);
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(40px);}
      to {opacity: 1; transform: translateY(0);}
    }
    @keyframes slideUp {
      from {transform: translateY(50px); opacity: 0;}
      to {transform: translateY(0); opacity: 1;}
    }

    footer {text-align: center; padding: 2rem; color: rgba(255, 255, 255, 0.5);}
  </style>
</head>
<body>
  <header>
    <h1>VEHICLE XtraPure</h1>
    <nav>
      <a href="#product">Product</a>
      <a href="#tech">Technology</a>
      <a href="#impact">Impact</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section class="hero" id="product">
    <div class="glass-panel">
      <h2>ExhauPure</h2>
      <p>Innovating Clean Air for Urban Futures. An eco-friendly exhaust filter using <strong>non-combustible sustainable materials</strong> to reduce harmful car emissions.</p>
      <button class="cta" id="learnMoreBtn">Learn More</button>
      <div class="product-animation">
        <div class="exhaust"></div>
      </div>
    </div>
  </section>

  <div class="overlay" id="modalOverlay">
    <div class="modal">
      <button class="close-btn" id="closeBtn">✕</button>
      <h2>ExhauPure Technology</h2>
      <p>Our eco-friendly exhaust filter uses multi-layer filtration to trap over 90% of harmful vehicle emissions.</p>
      <img src="https://i.ibb.co/rKTnFHvS/ce4b4d2c-f62a-4fd3-902c-3f11fe19a987.jpg" alt="Exhaust Filter"/>
      <div class="component-diagram">
        <div class="component">
          <h4>Non-Combustible Coating</h4>
          <p>Heat-resistant ceramic coating prevents ignition.</p>
        </div>
        <div class="component">
          <h4>Activated Carbon Layer</h4>
          <p>Absorbs CO, NOx, and other toxic gases.</p>
        </div>
        <div class="component">
          <h4>Fiber Particulate Trap</h4>
          <p>Natural fiber mesh traps fine particles.</p>
        </div>
        <div class="component">
          <h4>Outer Heat Shield</h4>
          <p>Durable, protects the filter and enhances safety.</p>
        </div>
      </div>
    </div>
  </div>

  <footer>
    © 2025 ExhauPure — Clean Cities. Clear Skies. All Rights Reserved.
  </footer>

  <script>
    const learnMoreBtn = document.getElementById('learnMoreBtn');
    const modalOverlay = document.getElementById('modalOverlay');
    const closeBtn = document.getElementById('closeBtn');

    learnMoreBtn.addEventListener('click', () => {
      modalOverlay.classList.add('active');
    });
    closeBtn.addEventListener('click', () => {
      modalOverlay.classList.remove('active');
    });
  </script>
</body>
</html>
