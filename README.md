<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Tienda MADMAXX</title>
  <meta name="description" content="Tienda MADMAXX - Rangos para tu servidor Minecraft" />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --yellow:#FFD54A;
      --orange:#FF8A00;
      --bg:#0b0b0b;
      --card:#111111;
      --muted:rgba(255,255,255,0.75);
      --glass: rgba(255,255,255,0.04);
    }
    *{box-sizing:border-box}
    body{
      font-family:Inter,system-ui,Segoe UI,Roboto,"Helvetica Neue",Arial;
      margin:0;
      background: url('https://static.wikia.nocookie.net/minecraft_gamepedia/images/d/d6/Overworld_Biome.png') center/cover no-repeat;
      background-attachment: fixed;
      color:#fff;
    }
    header{background:linear-gradient(90deg,var(--yellow),var(--orange)); padding:22px 28px; display:flex; align-items:center; justify-content:space-between; gap:16px;}
    .brand{display:flex; align-items:center; gap:12px}
    .logo{width:56px; height:56px; background:linear-gradient(135deg,var(--orange),var(--yellow)); border-radius:10px; display:flex; align-items:center; justify-content:center; box-shadow:0 6px 18px rgba(0,0,0,0.35);}
    .logo svg{width:34px; height:34px}
    h1{font-family:'Press Start 2P', monospace; font-size:18px; margin:0; color:#1b1b1b; letter-spacing:1px}

    .highlight-text {
      font-size: 28px;
      background: linear-gradient(90deg, #FFD700, #FF8A00, #FF4500);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 12px;
      transition: all 0.3s ease;
    }

    .highlight-text.active {
      background: linear-gradient(90deg, #00FFFF, #FF00FF, #FFFF00);
      text-shadow: 0 0 8px #fff, 0 0 12px #FF00FF, 0 0 16px #00FFFF;
    }

    .container{max-width:800px;margin:28px auto;padding:0 18px}
    .hero{background:linear-gradient(180deg, rgba(0,0,0,0.6), rgba(0,0,0,0.6)); padding:28px; border-radius:14px; box-shadow:0 6px 22px rgba(0,0,0,0.5); text-align:center; transition: background 0.3s;}
    .hero.dimmed{background:rgba(0,0,0,0.2);}
    .hero p{margin:0 0 18px; color:var(--muted)}

    .ranks{display:flex; gap:12px; margin-top:16px; justify-content:center; flex-wrap:wrap; transition: opacity 0.3s;}
    .rank{flex:1; background:var(--card); padding:16px; border-radius:12px; text-align:center; max-width:220px; cursor:pointer; transition: transform 0.2s, opacity 0.3s;}
    .rank.selected{border:2px solid var(--yellow); transform: scale(1.05);}
    .rank img{width:100%; border-radius:10px; margin-bottom:10px}
    .rank h3{margin:0 0 6px}
    .rank p{color:var(--muted); margin-bottom:6px}
    .price{font-weight:700; color:var(--yellow); margin-bottom:10px}

    form{margin-top:20px; display:flex; flex-direction:column; gap:12px; background:var(--card); padding:16px; border-radius:12px;}
    input, select, button{padding:10px; border-radius:8px; border:none; font-size:14px}
    input{background:var(--glass); color:#fff;}
    select{background:var(--glass); color:#fff;}
    button{background:linear-gradient(90deg,var(--orange),var(--yellow)); color:#111; font-weight:700; cursor:pointer;}

    .payment-details{display:none; flex-direction:column; gap:10px; margin-top:10px;}
    .amount{margin-top:10px; font-weight:700; color:var(--yellow)}

    footer{margin-top:38px;padding:28px;text-align:center;color:var(--muted)}
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="logo" aria-hidden="true">
        <svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="logo">
          <rect x="4" y="4" width="56" height="56" rx="6" fill="#2e8b2e"/>
          <rect x="6" y="42" width="52" height="14" rx="3" fill="#7b461a"/>
          <rect x="6" y="36" width="52" height="8" rx="2" fill="#3b6f12"/>
        </svg>
      </div>
      <div>
        <h1>Tienda MADMAXX</h1>
        <div style="font-size:12px;color:#0b0b0b;opacity:0.85">Rangos para tu servidor Minecraft</div>
      </div>
    </div>
  </header>

  <main class="container">
    <section class="hero" id="hero">
      <h2 class="highlight-text" id="highlightText">Rangos Exclusivos MADMAXX</h2>
      <p>Selecciona un rango, ingresa tu nombre de Minecraft y selecciona tu método de pago.</p>
      <div class="ranks" id="ranks">
        <div class="rank" data-rank="Explorador" data-price="$10 USD">
          <img src="https://static.wikia.nocookie.net/minecraft_gamepedia/images/0/0b/Grass_Block_JE2_BE2.png" alt="Explorador">
          <h3>Explorador</h3>
          <p>Acceso a mapas especiales y items básicos.</p>
          <div class="price">$10 USD</div>
        </div>
        <div class="rank" data-rank="Forjador" data-price="$13 USD">
          <img src="https://static.wikia.nocookie.net/minecraft_gamepedia/images/4/42/Iron_Block_JE2_BE2.png" alt="Forjador">
          <h3>Forjador</h3>
          <p>Generadores mejorados y recompensas en eventos.</p>
          <div class="price">$13 USD</div>
        </div>
        <div class="rank" data-rank="Conquistador" data-price="$20 USD">
          <img src="https://static.wikia.nocookie.net/minecraft_gamepedia/images/1/16/Diamond_Block_JE2_BE2.png" alt="Conquistador">
          <h3>Conquistador</h3>
          <p>Beneficios premium, acceso a zonas VIP y títulos exclusivos.</p>
          <div class="price">$20 USD</div>
        </div>
      </div>

      <form id="purchaseForm" onsubmit="event.preventDefault(); alert('Pago simulado: Gracias por tu compra!');">
        <input type="text" placeholder="Tu nombre de Minecraft" required>
        <select id="paymentMethod" required>
          <option value="paypal">PayPal</option>
          <option value="tarjeta">Tarjeta de Crédito</option>
        </select>

        <div class="payment-details" id="paypalDetails">
          <input type="email" placeholder="Correo de PayPal" required>
        </div>

        <div class="payment-details" id="cardDetails">
          <input type="text" placeholder="Número de tarjeta de crédito" required>
          <input type="text" placeholder="Nombre en la tarjeta" required>
          <input type="text" placeholder="Fecha de expiración MM/AA" required>
          <input type="text" placeholder="CVC" required>
        </div>

        <div class="amount" id="amountDisplay">Monto a pagar: </div>

        <button type="submit">Comprar Rango</button>
      </form>
    </section>

    <footer>
      © <span id="year"></span> Tienda MADMAXX — Servidor Minecraft
    </footer>
  </main>

  <script>
    document.getElementById('year').textContent = new Date().getFullYear();

    const paymentMethod = document.getElementById('paymentMethod');
    const paypalDetails = document.getElementById('paypalDetails');
    const cardDetails = document.getElementById('cardDetails');
    const ranks = document.querySelectorAll('.rank');
    const hero = document.getElementById('hero');
    const amountDisplay = document.getElementById('amountDisplay');
    const highlightText = document.getElementById('highlightText');

    paymentMethod.addEventListener('change', () => {
      if(paymentMethod.value === 'paypal'){
        paypalDetails.style.display = 'flex';
        cardDetails.style.display = 'none';
      } else {
        paypalDetails.style.display = 'none';
        cardDetails.style.display = 'flex';
      }
    });

    paypalDetails.style.display = 'flex';
    cardDetails.style.display = 'none';

    ranks.forEach(rank => {
      rank.addEventListener('click', () => {
        ranks.forEach(r => r.classList.remove('selected'));
        rank.classList.add('selected');
        hero.classList.add('dimmed');
        amountDisplay.textContent = 'Monto a pagar: ' + rank.dataset.price;

        // Cambio de color del título al seleccionar un rango
        highlightText.classList.add('active');
      });
    });
  </script>
</body>
</html>
