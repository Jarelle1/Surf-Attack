<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Merch Shop</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f6f6f6; }
    header { background: #111; color: #fff; padding: 1rem; text-align: center; position: relative; }
    h1 { margin: 0; font-size: 2rem; }
    .lang-switch { position: absolute; right: 1rem; top: 1rem; }
    .lang-switch button { margin-left: 0.5rem; padding: 0.25rem 0.5rem; }
    .products { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 1rem; padding: 1rem; }
    .product { background: #fff; padding: 1rem; border-radius: 8px; box-shadow: 0 0 10px rgba(0,0,0,0.1); text-align: center; }
    .product img { max-width: 100%; border-radius: 8px; }
    .product h2 { margin: 0.5rem 0; }
    .product p { color: #555; }
    .btn { background: #111; color: #fff; padding: 0.5rem 1rem; border: none; cursor: pointer; border-radius: 4px; }
    .btn:hover { background: #444; }
    footer { text-align: center; padding: 1rem; font-size: 0.9rem; color: #999; }
  </style>
</head>
<body>
  <header>
    <div class="lang-switch">
      <button onclick="setLanguage('de')">Deutsch</button>
      <button onclick="setLanguage('en')">English</button>
    </div>
    <h1 id="title">Unser Merch-Shop</h1>
    <p id="subtitle">Coole Kleidung & Accessoires von uns – supporte uns!</p>
  </header>

  <section class="products">
    <div class="product">
      <img src="https://via.placeholder.com/300x300?text=T-Shirt" alt="T-Shirt">
      <h2 id="prod1-title">Classic T-Shirt</h2>
      <p id="prod1-desc">Schlichtes Shirt mit Logo<br>Preis: 25€</p>
      <button class="btn" onclick="order('Classic T-Shirt')" id="prod1-btn">Anfragen</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/300x300?text=Hoodie" alt="Hoodie">
      <h2 id="prod2-title">Cozy Hoodie</h2>
      <p id="prod2-desc">Warmer Hoodie für kühle Tage<br>Preis: 45€</p>
      <button class="btn" onclick="order('Cozy Hoodie')" id="prod2-btn">Anfragen</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/300x300?text=Cap" alt="Cap">
      <h2 id="prod3-title">Stylische Cap</h2>
      <p id="prod3-desc">Mit gesticktem Logo<br>Preis: 20€</p>
      <button class="btn" onclick="order('Stylische Cap')" id="prod3-btn">Anfragen</button>
    </div>
  </section>

  <footer>
    © 2025 Unser Merch-Shop – Alle Rechte vorbehalten
  </footer>

  <script>
    const translations = {
      de: {
        title: "Unser Merch-Shop",
        subtitle: "Coole Kleidung & Accessoires von uns – supporte uns!",
        prod1: { title: "Classic T-Shirt", desc: "Schlichtes Shirt mit Logo<br>Preis: 25€", btn: "Anfragen" },
        prod2: { title: "Cozy Hoodie", desc: "Warmer Hoodie für kühle Tage<br>Preis: 45€", btn: "Anfragen" },
        prod3: { title: "Stylische Cap", desc: "Mit gesticktem Logo<br>Preis: 20€", btn: "Anfragen" }
      },
      en: {
        title: "Our Merch Shop",
        subtitle: "Cool clothing & accessories – support us!",
        prod1: { title: "Classic T-Shirt", desc: "Simple shirt with logo<br>Price: €25", btn: "Inquire" },
        prod2: { title: "Cozy Hoodie", desc: "Warm hoodie for chilly days<br>Price: €45", btn: "Inquire" },
        prod3: { title: "Stylish Cap", desc: "Embroidered logo<br>Price: €20", btn: "Inquire" }
      }
    };

    function setLanguage(lang) {
      document.getElementById('title').innerHTML = translations[lang].title;
      document.getElementById('subtitle').innerHTML = translations[lang].subtitle;
      document.getElementById('prod1-title').innerHTML = translations[lang].prod1.title;
      document.getElementById('prod1-desc').innerHTML = translations[lang].prod1.desc;
      document.getElementById('prod1-btn').innerHTML = translations[lang].prod1.btn;
      document.getElementById('prod2-title').innerHTML = translations[lang].prod2.title;
      document.getElementById('prod2-desc').innerHTML = translations[lang].prod2.desc;
      document.getElementById('prod2-btn').innerHTML = translations[lang].prod2.btn;
      document.getElementById('prod3-title').innerHTML = translations[lang].prod3.title;
      document.getElementById('prod3-desc').innerHTML = translations[lang].prod3.desc;
      document.getElementById('prod3-btn').innerHTML = translations[lang].prod3.btn;
    }

    function order(productName) {
      const email = "mailto:deine@email.de?subject=Bestellanfrage: " + encodeURIComponent(productName);
      window.location.href = email;
    }
  </script>
</body>
</html>
