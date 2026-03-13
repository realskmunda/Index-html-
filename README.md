# Index-html-
This is grocery store 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>RozeMart - Quick Delivery</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Poppins:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --white: #ffffff;
    --gray-100: #f5f5f5;
    --gray-200: #e8e8e8;
    --gray-400: #9a9a9a;
    --accent: #1a1a1a;
    --green: #22c55e;
    --red: #ef4444;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

  body {
    font-family: 'Poppins', sans-serif;
    background: var(--white);
    color: var(--black);
    max-width: 430px;
    margin: 0 auto;
    min-height: 100vh;
    overflow-x: hidden;
    position: relative;
  }

  /* SCREENS */
  .screen { display: none; min-height: 100vh; flex-direction: column; animation: fadeIn 0.3s ease; }
  .screen.active { display: flex; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== SPLASH SCREEN ===== */
  #splash {
    background: var(--white);
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 16px;
  }
  .splash-logo { animation: popIn 0.6s cubic-bezier(0.34,1.56,0.64,1); }
  @keyframes popIn { from { transform: scale(0.5); opacity: 0; } to { transform: scale(1); opacity: 1; } }
  .splash-logo svg { width: 100px; height: 100px; }
  .splash-name {
    font-family: 'Nunito', sans-serif;
    font-size: 32px;
    font-weight: 900;
    color: var(--black);
    letter-spacing: -1px;
  }
  .splash-tagline {
    font-size: 13px;
    color: var(--gray-400);
    font-weight: 500;
  }
  .delivery-badge {
    display: flex;
    align-items: center;
    gap: 8px;
    background: var(--black);
    color: white;
    padding: 10px 20px;
    border-radius: 50px;
    font-size: 13px;
    font-weight: 700;
    margin-top: 8px;
    animation: pulse 2s infinite;
  }
  @keyframes pulse { 0%,100% { box-shadow: 0 0 0 0 rgba(0,0,0,0.3); } 50% { box-shadow: 0 0 0 10px rgba(0,0,0,0); } }
  .delivery-badge .dot { width: 8px; height: 8px; background: var(--green); border-radius: 50%; animation: blink 1s infinite; }
  @keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0.3; } }

  /* ===== TOP NAV ===== */
  .top-nav {
    position: sticky;
    top: 0;
    z-index: 100;
    background: var(--black);
    padding: 12px 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .search-bar {
    flex: 1;
    display: flex;
    align-items: center;
    background: white;
    border-radius: 50px;
    padding: 10px 16px;
    gap: 8px;
    cursor: pointer;
  }
  .search-bar span { font-size: 13px; color: var(--gray-400); font-weight: 500; }
  .nav-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: white;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    flex-shrink: 0;
  }

  /* ===== DELIVERY BAR ===== */
  .delivery-bar {
    background: var(--gray-100);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid var(--gray-200);
  }
  .delivery-info { display: flex; align-items: center; gap: 6px; }
  .delivery-time {
    background: var(--black);
    color: white;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 700;
    font-family: 'Nunito', sans-serif;
  }
  .delivery-addr { font-size: 12px; color: var(--gray-400); font-weight: 500; max-width: 180px; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }

  /* ===== HOME CONTENT ===== */
  .home-content { flex: 1; overflow-y: auto; padding-bottom: 80px; }

  /* Hero Banner */
  .hero-banner {
    margin: 16px;
    background: var(--black);
    border-radius: 20px;
    padding: 24px 20px;
    color: white;
    position: relative;
    overflow: hidden;
  }
  .hero-banner::before {
    content: '';
    position: absolute;
    right: -20px;
    top: -20px;
    width: 120px;
    height: 120px;
    background: rgba(255,255,255,0.05);
    border-radius: 50%;
  }
  .hero-banner::after {
    content: '';
    position: absolute;
    right: 20px;
    bottom: -30px;
    width: 80px;
    height: 80px;
    background: rgba(255,255,255,0.03);
    border-radius: 50%;
  }
  .hero-tag { font-size: 11px; font-weight: 700; background: var(--green); color: white; padding: 3px 10px; border-radius: 20px; display: inline-block; margin-bottom: 8px; }
  .hero-title { font-family: 'Nunito', sans-serif; font-size: 22px; font-weight: 900; line-height: 1.2; margin-bottom: 4px; }
  .hero-sub { font-size: 12px; opacity: 0.6; }
  .hero-timer { display: flex; align-items: center; gap: 6px; margin-top: 12px; }
  .timer-box { background: white; color: var(--black); border-radius: 8px; padding: 4px 10px; font-weight: 800; font-size: 16px; font-family: 'Nunito', sans-serif; }
  .timer-label { font-size: 11px; opacity: 0.6; }

  /* Categories */
  .section-title { font-size: 15px; font-weight: 700; padding: 0 16px; margin: 16px 0 10px; font-family: 'Nunito', sans-serif; }
  .categories { display: flex; gap: 10px; padding: 0 16px; overflow-x: auto; scrollbar-width: none; -ms-overflow-style: none; }
  .categories::-webkit-scrollbar { display: none; }
  .cat-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
    cursor: pointer;
    flex-shrink: 0;
    min-width: 64px;
  }
  .cat-icon {
    width: 60px;
    height: 60px;
    background: var(--gray-100);
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 26px;
    transition: all 0.2s;
    border: 2px solid transparent;
  }
  .cat-item.active .cat-icon, .cat-icon:hover { background: var(--black); border-color: var(--black); transform: scale(1.05); }
  .cat-item.active .cat-icon { filter: invert(1); }
  .cat-name { font-size: 11px; font-weight: 600; text-align: center; color: var(--gray-400); }
  .cat-item.active .cat-name { color: var(--black); }

  /* Products Grid */
  .products-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    padding: 0 16px;
    margin-top: 12px;
  }
  .product-card {
    background: var(--white);
    border: 1.5px solid var(--gray-200);
    border-radius: 16px;
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .product-card:hover { transform: translateY(-2px); box-shadow: 0 8px 20px rgba(0,0,0,0.08); }
  .product-img {
    height: 120px;
    background: var(--gray-100);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 50px;
    position: relative;
  }
  .product-badge {
    position: absolute;
    top: 8px;
    left: 8px;
    background: var(--black);
    color: white;
    font-size: 9px;
    font-weight: 700;
    padding: 2px 7px;
    border-radius: 20px;
  }
  .product-info { padding: 10px; }
  .product-name { font-size: 13px; font-weight: 600; line-height: 1.3; margin-bottom: 2px; }
  .product-qty { font-size: 11px; color: var(--gray-400); margin-bottom: 8px; }
  .product-footer { display: flex; align-items: center; justify-content: space-between; }
  .product-price { font-family: 'Nunito', sans-serif; font-size: 15px; font-weight: 800; }
  .add-btn {
    width: 28px;
    height: 28px;
    background: var(--black);
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 18px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: transform 0.15s;
    font-family: 'Nunito', sans-serif;
    font-weight: 700;
    line-height: 1;
  }
  .add-btn:active { transform: scale(0.9); }
  .qty-ctrl { display: flex; align-items: center; gap: 6px; }
  .qty-ctrl button {
    width: 24px; height: 24px;
    background: var(--gray-200);
    border: none;
    border-radius: 6px;
    font-size: 14px;
    cursor: pointer;
    font-weight: 700;
    display: flex; align-items: center; justify-content: center;
  }
  .qty-ctrl .qty-num { font-size: 13px; font-weight: 700; min-width: 16px; text-align: center; }

  /* ===== BOTTOM NAV ===== */
  .bottom-nav {
    position: fixed;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 100%;
    max-width: 430px;
    background: white;
    border-top: 1.5px solid var(--gray-200);
    display: flex;
    padding: 8px 0 16px;
    z-index: 100;
  }
  .nav-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
    cursor: pointer;
    padding: 6px;
    position: relative;
  }
  .nav-item svg { transition: transform 0.2s; }
  .nav-item.active svg path, .nav-item.active svg rect, .nav-item.active svg circle { fill: var(--black); }
  .nav-item span { font-size: 10px; font-weight: 600; color: var(--gray-400); }
  .nav-item.active span { color: var(--black); }
  .cart-badge {
    position: absolute;
    top: 2px;
    right: 20px;
    background: var(--red);
    color: white;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    font-size: 9px;
    font-weight: 700;
    display: none;
    align-items: center;
    justify-content: center;
  }
  .cart-badge.show { display: flex; }

  /* ===== CART SCREEN ===== */
  .cart-header { background: var(--black); color: white; padding: 20px 16px; }
  .cart-header h2 { font-family: 'Nunito', sans-serif; font-size: 22px; font-weight: 900; }
  .cart-delivery-note {
    display: flex;
    align-items: center;
    gap: 6px;
    background: rgba(255,255,255,0.1);
    padding: 8px 12px;
    border-radius: 10px;
    margin-top: 10px;
    font-size: 12px;
  }
  .cart-items { flex: 1; overflow-y: auto; padding: 16px; padding-bottom: 20px; }
  .cart-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 12px 0;
    border-bottom: 1px solid var(--gray-200);
  }
  .cart-item-emoji { font-size: 32px; width: 50px; height: 50px; background: var(--gray-100); border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .cart-item-info { flex: 1; }
  .cart-item-name { font-size: 13px; font-weight: 600; }
  .cart-item-price { font-size: 13px; font-weight: 700; font-family: 'Nunito', sans-serif; color: var(--black); margin-top: 2px; }
  .cart-qty-ctrl { display: flex; align-items: center; gap: 8px; }
  .cq-btn {
    width: 28px; height: 28px;
    background: var(--black);
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    font-weight: 700;
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
  }
  .cq-btn.minus { background: var(--gray-200); color: var(--black); }
  .empty-cart { display: flex; flex-direction: column; align-items: center; justify-content: center; flex: 1; gap: 12px; color: var(--gray-400); padding: 40px; text-align: center; }
  .empty-cart .big-icon { font-size: 60px; }

  /* Cart Summary */
  .cart-summary { padding: 16px; border-top: 1px solid var(--gray-200); background: white; }
  .summary-row { display: flex; justify-content: space-between; font-size: 13px; margin-bottom: 8px; }
  .summary-row.total { font-size: 16px; font-weight: 800; font-family: 'Nunito', sans-serif; border-top: 1.5px dashed var(--gray-200); padding-top: 10px; margin-top: 6px; }
  .checkout-btn {
    width: 100%;
    background: var(--black);
    color: white;
    border: none;
    padding: 16px;
    border-radius: 14px;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    margin-top: 12px;
    font-family: 'Nunito', sans-serif;
    transition: transform 0.15s;
  }
  .checkout-btn:active { transform: scale(0.98); }

  /* ===== CHECKOUT SCREEN ===== */
  .checkout-header { background: var(--black); color: white; padding: 16px; display: flex; align-items: center; gap: 12px; }
  .back-btn { background: none; border: none; color: white; cursor: pointer; padding: 4px; }
  .checkout-header h2 { font-family: 'Nunito', sans-serif; font-size: 20px; font-weight: 900; }
  .checkout-body { flex: 1; overflow-y: auto; padding: 16px; padding-bottom: 100px; }

  .form-section { background: var(--gray-100); border-radius: 16px; padding: 16px; margin-bottom: 16px; }
  .form-section-title { font-size: 13px; font-weight: 700; margin-bottom: 12px; display: flex; align-items: center; gap: 6px; }
  .form-group { margin-bottom: 12px; }
  .form-group label { font-size: 11px; font-weight: 600; color: var(--gray-400); margin-bottom: 4px; display: block; text-transform: uppercase; letter-spacing: 0.5px; }
  .form-group input, .form-group select, .form-group textarea {
    width: 100%;
    padding: 12px 14px;
    border: 1.5px solid var(--gray-200);
    border-radius: 10px;
    font-size: 14px;
    font-family: 'Poppins', sans-serif;
    background: white;
    outline: none;
    transition: border-color 0.2s;
  }
  .form-group input:focus, .form-group textarea:focus { border-color: var(--black); }
  .form-group textarea { resize: none; height: 70px; }

  /* Payment Options */
  .payment-options { display: flex; flex-direction: column; gap: 10px; }
  .payment-option {
    display: flex;
    align-items: center;
    gap: 12px;
    background: white;
    padding: 14px;
    border-radius: 12px;
    border: 2px solid var(--gray-200);
    cursor: pointer;
    transition: all 0.2s;
  }
  .payment-option.selected { border-color: var(--black); background: var(--black); color: white; }
  .payment-option .pay-icon { font-size: 24px; width: 40px; height: 40px; background: var(--gray-100); border-radius: 10px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .payment-option.selected .pay-icon { background: rgba(255,255,255,0.15); }
  .payment-option .pay-label { font-size: 14px; font-weight: 600; }
  .payment-option .pay-sub { font-size: 11px; color: var(--gray-400); margin-top: 1px; }
  .payment-option.selected .pay-sub { color: rgba(255,255,255,0.6); }
  .payment-option .radio { width: 18px; height: 18px; border-radius: 50%; border: 2px solid var(--gray-200); margin-left: auto; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .payment-option.selected .radio { border-color: white; background: white; }
  .radio-dot { width: 8px; height: 8px; background: var(--black); border-radius: 50%; display: none; }
  .payment-option.selected .radio-dot { display: block; }

  /* UPI Input */
  .upi-input { margin-top: 10px; display: none; }
  .upi-input.show { display: block; }

  /* Order Btn fixed */
  .place-order-wrap { position: fixed; bottom: 0; left: 50%; transform: translateX(-50%); width: 100%; max-width: 430px; padding: 16px; background: white; border-top: 1px solid var(--gray-200); }
  .place-order-btn {
    width: 100%;
    background: var(--black);
    color: white;
    border: none;
    padding: 16px;
    border-radius: 14px;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    font-family: 'Nunito', sans-serif;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    transition: transform 0.15s;
  }
  .place-order-btn:active { transform: scale(0.98); }
  .order-total-label { font-size: 13px; opacity: 0.7; }

  /* ===== SUCCESS SCREEN ===== */
  #success {
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 16px;
    padding: 40px 24px;
    text-align: center;
  }
  .success-icon { font-size: 80px; animation: bounceIn 0.6s cubic-bezier(0.34,1.56,0.64,1); }
  @keyframes bounceIn { from { transform: scale(0); opacity: 0; } to { transform: scale(1); opacity: 1; } }
  .success-title { font-family: 'Nunito', sans-serif; font-size: 26px; font-weight: 900; }
  .success-sub { font-size: 14px; color: var(--gray-400); line-height: 1.5; }
  .success-timer-box {
    background: var(--black);
    color: white;
    padding: 20px 40px;
    border-radius: 20px;
    margin: 10px 0;
  }
  .success-timer-box .big-time { font-family: 'Nunito', sans-serif; font-size: 48px; font-weight: 900; line-height: 1; }
  .success-timer-box .time-label { font-size: 13px; opacity: 0.6; margin-top: 4px; }
  .order-id-box { background: var(--gray-100); padding: 12px 20px; border-radius: 12px; font-size: 13px; color: var(--gray-400); }
  .order-id-box span { font-weight: 700; color: var(--black); font-family: 'Nunito', sans-serif; }
  .continue-btn {
    background: var(--black);
    color: white;
    border: none;
    padding: 14px 40px;
    border-radius: 50px;
    font-size: 15px;
    font-weight: 700;
    cursor: pointer;
    font-family: 'Nunito', sans-serif;
    margin-top: 10px;
  }

  /* Toast */
  .toast {
    position: fixed;
    bottom: 90px;
    left: 50%;
    transform: translateX(-50%) translateY(100px);
    background: var(--black);
    color: white;
    padding: 12px 20px;
    border-radius: 50px;
    font-size: 13px;
    font-weight: 600;
    z-index: 999;
    transition: transform 0.3s cubic-bezier(0.34,1.56,0.64,1);
    white-space: nowrap;
    max-width: calc(100% - 40px);
    text-align: center;
  }
  .toast.show { transform: translateX(-50%) translateY(0); }

  /* Categories screen */
  .categories-full { flex: 1; overflow-y: auto; padding: 16px; padding-bottom: 80px; }
  .cat-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 12px; }
  .cat-full-item {
    aspect-ratio: 1;
    background: var(--gray-100);
    border-radius: 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 6px;
    cursor: pointer;
    transition: all 0.2s;
    border: 2px solid transparent;
  }
  .cat-full-item:hover { border-color: var(--black); background: var(--black); }
  .cat-full-item:hover span:first-child { filter: none; }
  .cat-full-item:hover .cat-full-name { color: white; }
  .cat-full-item .big-emoji { font-size: 36px; }
  .cat-full-name { font-size: 12px; font-weight: 600; color: var(--gray-400); text-align: center; }

  /* Profile screen */
  .profile-content { flex: 1; overflow-y: auto; padding: 0; padding-bottom: 80px; }
  .profile-header { background: var(--black); color: white; padding: 30px 20px 24px; text-align: center; }
  .avatar-big { width: 70px; height: 70px; background: rgba(255,255,255,0.15); border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 12px; font-size: 32px; }
  .profile-name { font-family: 'Nunito', sans-serif; font-size: 20px; font-weight: 900; }
  .profile-phone { font-size: 13px; opacity: 0.6; margin-top: 2px; }
  .profile-menu { padding: 16px; }
  .menu-item {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 16px;
    background: var(--gray-100);
    border-radius: 14px;
    margin-bottom: 10px;
    cursor: pointer;
    transition: background 0.2s;
  }
  .menu-item:hover { background: var(--gray-200); }
  .menu-icon { font-size: 20px; width: 36px; text-align: center; }
  .menu-label { font-size: 14px; font-weight: 600; }
  .menu-arrow { margin-left: auto; color: var(--gray-400); font-size: 18px; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 0; }
</style>
</head>
<body>

<!-- Toast -->
<div class="toast" id="toast"></div>

<!-- ===== SPLASH ===== -->
<div id="splash" class="screen active">
  <div class="splash-logo">
    <svg viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
      <rect x="18" y="35" width="64" height="55" rx="12" fill="#0a0a0a"/>
      <path d="M35 35 Q35 20 50 20 Q65 20 65 35" stroke="#0a0a0a" stroke-width="7" stroke-linecap="round" fill="none"/>
      <path d="M38 58 Q50 68 62 58" stroke="white" stroke-width="5" stroke-linecap="round" fill="none"/>
    </svg>
  </div>
  <div class="splash-name">RozeMart</div>
  <div class="splash-tagline">Groceries & More, At Your Door</div>
  <div class="delivery-badge
