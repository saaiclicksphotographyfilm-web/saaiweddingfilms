<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Saai Wedding Film's</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Trendy Font -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">

<style>
body{margin:0;font-family:Arial;background:#0b0b0b;color:#fff;}

/* ===== HEADER WITH IMAGE (Option 1) ===== */
header{
  position:relative;
  text-align:center;
  padding:100px 20px;
  background:
    linear-gradient(rgba(0,0,0,.65), rgba(0,0,0,.65)),
    url("images/camera1.jpg") center/cover no-repeat;
}
header h1{
  font-family:'Playfair Display',serif;
  font-size:52px;
  letter-spacing:2px;
}
header p{color:#d4af37;font-size:20px;}

nav{position:sticky;top:0;background:#111;padding:15px;text-align:center;z-index:9;}
nav a{color:#fff;margin:0 15px;text-decoration:none;}
nav a:hover{color:#d4af37;}

section{padding:80px 20px;max-width:1200px;margin:auto;}
h2{text-align:center;margin-bottom:35px;color:#d4af37;}
h3{text-align:center;margin:40px 0 20px;}

.toggle{text-align:center;margin-bottom:40px;}
.toggle button{
  padding:10px 25px;
  margin:5px;
  border:none;
  border-radius:25px;
  background:#222;
  color:#fff;
  cursor:pointer;
}
.toggle .active{background:#d4af37;color:#000;}

.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:25px;}
.gallery img{
  width:100%;
  height:220px;
  object-fit:cover;
  border-radius:14px;
  box-shadow:0 10px 25px rgba(0,0,0,.6);
}

.package{
  background:#111;
  padding:25px;
  border-radius:18px;
  text-align:center;
}
.package h4{color:#d4af37;margin:10px 0;}
.price{color:#d4af37;font-size:20px;font-weight:bold;}

footer{text-align:center;padding:30px;background:#000;color:#777;}
</style>
</head>

<body>

<header>
<h1>Saai Wedding Film's</h1>
<p>Premium Cinematic Wedding Photography & Films</p>
</header>

<nav>
<a href="#packages">Packages</a>
</nav>

<section id="packages">

<div class="toggle">
<button class="active" onclick="showEvent('wedding',this)">Wedding</button>
<button onclick="showEvent('prewedding',this)">Pre-Wedding</button>
<button onclick="showEvent('engagement',this)">Engagement</button>
</div>

<!-- ================= WEDDING ================= -->
<div id="wedding">
<h2>Wedding</h2>
<div class="grid gallery">
<img src="images/wedding1.jpg">
<img src="images/wedding2.jpg">
</div>

<h3>Wedding Packages</h3>
<div class="grid">
<div class="package"><h4>Bronze</h4><div class="price" id="w-bronze"></div></div>
<div class="package"><h4>Silver</h4><div class="price" id="w-silver"></div></div>
<div class="package"><h4>Gold</h4><div class="price" id="w-gold"></div></div>
</div>
</div>

<!-- ================= PRE-WEDDING ================= -->
<div id="prewedding" style="display:none;">
<h2>Pre-Wedding</h2>
<div class="grid gallery">
<img src="images/prewedding1.jpg">
<img src="images/prewedding2.jpg">
</div>

<h3>Pre-Wedding Packages</h3>
<div class="grid">
<div class="package"><h4>Bronze</h4><div class="price" id="pw-bronze"></div></div>
<div class="package"><h4>Silver</h4><div class="price" id="pw-silver"></div></div>
<div class="package"><h4>Gold</h4><div class="price" id="pw-gold"></div></div>
</div>
</div>

<!-- ================= ENGAGEMENT ================= -->
<div id="engagement" style="display:none;">
<h2>Engagement</h2>
<div class="grid gallery">
<img src="images/engagement.jpg">
<img src="images/engagement2.jpg">
</div>

<h3>Engagement Packages</h3>
<div class="grid">
<div class="package"><h4>Bronze</h4><div class="price" id="e-bronze"></div></div>
<div class="package"><h4>Silver</h4><div class="price" id="e-silver"></div></div>
<div class="package"><h4>Gold</h4><div class="price" id="e-gold"></div></div>
</div>
</div>

</section>

<footer>© 2026 Saai Wedding Film's</footer>

<script>
/* ===== OPTION 3 : ALL PRICES IN ONE PLACE ===== */
const PRICES={
  wedding:{bronze:23000,silver:31000,gold:43000},
  prewedding:{bronze:15000,silver:22000,gold:30000},
  engagement:{bronze:18000,silver:28000,gold:43000}
};

/* assign prices */
w-bronze.innerText="₹"+PRICES.wedding.bronze;
w-silver.innerText="₹"+PRICES.wedding.silver;
w-gold.innerText="₹"+PRICES.wedding.gold;

pw-bronze.innerText="₹"+PRICES.prewedding.bronze;
pw-silver.innerText="₹"+PRICES.prewedding.silver;
pw-gold.innerText="₹"+PRICES.prewedding.gold;

e-bronze.innerText="₹"+PRICES.engagement.bronze;
e-silver.innerText="₹"+PRICES.engagement.silver;
e-gold.innerText="₹"+PRICES.engagement.gold;

/* ===== OPTION 2 : EVENT TOGGLE ===== */
function showEvent(id,btn){
["wedding","prewedding","engagement"].forEach(s=>{
document.getElementById(s).style.display="none";
});
document.getElementById(id).style.display="block";
document.querySelectorAll('.toggle button').forEach(b=>b.classList.remove('active'));
btn.classList.add('active');
}
</script>

</body>
</html>
