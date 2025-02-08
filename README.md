<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <title>Dyqani Im Online</title>
</head>
<style>
            body {
            font-family: Arial, sans-serif;
            background-color: #f9f9f9;
            margin: 0;
            padding: 0;
        }

         header {
            background-color: #4CAF50;
            color: white;
            padding: 15px 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: relative;
        }

        .header-title {
            flex-grow: 1;
            text-align: center;
            font-size: 30px;
            font-weight: bold;
        }
        

        /* Menuja e fshehur */
        .menu {   
            height: 100%;
            width: 250px;
            position: fixed;
            top: 0;
            left: -250px; /* Fillon i fshehur */
            background-color: #4CAF50;
            padding-top: 20px;
            transition: 0.3s;
            display: flex;
            flex-direction: column;
            box-shadow: 4px 0 10px rgba(0, 0, 0, 0.2);
        }

        .menu a {
            color: white;
            text-decoration: none;
            padding: 15px;
            font-size: 18px;
            display: block;
            transition: 0.2s;
        }

        .menu a:hover {
            background-color: #2e7031;
        }

        .menu-icon {
            font-size: 22px;
            cursor: pointer;
            background: none;
            border: none;
            color: white;
            padding: 10px;
        }

        /* Butoni për mbylljen e menusë */
        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 25px;
            color: white;
            cursor: pointer;
            border: none;
            background: none;
        }

        /* Kur menuja është e hapur */
        .menu.show {
            left: 0;
        }
        
        .sidebar {
            width: 250px;
            background-color: #4CAF50;
            padding: 10px;
            position: fixed;
            height: 100%;
            overflow-y: auto;
        }        


        .dropdown {
            width: 100%;
        }
        
        .dropbtn {
            background-color: #4CAF50;
            color: white;
            padding: 15px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            width: 100%;
            text-align: left;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .dropdown-content {
            display: none;
            background-color: #4CAF50;
            min-width: 100%;
            box-shadow: 0px 8px 16px rgba(0,0,0,0.2);
            z-index: 1;
            padding-left: 0px;
        }
        
        .dropdown-content a {
            color: white;
            padding: 10px 18px;
            text-decoration: none;
            display: block;
            transition: 0.3s;
        }
        
        .dropdown-content a:hover {
            background-color: #4CAF50;
        }
        

        /* Përshtatja për pajisjet mobile */
        @media screen and (max-width: 768px) {
            .menu {
                width: 200px;
            }
        }

        .container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
        }

        .product {
            background-color: white;
            margin: 10px;
            padding: 15px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease-in-out;
        }

        .product:hover {
            transform: scale(1.05);
        }

        .product img {
            max-width: 100%;
            border-radius: 8px;
        }

        .product h2 {
            font-size: 20px;
            color: #333;
        }

        .product p {
            color: #555;
        }

        .product .price {
            font-size: 18px;
            color: #4CAF50;
            margin: 10px 0;
        }

        .product button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .product button:hover {
            background-color: #45a049;
        }

        /* Shporta */
        .cart-btn {
            position: fixed;
            top: 2.7%;
            right: 3%;
            background-color: #4CAF50;
            color: white;
            padding: 10px 10px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 18px;
        }

        .cart {
            background-color: #fff;
            padding: 10px;
            position: fixed;
            top: 8%;
            right: 0.5%;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 250px;
            box-sizing: border-box;
            display: none;
        }

        .cart h3 {
            margin-top: 0;
        }

        .cart-item {
            margin-bottom: 10px;
        }

        /* Forma e Pagesës (Full-screen Box) */
         #payment-form {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7); /* Ngjyra transparente */
            color: white;
            justify-content: center;
            align-items: center;
            display: flex;
            flex-direction: column;
        }

        .payment-box {
            background-color: #fff;
            padding: 30px;
            border-radius: 10px;
            width: 50%; /* Gjysma e faqes */
            color: black;
            text-align: center;
        }

        .payment-box input {
            padding: 10px;
            margin: 10px;
            width: 100%;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        .payment-box button {
            padding: 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 10px 20px 10px 0;
            display: inline-block;
        }

        .payment-box button:nth-child(2) {
    background-color: #f44336; /* Ngjyrë tjetër për butonin "Mbyll" */
        }


        /* Media Queries për telefonat dhe tabletët */
        @media screen and (max-width: 768px) {
            .container {
                grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
                gap: 10px;
            }--yo

            .payment-box {
        width: 80%;
    }
    }
</style>
<body>
<header>
    <button class="menu-icon" onclick="toggleMenu()">☰ Menu</button>

    <h1 class="header-title">Dyqani Im Online</h1>
</header>

<!-- Menu Sidebar -->
<div class="menu" id="menu">
    <button class="close-btn" onclick="toggleMenu()">×</button>
    <a href="index.html">Home</a>
            <div class="dropdown">
            <button class="dropbtn" onclick="toggleDropdown('productsDropdown')">
                Produktet <i class="fas fa-chevron-down"></i>
            </button>
            <div id="productsDropdown" class="dropdown-content">
                <a href="#">Të reja</a>
                <a href="#">Më të shitura</a>
                <a href="#">Oferta</a>
            </div>
        </div>
    <a href="login.html">Login</a>
</div>
</header>
    
<div class="container">
    <!-- Produkti 1 -->
    <div class="product" id="product1">
        <img src="https://via.placeholder.com/200" alt="Produkt 1">
        <h2>Produkt 1</h2>
        <p>Lorem ipsum dolor sit amet</p>
        <div class="price">$50</div>
        <button onclick="addToCart('Produkt 1', 50)">Shto në Shportë</button>
    </div>

    <!-- Produkti 2 -->
    <div class="product" id="product2">
        <img src="https://via.placeholder.com/200" alt="Produkt 2">
        <h2>Produkt 2</h2>
        <p>Lorem ipsum dolor sit amet</p>
        <div class="price">$30</div>
        <button onclick="addToCart('Produkt 2', 30)">Shto në Shportë</button>
    </div>

    <!-- Produkti 3 -->
    <div class="product" id="product3">
        <img src="https://via.placeholder.com/200" alt="Produkt 3">
        <h2>Produkt 3</h2>
        <p>Lorem ipsum dolor sit amet</p>
        <div class="price">$75</div>
        <button onclick="addToCart('Produkt 3', 75)">Shto në Shportë</button>
    </div>

     <!-- Produkt 4 -->
    <div class="product" id="product4">
        <img src="https://via.placeholder.com/200" alt="Produkt 4">
        <h2>Produkt 4</h2>
        <p>dardh</p>
        <div class="price">$5</div>
        <button onclick="addToCart('Produkt 4', 5)">Shto në Shportë</button>
    </div>

    <!-- Produkt 5 -->
    <div class="product" id="product5">
        <img src="https://via.placeholder.com/200" alt="Produkt 5">
        <h2>Produkt 5</h2>
        <p>modh</p>
        <div class="price">$3</div>
        <button onclick="addToCart('Produkt 5', 3)">Shto në Shportë</button>
    </div>

</div>

   <!-- Butoni i Shportës -->
    <button  class="cart-btn" onclick="toggleCart()">Shporta (0)</button>

    <!-- Shporta -->
    <div class="cart" id="cart">
        <h3>Shporta Juaj</h3>
        <div id="cart-items"></div>
        <button onclick="checkout()">Paguaj</button>
    </div>



<!-- Formë Pagesë -->
<div id="payment-form">
    <h3>Formë Pagesë</h3>
    <form action="/submit-payment" method="POST">
        <label for="name">Emri:</label><br>
        <input type="text" id="name" name="name" required><br><br>

        <label for="surname">Mbiemri:</label><br>
        <input type="text" id="surname" name="surname" required><br><br>

    <form action="/submit-payment" method="POST" onsubmit="return validatePaymentForm()">
        <label for="card">Numri i Kartës:</label><br>
        <input type="text" id="card" name="card" maxlength="16" required><br><br>


        <label for="expiry-date">Data e Skadimit:</label><br>
        <input type="month" id="expiry-date" name="expiry-date" required><br><br>

        <label for="cvv">CVV:</label><br>
        <input type="text" id="cvv" name="cvv" maxlength="4" required><br><br>

        <input type="submit" value="Paguaj">
         <button type="button" onclick="closePaymentForm()">Mbyll</button>
    </form>

</div>

<!-- Divi që do të shfaqë të dhënat e pagesës -->
<div id="payment-box" style="display:none;">
    <h3>Të Dhënat e Pagesës</h3>
    <div id="payment-details"></div>
</div>

    <script>
    let cart = [];

    // Funksioni për shtimin e produktit në shportë
    function addToCart(productName, price) {
        cart.push({ productName, price });
        updateCartButton();
        updateCart();
    }

    // Funksioni për përditësimin e butonit të shportës
    function updateCartButton() {
        const cartButton = document.querySelector('.cart-btn');
        cartButton.innerText = `Shporta (${cart.length})`; // Përshtat numrin e artikujve në shportë
    }

    // Funksioni për përditësimin e shportës
    function updateCart() {
        let cartItems = document.getElementById('cart-items');
        cartItems.innerHTML = '';
        cart.forEach((item, index) => {
            const cartItem = document.createElement('div');
            cartItem.classList.add('cart-item');
            cartItem.innerHTML = `${item.productName} - $${item.price} 
                <button onclick="removeFromCart(${index})">Heq</button>`;
            cartItems.appendChild(cartItem);
        });
    }

    // Funksioni për heqjen e produktit nga shporta
    function removeFromCart(index) {
        cart.splice(index, 1); // Heqim produktin nga shporta
        updateCartButton();
        updateCart(); // Përditësojmë shportën pas heqjes
    }

    // Funksioni për të hapur dhe mbyllur shportën
    function toggleCart() {
        const cartContainer = document.getElementById('cart')
        cartContainer.style.display = cartContainer.style.display === 'block' ? 'none' : 'block'; // Ndërron shfaqjen e shportës

    }
    function clearCart() {
    localStorage.removeItem("cart"); // Fshin shportën nga localStorage
    document.getElementById("cart-items").innerHTML = ""; // Pastron shfaqjen e produkteve
    updateCartTotal(); // Rifreskon totalin në shportë
    }
        // Funksioni për të kaluar në formën e pagesës
    function checkout() {
        document.getElementById('cart').style.display = 'none';
        document.getElementById('payment-form').style.display = 'flex'; // Shfaqim formën e pagesës
    }

    // Funksioni për të mbyllur formën e pagesës
    function closePaymentForm() {
        document.getElementById('payment-form').style.display = 'none'; // Mbyllim formën e pagesës
        document.getElementById('cart').style.display = 'block'; // Rishfaqim shportën
    }

    // Sigurohuni që forma e pagesës është e fshehur kur faqja ngarkohet
window.onload = function() {
    document.getElementById('payment-form').style.display = 'none';
};
function clearCart() {
    localStorage.removeItem("cart"); // Fshin shportën nga localStorage
    document.getElementById("cart-items").innerHTML = ""; // Pastron shfaqjen e produkteve
    updateCartTotal(); // Rifreskon totalin në shportë
}
function completePayment() {
    // Logjika e pagesës (p.sh., validimi, dërgimi i të dhënave, etj.)

    alert("Pagesa u krye me sukses!"); // Njoftim për përdoruesin
    clearCart(); // Pastron shportën pas pagesës
}
document.addEventListener("DOMContentLoaded", function() {
    let cart = localStorage.getItem("cart");
    if (!cart) {
        document.getElementById("cart-items").innerHTML = "";
    }
});
function validatePaymentForm() {
    let cardNumber = document.getElementById("card").value.trim();
    let cvv = document.getElementById("cvv").value.trim();
    
    // RegEx për 16 shifra (vetëm numra)
    let cardRegex = /^\d{16}$/;
    let cvvRegex = /^\d{3,4}$/;

    if (!cardRegex.test(cardNumber)) {
        alert("Numri i kartës duhet të ketë saktësisht 16 shifra!");
        return false;
    }

    if (!cvvRegex.test(cvv)) {
        alert("CVV duhet të ketë 3 ose 4 shifra!");
        return false;
    }

    alert("Pagesa u krye me sukses!"); // Njoftim për përdoruesin
    clearCart(); // Pastron shportën pas pagesës
    return true;
}
document.getElementById("card").addEventListener("input", function() {
    this.value = this.value.replace(/\D/g, ""); // Lejon vetëm numra
});

document.getElementById("cvv").addEventListener("input", function() {
    this.value = this.value.replace(/\D/g, ""); // Lejon vetëm numra
});

    function toggleMenu() {
        let menu = document.getElementById("menu");
        menu.classList.toggle("show");
    }

    // Mbyllja e menusë kur klikohet jashtë saj
    document.addEventListener("click", function(event) {
        let menu = document.getElementById("menu");
        let menuIcon = document.querySelector(".menu-icon");
        if (!menu.contains(event.target) && !menuIcon.contains(event.target)) {
            menu.classList.remove("show");
        }
    });
            function toggleDropdown(id) {
            var dropdown = document.getElementById(id);
            if (dropdown.style.display === "block") {
                dropdown.style.display = "none";
            } else {
                dropdown.style.display = "block";
            }
        }

</script>
</body>
</html>
