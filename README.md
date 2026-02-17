<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>QuickDoor - Premium B2C Delivery</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins',sans-serif;
}
body{
  background:#f5f7fa;
  color:#333;
}
header{
  background:linear-gradient(135deg,#ff416c,#ff4b2b);
  color:white;
  padding:20px 50px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}
header h1{
  font-size:28px;
}
nav a{
  color:white;
  text-decoration:none;
  margin-left:20px;
  font-weight:500;
}
.hero{
  text-align:center;
  padding:60px 20px;
}
.hero h2{
  font-size:40px;
  margin-bottom:10px;
}
.section{
  padding:50px 60px;
}
.section h2{
  margin-bottom:30px;
  font-size:28px;
}
.products{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:25px;
}
.card{
  background:white;
  border-radius:15px;
  padding:20px;
  box-shadow:0 10px 25px rgba(0,0,0,0.1);
  transition:0.3s;
}
.card:hover{
  transform:translateY(-10px);
}
.card img{
  width:100%;
  border-radius:10px;
}
.card h3{
  margin:15px 0;
}
.price{
  font-weight:600;
  color:#ff416c;
}
button{
  background:#ff416c;
  color:white;
  border:none;
  padding:10px 15px;
  border-radius:8px;
  cursor:pointer;
  margin-top:10px;
}
button:hover{
  background:#ff4b2b;
}
.cart{
  position:fixed;
  right:20px;
  bottom:20px;
  background:white;
  padding:20px;
  width:300px;
  border-radius:15px;
  box-shadow:0 10px 30px rgba(0,0,0,0.2);
}
.cart h3{
  margin-bottom:10px;
}
.delivery{
  background:#fff;
  padding:40px 60px;
}
.delivery-card{
  background:#f0f3f7;
  padding:20px;
  border-radius:15px;
  display:flex;
  align-items:center;
  gap:20px;
}
footer{
  text-align:center;
  padding:20px;
  background:#222;
  color:white;
  margin-top:50px;
}
.payment-modal{
  display:none;
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.5);
  justify-content:center;
  align-items:center;
}
.payment-box{
  background:white;
  padding:30px;
  border-radius:15px;
  width:350px;
}
input{
  width:100%;
  padding:8px;
  margin:8px 0;
  border-radius:8px;
  border:1px solid #ccc;
}
</style>
</head>

<body>

<header>
  <h1>QuickDoor</h1>
  <nav>
    <a href="#">Home</a>
    <a href="#">Products</a>
    <a href="#">Delivery</a>
  </nav>
</header>

<div class="hero">
  <h2>Premium B2C Door Delivery</h2>
  <p>Fast • Reliable • Secure Payments</p>
</div>

<!-- RICE SECTION -->
<div class="section">
<h2>Rice</h2>
<div class="products">
  <div class="card">
    <img src="https://via.placeholder.com/300">
    <h3>Basmati Rice</h3>
    <p class="price">₹500</p>
    <button onclick="addToCart(500)">Add to Cart</button>
  </div>
  <div class="card">
    <img src="https://via.placeholder.com/300">
    <h3>Brown Rice</h3>
    <p class="price">₹400</p>
    <button onclick="addToCart(400)">Add to Cart</button>
  </div>
</div>
</div>

<!-- KITCHEN APPLIANCES -->
<div class="section">
<h2>Kitchen Appliances</h2>
<div class="products">
  <div class="card">
    <img src="https://via.placeholder.com/300">
    <h3>Electric Cooker</h3>
    <p class="price">₹2500</p>
    <button onclick="addToCart(2500)">Add to Cart</button>
  </div>
  <div class="card">
    <img src="https://via.placeholder.com/300">
    <h3>Blender</h3>
    <p class="price">₹1500</p>
    <button onclick="addToCart(1500)">Add to Cart</button>
  </div>
</div>
</div>

<!-- SNACKS SECTION -->
<div class="section">
<h2>Chips & Biscuits</h2>
<div class="products">
  <div class="card">
    <img src="https://via.placeholder.com/300">
    <h3>Potato Chips</h3>
    <p class="price">₹50</p>
    <button onclick="addToCart(50)">Add to Cart</button>
  </div>
  <div class="card">
    <img src="https://via.placeholder.com/300">
    <h3>Chocolate Biscuits</h3>
    <p class="price">₹60</p>
    <button onclick="addToCart(60)">Add to Cart</button>
  </div>
</div>
</div>

<!-- DELIVERY BOY DETAILS -->
<div class="delivery">
<h2>Delivery Partner</h2>
<div class="delivery-card">
  <img src="https://via.placeholder.com/100" style="border-radius:50%">
  <div>
    <h3>Ravi Kumar</h3>
    <p>Experience: 3 Years</p>
    <p>Rating: ⭐ 4.8</p>
    <p>Contact: +91 9876543210</p>
  </div>
</div>
</div>

<!-- CART -->
<div class="cart">
<h3>Cart Total</h3>
<p>₹ <span id="total">0</span></p>
<button onclick="openPayment()">Proceed to Payment</button>
</div>

<!-- PAYMENT MODAL -->
<div class="payment-modal" id="paymentModal">
  <div class="payment-box">
    <h3>Payment Details</h3>
    <input type="text" placeholder="Card Number">
    <input type="text" placeholder="Name on Card">
    <input type="text" placeholder="Expiry Date">
    <input type="text" placeholder="CVV">
    <button onclick="payNow()">Pay Now</button>
  </div>
</div>

<footer>
© 2026 QuickDoor | Premium Delivery Service
</footer>

<script>
let total = 0;

function addToCart(price){
  total += price;
  document.getElementById("total").innerText = total;
}

function openPayment(){
  document.getElementById("paymentModal").style.display = "flex";
}

function payNow(){
  alert("Payment Successful! Order Placed.");
  total = 0;
  document.getElementById("total").innerText = total;
  document.getElementById("paymentModal").style.display = "none";
}
</script>

</body>
</html>
