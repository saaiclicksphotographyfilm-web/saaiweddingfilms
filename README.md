<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Saai Wedding Films | Cinematic Photography</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">

<style>
body{margin:0;font-family:Arial;background:#0b0b0b;color:#fff;}

header{
  background:linear-gradient(rgba(0,0,0,.65),rgba(0,0,0,.65)),
  url("images/wedding1.jpg") center/cover no-repeat;
  text-align:center;
  padding:120px 20px;
}
header h1{font-family:'Playfair Display',serif;font-size:52px;}
header p{color:#d4af37;font-size:20px;}

nav{
  position:sticky;top:0;z-index:9;
  background:#111;text-align:center;padding:15px;
}
nav a{color:#fff;margin:0 15px;text-decoration:none;}
nav a:hover{color:#d4af37;}

section{padding:80px 20px;max-width:1200px;margin:auto;}
h2{text-align:center;color:#d4af37;margin-bottom:40px;}
h3{text-align:center;margin:30px 0;}

.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:25px;
}

.gallery img{
  width:100%;
  height:220px;
  object-fit:cover;
  border-radius:16px;
  box-shadow:0 10px 25px rgba(0,0,0,.6);
}

.package{
  background:#111;
  padding:25px;
  border-radius:18px;
  text-align:center;
}
.package h4{color:#d4af37;}
.price{color:#d4af37;font-size:18px;font-weight:bold;}

.calc{
  background:#111;
  padding:35px;
  border-radius:20px;
  max-width:800px;
  margin:0 auto;
}
.calc .row{
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:12px 0;
  font-size:18px;
}
.calc input[type="checkbox"]{transform:scale(1.2);}
.calc input[type="number"]{
  width:70px;
  padding:6px;
  border-radius:8px;
  border:none;
}

.total{
  margin-top:25px;
  font-size:30px;
  text-align:center;
  color:#d4af37;
  font-weight:bold;
}

.contact-box{
  background:#111;
  padding:30px;
  border-radius:18px;
  text-align:center;
}

.btn{
  display:inline-block;
  padding:12px 30px;
  background:#d4af37;
  color:#000;
  border-radius:30px;
  text-decoration:none;
  margin-top:15px;
}

footer{text-align:center;padding:30px;background:#000;color:#777;}
</style>
</head>

<body>

<header>
<h1>Saai Wedding Films</h1>
<p>Cinematic Wedding Photography & Films</p>
</header>

<nav>
<a href="#services">Services</a>
<a href="#calculator">Custom Package</a>
<a href="#contact">Contact</a>
</nav>

<!-- SERVICES -->
<section id="services">

<h2>Wedding Photography</h2>
<div class="grid gallery">
<img src="images/wedding1.jpg">
<img src="images/wedding2.jpg">
</div>

<h3>Wedding Packages</h3>
<div class="grid">
<div class="package"><h4>Silver</h4><div class="price">₹31,000</div></div>
<div class="package"><h4>Gold</h4><div class="price">₹43,000</div></div>
<div class="package"><h4>Platinum</h4><div class="price">₹65,000</div></div>
</div>

</section>

<!-- ================= CUSTOM PACKAGE CALCULATOR ================= -->
<section id="calculator">
<h2>Custom Package Calculator (Per Day)</h2>

<div class="calc">

<div class="row">
<span>Traditional Photographer (₹9,000)</span>
<span>
<input type="checkbox" data-price="9000" onchange="calcTotal()">
Days <input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</div>

<div class="row">
<span>Traditional Videographer (₹16,000)</span>
<span>
<input type="checkbox" data-price="16000" onchange="calcTotal()">
Days <input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</div>

<div class="row">
<span>Candid Photographer (₹16,000)</span>
<span>
<input type="checkbox" data-price="16000" onchange="calcTotal()">
Days <input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</div>

<div class="row">
<span>Cinematic Videographer (₹25,000)</span>
<span>
<input type="checkbox" data-price="25000" onchange="calcTotal()">
Days <input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</div>

<div class="total">
Total : ₹<span id="total">0</span>
</div>

<p style="text-align:center;color:#aaa;font-size:14px;">
* Per day price = base price / 2
</p>

</div>
</section>

<!-- CONTACT -->
<section id="contact">
<h2>Contact Us</h2>
<div class="grid">
<div class="contact-box">
<p>📞 Mobile / WhatsApp</p>
<h3>8698029935</h3>
<p>📍 Solapur</p>
<a class="btn" href="https://wa.me/918698029935" target="_blank">WhatsApp Now</a>
</div>
<div class="contact-box">
<p>📸 Follow on Instagram</p>
<a class="btn" href="https://www.instagram.com/_saai_clicks?igsh=MWh2eTlmemNhcWR3dA==" target="_blank">
Instagram
</a>
</div>
</div>
</section>

<footer>
© 2026 Saai Wedding Films | Solapur
</footer>

<script>
function calcTotal(){
  let total = 0;

  document.querySelectorAll('.calc .row').forEach(row=>{
    const checkbox = row.querySelector('input[type="checkbox"]');
    const daysInput = row.querySelector('input[type="number"]');

    if(checkbox.checked){
      const basePrice = parseInt(checkbox.dataset.price);
      const days = parseInt(daysInput.value) || 1;

      const perDay = basePrice / 2;
      total += perDay * days;
    }
  });

  document.getElementById("total").innerText = total;
}
</script>

</body>
</html>
