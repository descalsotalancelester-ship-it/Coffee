9<Index.html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Deja Brew Cafe</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
:root{--primary:#6f4e37;--secondary:#c49a6c;--dark:#1a100a;}
body{margin:0;font-family:'Segoe UI',sans-serif;background:var(--dark);color:#fff}

/* HEADER */
header{background:var(--primary);padding:18px;text-align:center;font-size:22px;font-weight:bold}

/* TABS */
.tab-container{display:flex;gap:8px;padding:10px;background:#2b1d14;position:sticky;top:0}
.tab-btn{flex:1;padding:10px;border:none;border-radius:10px;background:#3b2a1e;color:#fff;font-weight:bold;cursor:pointer}
.tab-btn.active{background:var(--secondary);color:#000}

/* CONTAINER */
.container{max-width:500px;margin:auto;padding:15px}
.category{display:none}
.category.active{display:block}

/* MENU ITEMS */
.menu-item{background:#fff;color:#333;border-radius:16px;padding:12px;margin-bottom:12px;display:flex;gap:12px;align-items:center}
.menu-item img{width:80px;height:80px;border-radius:12px;object-fit:cover}
.item-info{flex:1}
.item-header{display:flex;justify-content:space-between;font-weight:bold}
.controls{display:flex;gap:8px;align-items:center;margin-top:8px}
.controls button{width:30px;height:30px;border:none;border-radius:50%;background:var(--primary);color:#fff;font-size:18px;cursor:pointer}

/* PAYMENT */
.payment-box{background:#ffffff15;padding:15px;border-radius:15px;margin-top:15px}
input,select{width:100%;padding:12px;border-radius:10px;border:none;margin-top:8px}
.main-btn{width:100%;padding:16px;margin-top:12px;border:none;border-radius:15px;background:var(--secondary);font-weight:bold}

/* RECEIPT */
.receipt{background:#fff;color:#000;padding:20px;margin-top:20px;display:none;font-family:monospace}
@media print{body *{visibility:hidden}.receipt,.receipt *{visibility:visible}.receipt{position:absolute;inset:0}}
</style>
</head>
<body>

<header>☕ Deja Brew Cafe</header>

<div class="tab-container">
  <button class="tab-btn active" onclick="showCat('coffee',this)">COFFEE</button>
  <button class="tab-btn" onclick="showCat('meals',this)">MEALS</button>
  <button class="tab-btn" onclick="showCat('pastries',this)">PASTRIES</button>
</div>

<div class="container">

<!-- COFFEE -->
<div id="coffee" class="category active">
  <div class="menu-item" data-id="latte" data-price="130">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTn3rc73mfllqY7TURp9nOWyl027HAOwp7aVA&s" alt="Spanish Latte">
    <div class="item-info">
      <div class="item-header">Spanish Latte ₱130</div>
      <div class="controls"><button onclick="changeQty('latte',-1)">-</button><span id="q-latte">0</span><button onclick="changeQty('latte',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="capp" data-price="120">
    <img src="https://coffee-slang.com/wp-content/uploads/2024/05/how-to-make-a-cappuccino-1200x900.jpg" alt="Cappuccino">
    <div class="item-info">
      <div class="item-header">Cappuccino ₱120</div>
      <div class="controls"><button onclick="changeQty('capp',-1)">-</button><span id="q-capp">0</span><button onclick="changeQty('capp',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="americano" data-price="100">
    <img src="https://www.foodandwine.com/thmb/9JyfZPcxlV9ubEeuSznhO-M4q0w=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/Partners-Americano-FT-BLOG0523-b8e18cc340574cc9bed536cceeec7082.jpg" alt="Americano">
    <div class="item-info">
      <div class="item-header">Americano ₱100</div>
      <div class="controls"><button onclick="changeQty('americano',-1)">-</button><span id="q-americano">0</span><button onclick="changeQty('americano',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="mocha" data-price="135">
    <img src="https://athome.starbucks.com/sites/default/files/styles/recipe_banner_xlarge/public/2024-05/CaffeMocha_RecipeHeader_848x539_%402x.jpg.webp?itok=ov3gQo8W" alt="Mocha">
    <div class="item-info">
      <div class="item-header">Mocha ₱135</div>
      <div class="controls"><button onclick="changeQty('mocha',-1)">-</button><span id="q-mocha">0</span><button onclick="changeQty('mocha',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="caramel" data-price="140">
    <img src="https://emilylaurae.com/wp-content/uploads/2022/10/Caramel-macchiato-4.jpg" alt="Caramel Macchiato">
    <div class="item-info">
      <div class="item-header">Caramel Macchiato ₱140</div>
      <div class="controls"><button onclick="changeQty('caramel',-1)">-</button><span id="q-caramel">0</span><button onclick="changeQty('caramel',1)">+</button></div>
    </div>
  </div>
</div>

<!-- MEALS -->
<div id="meals" class="category">
  <div class="menu-item" data-id="tapa" data-price="175">
    <img src="https://whatasiamakes.com/wp-content/uploads/2024/04/P1040101-800x530.jpg?w=200" alt="Beef Tapa">
    <div class="item-info">
      <div class="item-header">Beef Tapa ₱175</div>
      <div class="controls"><button onclick="changeQty('tapa',-1)">-</button><span id="q-tapa">0</span><button onclick="changeQty('tapa',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="adobo" data-price="145">
    <img src="https://www.foodandwine.com/thmb/byTnFTHAnIPFXZPq8XlC_UA9fSc=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/coconut-chicken-adobo-FT-RECIPE1020-1fa386126d214e9286fef96a6263b498.jpg" alt="Chicken Adobo">
    <div class="item-info">
      <div class="item-header">Chicken Adobo ₱145</div>
      <div class="controls"><button onclick="changeQty('adobo',-1)">-</button><span id="q-adobo">0</span><button onclick="changeQty('adobo',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="tocilog" data-price="155">
    <img src="https://static01.nyt.com/images/2023/03/14/multimedia/RB-Pork-Tocino-czgq/RB-Pork-Tocino-czgq-threeByTwoMediumAt2X-v2.jpg?w=200" alt="Pork Tocilog">
    <div class="item-info">
      <div class="item-header">Pork Tocilog ₱155</div>
      <div class="controls"><button onclick="changeQty('tocilog',-1)">-</button><span id="q-tocilog">0</span><button onclick="changeQty('tocilog',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="pancit" data-price="150">
    <img src="https://upload.wikimedia.org/wikipedia/commons/e/ef/Pancit_Ilonggo_Style_-_12110747826.jpg" alt="Pancit">
    <div class="item-info">
      <div class="item-header">Pancit ₱150</div>
      <div class="controls"><button onclick="changeQty('pancit',-1)">-</button><span id="q-pancit">0</span><button onclick="changeQty('pancit',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="burger" data-price="185">
    <img src="https://images.unsplash.com/photo-1586190848861-99aa4a171e90?w=200" alt="Classic Burger">
    <div class="item-info">
      <div class="item-header">Classic Burger ₱185</div>
      <div class="controls"><button onclick="changeQty('burger',-1)">-</button><span id="q-burger">0</span><button onclick="changeQty('burger',1)">+</button></div>
    </div>
  </div>
</div>

<!-- PASTRIES -->
<div id="pastries" class="category">
  <div class="menu-item" data-id="croissant" data-price="95">
    <img src="https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=200" alt="Croissant">
    <div class="item-info">
      <div class="item-header">Croissant ₱95</div>
      <div class="controls"><button onclick="changeQty('croissant',-1)">-</button><span id="q-croissant">0</span><button onclick="changeQty('croissant',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="muffin" data-price="88">
    <img src="https://wildernesswife.com/wp-content/uploads/2023/09/jordan_marsh_blueberry_muffin1.jpg	" alt="Blueberry Muffin">
    <div class="item-info">
      <div class="item-header">Blueberry Muffin ₱88</div>
      <div class="controls"><button onclick="changeQty('muffin',-1)">-</button><span id="q-muffin">0</span><button onclick="changeQty('muffin',1)">+</button></div>
    </div>
  </div>
  <div class="menu-item" data-id="donut" data-price="80">
    <img src="https://www.barbarabakes.com/wp-content/uploads/2022/11/chocolate-glazed-donuts-recipe-35-of-38-500x500.jpg" alt="Donut">
    <div class="item-info">
      <div class="item-header">Chocolate Donut ₱80</div>
      <div class="controls"><button onclick="changeQty('donut',-1)">-</button><span id="q-donut">0</span><button onclick="changeQty('donut',1)">+</button></div>
    </div>
  </div>
</div>


<!-- PAYMENT METHOD -->
<div class="payment-box">
  <b>Payment Method</b>
  <select id="paymentMethod">
    <option value="Cash">Cash</option>
    <option value="Card">Card</option>
    <option value="Gcash">Gcash</option>
    <Option value="Paymaya">PayMaya</Option>
  </select>
</div>

<!-- CASH INPUT -->
<div class="payment-box">
  <b>Cash</b>
  <input id="cash" type="number" placeholder="Enter cash">
</div>

<button class="main-btn" onclick="checkout()">✔ CONFIRM ORDER</button>
<div class="receipt" id="receipt"></div>

<script>
let cart={};

function changeQty(id,val){
  let q=cart[id]?.qty||0;
  q+=val;
  if(q<0) q=0;
  cart[id]={...cart[id],qty:q};
  document.getElementById('q-'+id).innerText=q;
  let elem=document.querySelector(`.menu-item[data-id="${id}"]`);
  cart[id].price=Number(elem.dataset.price);
  cart[id].name=elem.querySelector('.item-header').innerText;
}

function showCat(id,btn){
  document.querySelectorAll('.category').forEach(c=>c.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
}

function checkout(){
  let total=0,html="";
  for(let i in cart){
    if(cart[i].qty>0){
      let sub=cart[i].qty*cart[i].price;
      total+=sub;
      html+=`${cart[i].qty}x ${cart[i].name} — ₱${sub}<br>`;
    }
  }
  if(total==0) return alert("Add items first!");

  let paymentMethod=document.getElementById('paymentMethod').value;
  let cash=Number(document.getElementById('cash').value||0);

  if(paymentMethod==="Cash" && cash<total)
    return alert("Not enough cash!");

  let receipt=document.getElementById('receipt');
  receipt.style.display='block';
  receipt.innerHTML=`
    <center><b>DEJA BREW CAFE</b><br>${new Date().toLocaleString()}</center>
    <hr>${html}<hr>
    Total: ₱${total}<br>
    Payment Method: ${paymentMethod}<br>
    ${paymentMethod==="Cash" ? `Cash: ₱${cash}<br>Change: ₱${(cash-total).toFixed(2)}<br>` : ``}
    <center>Thank you ☕</center>
  `;
  window.print();
  cart={};
  document.querySelectorAll('.controls span').forEach(s=>s.innerText=0);
}
</script>
