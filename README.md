<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Магазин товаров</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }

        .product-card {
            border: 1px solid #ccc;
            padding: 10px;
            margin: 10px;
            width: 200px;
            text-align: center;
        }

        .add-to-cart-button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
            border-radius: 4px;
        }
    </style>
</head>
<body>

<div class="product-card" id="product1">
    <h2>Товар 1</h2>
    <p>Описание товара 1</p>
    <p>Цена: $10</p>
    <button class="add-to-cart-button" onclick="addToCart('Товар 1', 10)">Добавить в корзину</button>
</div>

<div class="product-card" id="product2">
    <h2>Товар 2</h2>
    <p>Описание товара 2</p>
    <p>Цена: $15</p>
    <button class="add-to-cart-button" onclick="addToCart('Товар 2', 15)">Добавить в корзину</button>
</div>

<div id="cart">
    <h2>Корзина</h2>
    <ul id="cart-items"></ul>
</div>

<script>
    let cartItems = [];

    function addToCart(product, price) {
        cartItems.push({ product, price });
        updateCart();
    }

    function updateCart() {
        let cartList = document.getElementById("cart-items");
        cartList.innerHTML = "";

        cartItems.forEach(item => {
            let listItem = document.createElement("li");
            listItem.textContent = `${item.product} - $${item.price}`;
            cartList.appendChild(listItem);
        });
    }
</script>

</body>
</html>
