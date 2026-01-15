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
  background:linear-gradient(rgba(0,0,0,.65),rgba(0,0,0,.65)),url("images/wedding1.jpg") center/cover no-repeat;
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

.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:25px;}

.calc{
  background:#111;
  padding:35px;
  border-radius:20px;
  max-width:700px;
  margin:0 auto;
}
.calc label{
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
  font-size:28px;
  text-align:center;
  color:#d4af37;
  font-weight:bold;
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
<a href="#calculator">Custom Package</a>
</nav>

<!-- ================= CUSTOM PACKAGE CALCULATOR ================= -->
<section id="calculator">
<h2>Custom Package Calculator (Per Day)</h2>

<div class="calc">

<label>
<span>Traditional Photographer (₹9,000)</span>
<span>
<input type="checkbox" data-price="9000" onchange="calcTotal()">
Days:
<input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</label>

<label>
<span>Traditional Videographer (₹16,000)</span>
<span>
<input type="checkbox" data-price="16000" onchange="calcTotal()">
Days:
<input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</label>

<label>
<span>Cinematic Videographer (₹25,000)</span>
<span>
<input type="checkbox" data-price="25000" onchange="calcTotal()">
Days:
<input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</label>

<label>
<span>Candid Photographer (₹16,000)</span>
<span>
<input type="checkbox" data-price="16000" onchange="calcTotal()">
Days:
<input type="number" min="1" value="1" onchange="calcTotal()">
</span>
</label>

<div class="total">
Total : ₹<span id="total">0</span>
</div>

<p style="text-align:center;color:#aaa;margin-top:10px;font-size:14px;">
* For multiple days, per-day price is calculated at half rate
</p>

</div>
</section>

<footer>
© 2026 Saai Wedding Films | Solapur
</footer>

<script>
function calcTotal(){
  let total = 0;

  document.querySelectorAll('.calc label').forEach(row=>{
    const checkbox = row.querySelector('input[type="checkbox"]');
    const daysInput = row.querySelector('input[type="number"]');

    if(checkbox.checked){
      const basePrice = parseInt(checkbox.dataset.price);
      const days = parseInt(daysInput.value) || 1;

      let price;
      if(days === 1){
        price = basePrice;
      }else{
        price = (basePrice / 2) * days;
      }

      total += price;
    }
  });

  document.getElementById("total").innerText = total;
}
</script>

</body>
</html>
