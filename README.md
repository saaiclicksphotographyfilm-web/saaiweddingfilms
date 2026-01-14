<html lang="en">
<head>
<meta charset="UTF-8">
<title>Saai Wedding Film's | Cinematic Wedding Photographer</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{margin:0;font-family:Arial;background:#0b0b0b;color:#fff;}
header{text-align:center;padding:100px 20px;background:radial-gradient(circle,#1c1c1c,#000);}
header h1{font-size:48px;}
header p{color:#d4af37;font-size:20px;}

nav{position:sticky;top:0;background:#111;padding:15px;text-align:center;}
nav a{color:#fff;margin:0 15px;text-decoration:none;}
nav a:hover{color:#d4af37;}

section{padding:80px 20px;max-width:1200px;margin:auto;}
h2{text-align:center;margin-bottom:40px;}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:25px;}

.btn{padding:12px 30px;background:#d4af37;color:#000;border-radius:30px;text-decoration:none;font-weight:bold;display:inline-block;margin-top:15px;}

.toggle{text-align:center;margin-bottom:30px;}
.toggle button{padding:10px 25px;margin:5px;border:none;border-radius:25px;background:#222;color:#fff;cursor:pointer;}
.toggle .active{background:#d4af37;color:#000;}

.package{background:#111;padding:25px;border-radius:18px;text-align:center;box-shadow:0 10px 25px rgba(0,0,0,.6);}
.package h3{color:#d4af37;}
.package ul{list-style:none;padding:0;}
.package li{margin:8px 0;}

.custom{max-width:500px;margin:auto;}
.custom label{display:block;margin:10px 0;}
.total{font-size:22px;color:#d4af37;margin-top:15px;}

input,textarea{width:100%;padding:12px;border:none;border-radius:8px;margin:8px 0;}

.whatsapp{position:fixed;bottom:25px;right:25px;background:#25D366;color:#fff;padding:14px 22px;border-radius:50px;text-decoration:none;}
footer{text-align:center;padding:30px;background:#000;color:#777;}
</style>
</head>

<body>

<header>
<h1>Saai Wedding Film's</h1>
<p>Premium Cinematic Wedding Photography & Films</p>
<a href="#packages" class="btn">View Packages</a>
</header>

<nav>
<a href="#packages">Packages</a>
<a href="#contact">Contact</a>
</nav>

<section id="packages">
<h2>Packages & Pricing</h2>

<div class="toggle">
<button class="active" onclick="showType('wedding',this)">Wedding</button>
<button onclick="showType('engagement',this)">Engagement</button>
</div>

<!-- WEDDING -->
<div id="wedding" class="grid">
<div class="package">
<h3>Bronze</h3>
<ul><li>Traditional Photo</li><li>Traditional Video</li></ul>
<h3>₹23,000</h3>
<button class="btn" onclick="selectPackage('Wedding Bronze','23000')">Book Now</button>
</div>

<div class="package">
<h3>Silver</h3>
<ul><li>Candid Photo</li><li>Traditional Video</li></ul>
<h3>₹31,000</h3>
<button class="btn" onclick="selectPackage('Wedding Silver','31000')">Book Now</button>
</div>

<div class="package">
<h3>Gold</h3>
<ul><li>Candid Photo</li><li>Cinematic Video</li></ul>
<h3>₹43,000</h3>
<button class="btn" onclick="selectPackage('Wedding Gold','43000')">Book Now</button>
</div>

<div class="package">
<h3>Platinum</h3>
<ul><li>All Services</li></ul>
<h3>₹66,000</h3>
<button class="btn" onclick="selectPackage('Wedding Platinum','66000')">Book Now</button>
</div>
</div>

<!-- ENGAGEMENT -->
<div id="engagement" class="grid" style="display:none;">
<div class="package">
<h3>Engagement Basic</h3>
<h3>₹18,000</h3>
<button class="btn" onclick="selectPackage('Engagement Basic','18000')">Book Now</button>
</div>

<div class="package">
<h3>Engagement Premium</h3>
<h3>₹43,000</h3>
<button class="btn" onclick="selectPackage('Engagement Premium','43000')">Book Now</button>
</div>
</div>

<h2 style="margin-top:60px;">Custom Package</h2>
<div class="package custom">
<label><input type="checkbox" value="25000" onchange="calc()"> Cinematic Videographer – ₹25,000</label>
<label><input type="checkbox" value="18000" onchange="calc()"> Candid Photographer – ₹18,000</label>
<label><input type="checkbox" value="13000" onchange="calc()"> Traditional Videographer – ₹13,000</label>
<label><input type="checkbox" value="10000" onchange="calc()"> Traditional Photographer – ₹10,000</label>

<div class="total">Total: ₹<span id="total">0</span></div>
<button class="btn" onclick="sendCustom()">Send on WhatsApp</button>
</div>
</section>

<section id="contact">
<h2>Contact</h2>
<form>
<input type="text" id="pkg" placeholder="Selected Package">
<input type="text" id="amount" placeholder="Amount">
<input type="text" placeholder="Your Name">
<input type="tel" placeholder="Mobile Number">
<textarea placeholder="Details"></textarea>
</form>
</section>

<a class="whatsapp" href="https://wa.me/918698029935">WhatsApp</a>

<footer>© 2026 Saai Wedding Film's</footer>

<script>
let selectedPackage='',selectedAmount='';

function showType(t,btn){
document.getElementById("wedding").style.display=t=='wedding'?'grid':'none';
document.getElementById("engagement").style.display=t=='engagement'?'grid':'none';
document.querySelectorAll('.toggle button').forEach(b=>b.classList.remove('active'));
btn.classList.add('active');
}

function selectPackage(name,amt){
document.getElementById("pkg").value=name;
document.getElementById("amount").value="₹"+amt;
window.open(`https://wa.me/918698029935?text=Package: ${name}%0AAmount: ₹${amt}`);
}

function calc(){
let t=0;
document.querySelectorAll('.custom input:checked').forEach(i=>t+=+i.value);
document.getElementById("total").innerText=t;
}

function sendCustom(){
let total=document.getElementById("total").innerText;
window.open(`https://wa.me/918698029935?text=Custom Package Total: ₹${total}`);
}
</script>

</body>
</html>
