<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Asyl Онлайн Дүкені</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #ffcccc;
            padding: 15px;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #333;
        }

        .auth-buttons {
            display: flex;
            align-items: center;
        }

        .auth-buttons a {
            text-decoration: none;
            margin-left: 10px;
            padding: 10px 15px;
            background-color: #ff6666;
            color: white;
            border-radius: 5px;
            transition: background-color 0.3s;
        }

        .auth-buttons a:hover {
            background-color: #ff4d4d;
        }

        .cart-icon {
            font-size: 24px;
            color: #333;
            margin-left: 10px;
            cursor: pointer;
        }

        .products {
            padding: 40px 20px;
            background-color: white;
        }

        .section-title {
            text-align: center;
            font-size: 36px;
            margin-bottom: 30px;
        }

        .product-grid {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }

        .product-card {
            background-color: white;
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 20px;
            width: 220px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .product-card:hover {
            transform: translateY(-10px);
        }

        .product-card img {
            width: 100%;
            height: auto;
            border-radius: 10px;
        }

        .price {
            color: #ff6666;
            font-weight: bold;
            font-size: 18px;
        }

        .quantity-input {
            width: 40px;
            margin: 0 10px;
            text-align: center;
        }

        .add-to-cart-btn {
            margin-top: 10px;
            padding: 10px;
            background-color: #ff6666;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .add-to-cart-btn:hover {
            background-color: #ff4d4d;
        }

        .modal {
            display: none;
            position: fixed;
            top: 20%;
            left: 30%;
            width: 40%;
            padding: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            border-radius: 10px;
        }

        .modal-content {
            text-align: center;
        }

        .modal-content input {
            width: 80%;
            padding: 10px;
            margin: 10px 0;
        }

        button {
            padding: 10px 20px;
            background-color: #ff6666;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #ff4d4d;
        }

        .cart-total {
            font-size: 18px;
            margin-top: 20px;
        }

        .checkout-btn {
            margin-top: 20px;
            padding: 10px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .checkout-btn:hover {
            background-color: #218838;
        }

        .payment-modal {
            display: none;
            position: fixed;
            top: 20%;
            left: 30%;
            width: 40%;
            padding: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            border-radius: 10px;
        }

        .remove-item {
            color: red;
            cursor: pointer;
            margin-left: 10px;
        }

        .payment-message {
            font-size: 18px;
            margin-top: 20px;
        }

        .payment-form input {
            width: 90%;
            margin: 5px 0;
            padding: 10px;
        }

        footer {
            margin-top: 50px;
            background-color: #ffcccc;
            padding: 20px;
            text-align: center;
        }

        footer .social-links a {
            color: #333;
            text-decoration: none;
            margin: 0 15px;
            font-size: 20px;
            transition: color 0.3s;
        }

        footer .social-links a:hover {
            color: #ff6666;
        }
         /* Иконка стилі */
         #profile-icon {
            font-size: 24px;
            cursor: pointer;
            position: relative;
        }

        /* Жеке кабинет мәзір стилі */
        #profile-menu {
            display: none;
            position: absolute;
            top: 30px;
            right: 0;
            background-color: #f9f9f9;
            padding: 15px;
            border: 1px solid #ddd;
            width: 200px;
            z-index: 100;
        }

        #profile-menu p {
            margin: 5px 0;
            font-size: 14px;
        }
         /* Стильдер */
        #profile-icon {
            font-size: 24px;
            cursor: pointer;
            display: none; /* Алғашында көрінбейді */
        }

        #profile-menu {
            display: none;
            position: absolute;
            top: 40px;
            right: 10px;
            background-color: #f9f9f9;
            padding: 15px;
            border: 1px solid #ddd;
            width: 200px;
        }

        #profile-menu p {
            margin: 5px 0;
            font-size: 14px;
        }

        .form-container {
            margin: 20px 0;
        }
        .header {
            display: flex;
            justify-content: flex-end;
            margin-bottom: 20px;
        }
        .user-info {
            position: relative;
            display: inline-block;
            margin-right: 20px;
        }
        .user-icon-container {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: #ff4d4d;
            color: white;
            font-size: 20px;
            font-weight: bold;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
        }
        .user-details {
            display: none;
            position: absolute;
            top: 60px;
            right: 0;
            width: 250px;
            background-color: white;
            padding: 15px;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .close-button {
            float: right;
            cursor: pointer;
            font-weight: bold;
            color: #888;
        }
        .close-button:hover {
            color: black;
        }
    </style>
</head>
<body>

<header>
    <div class="navbar">
        <div class="logo">Asyl</div>
        <div class="auth-buttons">
            <a href="#" id="login-btn">Войти</a>
            <a href="#" id="register-btn">Регистрация</a>
            <span class="cart-icon" id="cart-btn"><i class="fas fa-shopping-cart"></i></span>
            <div class="header">
            <select id="language-selector">
                <option value="kz">Қазақ</option>
                <option value="ru">Русский</option>
                <option value="en">English</option>
            </select>
            </div>
            <div class="user-info" id="userInfo">
                <div class="user-icon-container" id="userIcon"><i class="fas fa-user"></i></div>
                <div class="user-details" id="userDetails">
                    <span class="close-button" onclick="toggleUserDetails()">&times;</span>
                    <h3>Жеке кабинет</h3>
                    <p><strong>Логин:</strong> <span id="userUsername">логин</span></p>
                    <p><strong>Пароль:</strong> <span id="userPassword">пароль</span></p>
                </div>
        </div>
    </div>
</header>
</div>

<div class="products">
    <h2 class="section-title">Новинки</h2>
    <div class="product-grid">
        <!-- Тауар 1 -->
        <div class="product-card">
            <img src="серьги.jpeg" alt="syrga">
            <h3 class="product-name">SYRGA</h3>
            <p class="price">2990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 2 -->
        <div class="product-card">
            <img src="серьги2.jpeg" alt="SYRGA2">
            <h3 class="product-name">SYRGA2</h3>
            <p class="price">3490₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 3 -->
        <div class="product-card">
            <img src="серьги3.jpeg" alt="SYRGA3">
            <h3 class="product-name">SYRGA3</h3>
            <p class="price">2590₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 4 -->
        <div class="product-card">
            <img src="серьги4.jpeg" alt="SYRGA4">
            <h3 class="product-name">SYRGA4</h3>
            <p class="price">3990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 5 -->
        <div class="product-card">
            <img src="тақия.jpeg" alt="TAQIA">
            <h3 class="product-name">TAQIA</h3>
            <p class="price">4990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 6 -->
        <div class="product-card">
            <img src="диадема2.jpeg" alt="DIADEMA">
            <h3 class="product-name">Diadema</h3>
            <p class="price">5990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 6 -->
        <div class="product-card">
            <img src="диадема3.jpeg" alt="DIADEMA2">
            <h3 class="product-name">Diadema</h3>
            <p class="price">6990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 7 -->
        <div class="product-card">
            <img src="диадема4.jpeg" alt="DIADEMA3">
            <h3 class="product-name">DIADEMA3</h3>
            <p class="price">5990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 8 -->
        <div class="product-card">
            <img src="цепочки.jpeg" alt="Alqa">
            <h3 class="product-name">Alqa</h3>
            <p class="price">4990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 9 -->
        <div class="product-card">
            <img src="цепочки1.jpeg" alt="Alqa1">
            <h3 class="product-name">Alqa1</h3>
            <p class="price">5990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 10 -->
        <div class="product-card">
            <img src="цепочки2.jpeg" alt="Alqa2">
            <h3 class="product-name">Alqa2</h3>
            <p class="price">4490₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 11-->
        <div class="product-card">
            <img src="цепочки3.jpeg" alt="Alqa3">
            <h3 class="product-name">Alqa3</h3>
            <p class="price">5690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 12-->
        <div class="product-card">
            <img src="браслет.jpeg" alt="Blezik">
            <h3 class="product-name">Blezik</h3>
            <p class="price">3290₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 12-->
        <div class="product-card">
            <img src="браслет1.jpeg" alt="Blezik1">
            <h3 class="product-name">Blezik1</h3>
            <p class="price">3490₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 13-->
        <div class="product-card">
            <img src="браслет2.jpeg" alt="Blezik2">
            <h3 class="product-name">Blezik2</h3>
            <p class="price">4290₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 14-->
        <div class="product-card">
            <img src="браслет3.jpeg" alt="Blezik3">
            <h3 class="product-name">Blezik3</h3>
            <p class="price">3690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 15-->
        <div class="product-card">
            <img src="чокер.jpeg" alt="Мonshaq">
            <h3 class="product-name">Monshaq</h3>
            <p class="price">2690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 16-->
        <div class="product-card">
            <img src="чокер1.jpeg" alt="Monshaq1">
            <h3 class="product-name">Monshaq1</h3>
            <p class="price">3290₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 17-->
        <div class="product-card">
            <img src="чокер2.jpeg" alt="Monshaq2">
            <h3 class="product-name">Monshaq2</h3>
            <p class="price">3590₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 18-->
        <div class="product-card">
            <img src="чокер3.jpeg" alt="Monshaq3">
            <h3 class="product-name">Monshaq3</h3>
            <p class="price">3990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 19-->
        <div class="product-card">
            <img src="чокер4.jpeg" alt="Мonshaq4">
            <h3 class="product-name">Monshaq4</h3>
            <p class="price">2990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 20-->
        <div class="product-card">
            <img src="чокер5.jpeg" alt="Monshaq5">
            <h3 class="product-name">Monshaq5</h3>
            <p class="price">4290₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 21-->
        <div class="product-card">
            <img src="чокер6.jpeg" alt="Monshaq6">
            <h3 class="product-name">Monshaq6</h3>
            <p class="price">3990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 22-->
        <div class="product-card">
            <img src="чокер7.jpeg" alt="Monshaq7">
            <h3 class="product-name">Monshaq7</h3>
            <p class="price">3690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 23-->
        <div class="product-card">
            <img src="пояс.jpeg" alt="Shekelik">
            <h3 class="product-name">Shekelik</h3>
            <p class="price">4590₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 24-->
        <div class="product-card">
            <img src="пояс1.jpeg" alt="Beldik1">
            <h3 class="product-name">Beldik1</h3>
            <p class="price">7990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 25-->
        <div class="product-card">
            <img src="пояс2.jpeg" alt="Beldik2">
            <h3 class="product-name">Beldik2</h3>
            <p class="price">7590₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 26-->
        <div class="product-card">
            <img src="пояс3.jpeg" alt="Beldik3">
            <h3 class="product-name">Beldik3</h3>
            <p class="price">8590₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 27-->
        <div class="product-card">
            <img src="этнокомплект .jpeg" alt="Alqa+bilezik">
            <h3 class="product-name">Alqa+blezik</h3>
            <p class="price">9990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 28-->
        <div class="product-card">
            <img src="шолпы.jpeg" alt="Sholpy">
            <h3 class="product-name">Sholpy</h3>
            <p class="price">1690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 29-->
        <div class="product-card">
            <img src="өңіржиек.jpeg" alt="Onirzhiek">
            <h3 class="product-name">Onirzhiek</h3>
            <p class="price">4690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 30-->
        <div class="product-card">
            <img src="заколка.jpeg" alt="Qystyrgysh">
            <h3 class="product-name">Qystyrgysh</h3>
            <p class="price">3690₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 31-->
        <div class="product-card">
            <img src="алқа.jpeg" alt="Tumar">
            <h3 class="product-name">Alqa</h3>
            <p class="price">3490₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 32-->
        <div class="product-card">
            <img src="алқа1.jpeg" alt="Tumar1">
            <h3 class="product-name">Alqaa</h3>
            <p class="price">3790₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 33-->
        <div class="product-card">
            <img src="сырға .jpeg" alt="Syrga">
            <h3 class="product-name">Syrga</h3>
            <p class="price">1990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 34-->
        <div class="product-card">
            <img src="шашбау.jpeg" alt="Shashbau">
            <h3 class="product-name">Shashbau</h3>
            <p class="price">3990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 35-->
        <div class="product-card">
            <img src="диа1.jpeg" alt="Sarna diadema">
            <h3 class="product-name">Sarna diadema</h3>
            <p class="price">4590₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 36-->
        <div class="product-card">
            <img src="диа.jpeg" alt="Diadema">
            <h3 class="product-name">Diadema</h3>
            <p class="price">5990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 37-->
        <div class="product-card">
            <img src="диадем.jpeg" alt="Marua diademma">
            <h3 class="product-name">Marua diademma</h3>
            <p class="price">4990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
        <!-- Тауар 38-->
        <div class="product-card">
            <img src="d.jpeg" alt="Aisha diadema">
            <h3 class="product-name">Aisha diadema</h3>
            <p class="price">5990₸</p>
            <input type="number" class="quantity-input" value="1" min="1">
            <button class="add-to-cart-btn">В корзину</button>
        </div>
    </div>
</div>
</div>
<!-- Кіру модалы -->
<div class="modal" id="login-modal">
    <div class="modal-content">
        <h2>Войти</h2>
        <input type="email" id="login-email" placeholder="Электронная почта" required>
        <input type="password" id="login-password" placeholder="Пароль" required>
        <button id="login-submit">Войти</button>
        <button id="close-login-modal">закрыть</button>
    </div>
</div>
<!-- Тіркелу модалы -->
<div class="modal" id="register-modal">
    <div class="modal-content">
        <h2>Тіркелу</h2>
        <input type="text" id="register-name" placeholder="Аты-жөні" required>
        <input type="email" id="register-email" placeholder="Электрондық пошта" required>
        <input type="password" id="register-password" placeholder="Пароль" required>
        <button id="register-submit">Тіркелу</button>
        <button id="close-register-modal">Жабу</button>
    </div>
</div>

<!-- Корзина модалы -->
<div class="modal" id="cart-modal">
    <div class="modal-content">
        <h2>Корзина</h2>
        <div id="cart-items"></div>
        <div class="cart-total">Общие: <span id="cart-total">0₸</span></div>
        <button id="checkout-btn" class="checkout-btn">Оплата заказа</button>
        <button id="history-btn">История заказов</button>
        <button id="close-cart-modal">закрыть</button>
    </div>
</div>

<!-- Төлем модалы -->
<div class="payment-modal" id="payment-modal">
    <div class="modal-content">
        <h2>Оплата заказа</h2>
        <div class="payment-form">
            <p>общая сумма: <span id="total-amount">0₸</span></p>
            <input type="text" id="card-number" placeholder="номер карты" required>
            <input type="text" id="card-expiry" placeholder="срок (ММ/ЖЖ)" required>
            <input type="text" id="card-cvv" placeholder="CVV" required>
            <button id="pay-btn">Оплатить</button>
        </div>
        <div class="payment-message" style="display:none;">Оплата прошла успешно!</div>
        <button id="close-payment-modal">закрыть</button>
    </div>
</div>

<!-- Тарих модалы -->
<div class="modal" id="history-modal">
    <div class="modal-content">
        <h2>История заказов</h2>
        <div id="order-history"></div>
        <button id="close-history-modal">закрыть</button>
    </div>
</div>

<footer>
    <p>© 2024 Asylstore</p>
    <div class="social-links">
        <a href="https://wa.me/77075797157" target="_blank"><i class="fab fa-whatsapp"></i></a>
        <a href="https://www.instagram.com/asyyl_zatt" target="_blank"><i class="fab fa-instagram"></i></a>
    </div>    
    
</footer>

<script>
    
    const loginBtn = document.getElementById('login-btn');
    const registerBtn = document.getElementById('register-btn');
    const closeLoginModal = document.getElementById('close-login-modal');
    const closeRegisterModal = document.getElementById('close-register-modal');
    const loginModal = document.getElementById('login-modal');
    const registerModal = document.getElementById('register-modal');

    const cartBtn = document.getElementById('cart-btn');
    const cartModal = document.getElementById('cart-modal');
    const closeCartModal = document.getElementById('close-cart-modal');
    const checkoutBtn = document.getElementById('checkout-btn');
    const historyBtn = document.getElementById('history-btn');
    const historyModal = document.getElementById('history-modal');
    const closeHistoryModal = document.getElementById('close-history-modal');
    const paymentModal = document.getElementById('payment-modal');
    const closePaymentModal = document.getElementById('close-payment-modal');
    const payBtn = document.getElementById('pay-btn');
    const paymentMessage = document.querySelector('.payment-message');
    const totalAmount = document.getElementById('total-amount');

    let cart = [];
    let total = 0;
    let orderHistory = [];

    // Тілдер
    const languages = {
        kz: {
            login: "Кіру",
            register: "Тіркелу",
            cart: "Себет",
            checkout: "Тапсырыс беруді аяқтау",
            history: "Тарих",
            close: "жабу",
            total: "Жалпы:",
            paymentSuccess: "Төлем сәтті өтті!",
            orderHistory: "Тауарлар"
        },
        ru: {
            login: "Войти",
            register: "Регистрация",
            cart: "Корзина",
            checkout: "Оплата заказа",
            history: "История заказов",
            close: "закрыть",
            total: "Общие:",
            paymentSuccess: "Оплата прошла успешно!",
            orderHistory: "Товары"
        },
        en: {
            login: "Login",
            register: "Register",
            cart: "Cart",
            checkout: "Checkout",
            history: "Order History",
            close: "close",
            total: "Total:",
            paymentSuccess: "Payment successful!",
            orderHistory: "Merchandise"
        }
    };

    const languageSelector = document.getElementById('language-selector');
    languageSelector.addEventListener('change', function() {
        updateLanguage(this.value);
    });

    function updateLanguage(lang) {
        const texts = languages[lang];
        document.getElementById('login-btn').innerText = texts.login;
        document.getElementById('register-btn').innerText = texts.register;
        document.getElementById('checkout-btn').innerText = texts.checkout;
        document.getElementById('history-btn').innerText = texts.history;
        closeLoginModal.innerText = texts.close;
        closeRegisterModal.innerText = texts.close;
        closeCartModal.innerText = texts.close;
        closePaymentModal.innerText = texts.close;
        closeHistoryModal.innerText = texts.close;

        document.querySelector('.section-title').innerText = texts.orderHistory;
        document.querySelector('.cart-total').innerText = texts.total;
        paymentMessage.innerText = texts.paymentSuccess;
        document.getElementById('total-amount').innerText = texts.total + ' 0₸'; // default
    }

    // Кіру модалы ашу
    loginBtn.onclick = function() {
        loginModal.style.display = 'block';
    }

    // Тіркелу модалы ашу
    registerBtn.onclick = function() {
        registerModal.style.display = 'block';
    }

    // Кіру модалын жабу
    closeLoginModal.onclick = function() {
        loginModal.style.display = 'none';
    }

    // Тіркелу модалын жабу
    closeRegisterModal.onclick = function() {
        registerModal.style.display = 'none';
    }

    // Корзина модалы ашу
    cartBtn.onclick = function() {
        cartModal.style.display = 'block';
        updateCart();
    }

    // Корзина модалын жабу
    closeCartModal.onclick = function() {
        cartModal.style.display = 'none';
    }

    // Тарих модалы ашу
    historyBtn.onclick = function() {
        historyModal.style.display = 'block';
        updateOrderHistory();
    }

    // Тарих модалын жабу
    closeHistoryModal.onclick = function() {
        historyModal.style.display = 'none';
    }

    // Тапсырыс беруді аяқтау
    checkoutBtn.onclick = function() {
        totalAmount.innerText = total + '₸'; // Жалпы соманы көрсету
        paymentModal.style.display = 'block';
    }

    // Төлем модалын жабу
    closePaymentModal.onclick = function() {
        paymentModal.style.display = 'none';
        paymentMessage.style.display = 'none'; // Жасыру хабарламасы
    }

    // Тауарды корзинаға қосу
    document.querySelectorAll('.add-to-cart-btn').forEach(button => {
        button.onclick = function() {
            const productCard = this.parentElement;
            const productName = productCard.querySelector('.product-name').innerText;
            const productPrice = parseInt(productCard.querySelector('.price').innerText);
            const quantity = parseInt(productCard.querySelector('.quantity-input').value);

            cart.push({ name: productName, price: productPrice, quantity: quantity });
            total += productPrice * quantity;

            updateCart();
        }
    });

    function updateCart() {
        const cartItemsDiv = document.getElementById('cart-items');
        cartItemsDiv.innerHTML = '';

        cart.forEach((item, index) => {
            cartItemsDiv.innerHTML += `<div>${item.name} - ${item.price}₸ x ${item.quantity} <span class="remove-item" onclick="removeItem(${index})">[x]</span></div>`;
        });

        document.getElementById('cart-total').innerText = total + '₸';
    }

    function removeItem(index) {
        total -= cart[index].price * cart[index].quantity;
        cart.splice(index, 1);
        updateCart();
    }
     // Кіру және тіркелу сәтті болғанда негізгі бетке ауысу
     document.getElementById('login-submit').onclick = function() {
        // Мұнда аутентификация логикасын қосу керек
        window.location.href = "index.html"; // Негізгі бет
    }

    document.getElementById('register-submit').onclick = function() {
        // Мұнда тіркелу логикасын қосу керек
        window.location.href = "index.html"; // Негізгі бет
    }
    // Төлем жасау
    payBtn.onclick = function() {
        paymentMessage.style.display = 'block';
        cart = []; // Корзинаны тазалау
        total = 0; // Жалпы соманы нөлдеу
        updateCart();
        setTimeout(() => {
            closePaymentModal.click(); // Төлем соңында модалды жабу
        }, 2000);
    }

    // Тарихты жаңарту
    function updateOrderHistory() {
        const orderHistoryDiv = document.getElementById('order-history');
        orderHistoryDiv.innerHTML = '';

        if (orderHistory.length === 0) {
            orderHistoryDiv.innerHTML = 'Тарих бос'; // Қазақша
        } else {
            orderHistory.forEach(order => {
                orderHistoryDiv.innerHTML += `<div>${order}</div>`;
            });
        }
    }

    // Тапсырыс тарихына қосу
    function addToOrderHistory(order) {
        orderHistory.push(order);
    }
    
    // Орындалған тапсырысты қосу
    payBtn.onclick = function() {
        const order = `Тапсырыс: ${cart.map(item => `${item.name} - ${item.price}₸ x ${item.quantity}`).join(', ')}`;
        addToOrderHistory(order);
        paymentMessage.style.display = 'block';
        cart = [];
        total = 0;
        updateCart();
        setTimeout(() => {
            closePaymentModal.click();
        }, 2000);
    }
    // Кіру және тіркелу сәтті болғанда негізгі бетке ауысу
    document.getElementById('login-submit').onclick = function() {
        // Мұнда аутентификация логикасын қосу керек
        window.location.href = "asylstore.html"; // Негізгі бет
    }

    document.getElementById('register-submit').onclick = function() {
        // Мұнда тіркелу логикасын қосу керек
        window.location.href = "asylstore.html"; // Негізгі бет
    }
    // Бастапқы тіл - қазақ
    updateLanguage('kz');
    
</script>
</body>
</html>





