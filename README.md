<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Sri Lakshmi Tours and Travels</title>

<style>

body{
    margin:0;
    font-family:Arial, sans-serif;
    background:#f4f4f4;
}

header{
    background:#0056d6;
    color:white;
    text-align:center;
    padding:20px;
}

.container{
    max-width:500px;
    background:white;
    margin:30px auto;
    padding:20px;
    border-radius:15px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
}

h2{
    text-align:center;
    margin-bottom:20px;
}

input, select{
    width:100%;
    padding:12px;
    margin-bottom:15px;
    border-radius:8px;
    border:1px solid #ccc;
    font-size:16px;
}

button{
    width:100%;
    padding:15px;
    border:none;
    background:green;
    color:white;
    font-size:18px;
    border-radius:10px;
    cursor:pointer;
}

button:hover{
    background:darkgreen;
}

.result{
    margin-top:20px;
    background:#f1f1f1;
    padding:15px;
    border-radius:10px;
    font-size:18px;
    line-height:1.8;
}

.whatsapp{
    display:block;
    margin-top:20px;
    text-align:center;
    background:#25D366;
    color:white;
    padding:15px;
    border-radius:10px;
    text-decoration:none;
    font-size:18px;
}

.cod{
    display:block;
    margin-top:15px;
    text-align:center;
    background:#ff9800;
    color:white;
    padding:15px;
    border-radius:10px;
    text-decoration:none;
    font-size:18px;
}

footer{
    background:#222;
    color:white;
    text-align:center;
    padding:15px;
    margin-top:30px;
}

</style>
</head>

<body>

<header>
    <h1>Sri Lakshmi Tours and Travels</h1>
</header>

<div class="container">

    <h2>Book Your Travel</h2>

    <input type="text" id="name" placeholder="Enter Your Name">

    <input type="number" id="phone" placeholder="Enter Phone Number">

    <input type="number" id="members" placeholder="How Many Members">

    <input type="text" id="pickup" placeholder="Pick Up Location">

    <input type="text" id="drop" placeholder="Drop Location">

    <input type="number" id="distance" placeholder="Distance in KM">

    <select id="payment">
        <option>Cash On Delivery</option>
        <option>PhonePe</option>
        <option>Google Pay</option>
    </select>

    <button onclick="calculatePrice()">
        Calculate Price
    </button>

    <div class="result" id="result">
        Total Price: ₹0
    </div>

    <a id="whatsappBtn" class="whatsapp" href="#">
        Send Booking in WhatsApp
    </a>

    <a class="cod" href="#">
        Cash On Delivery Available
    </a>

</div>

<footer>
    © 2026 Sri Lakshmi Tours and Travels
</footer>

<script>

function calculatePrice(){

    let name = document.getElementById("name").value;
    let phone = document.getElementById("phone").value;
    let members = document.getElementById("members").value;
    let pickup = document.getElementById("pickup").value;
    let drop = document.getElementById("drop").value;
    let distance = document.getElementById("distance").value;
    let payment = document.getElementById("payment").value;

    // 1 KM = 30 Rupees
    let rate = 30;

    // Auto Price Calculation
    let total = distance * rate;

    document.getElementById("result").innerHTML =
    "Name: " + name + "<br>" +
    "Phone: " + phone + "<br>" +
    "Members: " + members + "<br>" +
    "Pick Up: " + pickup + "<br>" +
    "Drop: " + drop + "<br>" +
    "Distance: " + distance + " KM<br>" +
    "Payment Method: " + payment + "<br><br>" +
    "<b>Total Price: ₹" + total + "</b>";

    let message =
`Sri Lakshmi Tours Booking

Name: ${name}
Phone: ${phone}
Members: ${members}
Pick Up: ${pickup}
Drop: ${drop}
Distance: ${distance} KM
Payment: ${payment}
Total Price: ₹${total}`;

    // Change to your WhatsApp number
    let whatsappLink =
"https://wa.me/999999999?text=" + encodeURIComponent(message);

    document.getElementById("whatsappBtn").href = whatsappLink;

}

</script>

</body>
</html>
