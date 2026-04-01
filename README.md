
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DAKTRA — Оптовая торговля техническими тканями</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --graphite: #2F2F2F;
            --blue: #0046FF;
            --white: #FFFFFF;
            --light-bg: #F8F9FA;
        }

        * { box-sizing: border-box; }
        body { font-family: 'Inter', 'Segoe UI', sans-serif; margin: 0; color: var(--graphite); line-height: 1.6; background-color: var(--white); }

        /* ВЕРХНЯЯ ПАНЕЛЬ */
        .top-bar {
            background: var(--graphite);
            color: white;
            padding: 10px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
        }
        .top-bar a { color: white; text-decoration: none; margin-left: 15px; opacity: 0.8; transition: 0.3s; }
        .top-bar a:hover { opacity: 1; color: var(--blue); }

        /* ШАПКА */
        .main-header {
            background: white;
            padding: 15px 5%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 15px rgba(0,0,0,0.05);
        }
        .logo img { height: 50px; width: auto; display: block; }
        
        .nav-menu { display: flex; gap: 25px; }
        .nav-menu a { text-decoration: none; color: var(--graphite); font-weight: 600; font-size: 14px; text-transform: uppercase; letter-spacing: 0.5px; }
        .nav-menu a:hover { color: var(--blue); }

        .search-box { flex-grow: 0.5; display: flex; border: 1px solid #ddd; border-radius: 4px; overflow: hidden; }
        .search-box input { border: none; padding: 8px 12px; width: 100%; outline: none; }
        .search-box button { background: var(--blue); color: white; border: none; padding: 0 15px; cursor: pointer; }

        /* ГЕРОЙ-СЕКЦИЯ */
        .hero {
            background: linear-gradient(rgba(47, 47, 47, 0.7), rgba(47, 47, 47, 0.7)), url('IMG_2010.jpeg');
            background-size: cover;
            background-position: center;
            height: 400px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
        }
        .hero-content h1 { font-size: 42px; margin-bottom: 10px; }
        .hero-content p { font-size: 18px; margin-bottom: 25px; opacity: 0.9; }
        .btn-primary { background: var(--blue); color: white; padding: 12px 30px; text-decoration: none; border-radius: 4px; font-weight: bold; transition: 0.3s; }
        .btn-primary:hover { background: #0036CC; box-shadow: 0 4px 15px rgba(0,70,255,0.3); }

        /* ТОВАРЫ */
        .section-container { padding: 60px 5%; }
        .section-title { font-size: 24px; border-left: 5px solid var(--blue); padding-left: 15px; margin-bottom: 30px; text-transform: uppercase; }
        
        .product-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
        .product-card { border: 1px solid #eee; padding: 20px; transition: 0.3s; position: relative; }
        .product-card:hover { border-color: var(--blue); box-shadow: 0 10px 20px rgba(0,0,0,0.05); }
        .product-card img { width: 100%; height: 220px; object-fit: cover; margin-bottom: 15px; }
        .price-tag { color: var(--blue); font-size: 22px; font-weight: 800; margin-bottom: 5px; }
        .product-name { font-weight: bold; font-size: 16px; min-height: 45px; }

        /* КАЛЬКУЛЯТОР */
        .calc-section { background: var(--light-bg); padding: 60px 5%; }
        .calc-card { background: var(--white); padding: 40px; border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); width: 100%; max-width: 500px; margin: 0 auto; }
        .calc-card h2 { color: var(--graphite); border-left: 4px solid var(--blue); padding-left: 15px; font-size: 22px; margin-top: 0; margin-bottom: 25px; }
        .input-group { margin-bottom: 15px; }
        .input-group label { display: block; margin-bottom: 5px; font-size: 14px; color: #666; font-weight: 600; }
        .input-group input, .input-group select { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 6px; font-size: 16px; }
        .calc-btn { width: 100%; padding: 15px; background: var(--blue); color: white; border: none; border-radius: 6px; cursor: pointer; font-weight: bold; font-size: 16px; transition: 0.3s; margin-top: 10px; }
        .calc-btn:hover { background: #0036CC; }
        .result-box { margin-top: 25px; padding: 20px; background: #f0f4ff; border-radius: 6px; display: none; text-align: center; border: 1px solid #d0deff; }
        .result-val { font-size: 32px; color: var(--blue); font-weight: 900; }

        /* НОВОСТИ */
        .news-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        .news-card { background: white; border: 1px solid #eee; overflow: hidden; transition: 0.3s; }
        .news-card img { width: 100%; height: 200px; object-fit: cover; }
        .news-body { padding: 20px; }
        .news-date { font-size: 12px; color: #999; margin-bottom: 10px; }
        .news-body h4 { margin: 0 0 10px 0; color: var(--graphite); }
        .read-more { color: var(--blue); text-decoration: none; font-weight: bold; font-size: 14px; }

        /* ФУТЕР */
        footer { background: var(--graphite); color: white; padding: 60px 5% 20px; display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 40px; }
        footer h4 { border-bottom: 1px solid #444; padding-bottom: 10px; margin-bottom: 20px; }
        footer ul { list-style: none; padding: 0; }
        footer ul li { margin-bottom: 10px; font-size: 14px; opacity: 0.8; }
        .copyright { grid-column: 1 / -1; text-align: center; padding-top: 40px; border-top: 1px solid #444; font-size: 12px; opacity: 0.5; }

        @media (max-width: 768px) {
            .nav-menu { display: none; }
            .hero-content h1 { font-size: 28px; }
        }
    </style>
</head>
<body>

<div class="top-bar">
    <div><i class="fa fa-map-marker-alt"></i> Минск, Республика Беларусь</div>
    <div>
        <span><i class="fa fa-phone"></i> +375 44 506 34 72</span>
        <a href="#"><i class="fab fa-whatsapp"></i> WhatsApp</a>
        <a href="#"><i class="fa fa-envelope"></i> daktra_a.s@mail.ru</a>
    </div>
</div>

<header class="main-header">
    <a href="/" class="logo">
        <img src="IMG_8608.jpeg" alt="DAKTRA LOGO">
    </a>
    
    <nav class="nav-menu">
        <a href="#">Каталог</a>
        <a href="#">О компании</a>
        <a href="#">Доставка</a>
        <a href="#">Опт</a>
        <a href="#">Контакты</a>
    </nav>

    <div class="search-box">
        <input type="text" placeholder="Поиск по артикулу...">
        <button><i class="fa fa-search"></i></button>
    </div>
</header>

<section class="hero">
    <div class="hero-content">
        <h1>ТКАНИ ДЛЯ ВАШЕГО ПРОИЗВОДСТВА</h1>
        <p>Прямые поставки из Китая, Турции и России</p>
        <a href="#calculator" class="btn-primary">Рассчитать заказ</a>
    </div>
</section>

<section class="section-container">
    <h2 class="section-title">Хиты продаж</h2>
    <div class="product-grid">
        <div class="product-card">
            <img src="IMG_2010.jpeg" alt="Oxford Red">
            <div class="price-tag">14.90 BYN</div>
            <div class="product-name">Оксфорд 600D PU1000 (Красный)</div>
            <p style="font-size: 13px; color: #777;">Ткань для тентов и рюкзаков</p>
            <button style="width:100%; padding:10px; background:var(--graphite); color:white; border:none; cursor:pointer;">В корзину</button>
        </div>
    </div>
</section>

<section class="calc-section" id="calculator">
    <div class="calc-card">
        <h2>Производственный калькулятор</h2>
        
        <div class="input-group">
            <label>Количество изделий (шт)</label>
            <input type="number" id="quantity" placeholder="Например: 1000" oninput="calculate()">
        </div>
        
        <div class="input-group">
            <label>Расход на 1 изделие (метры)</label>
            <input type="number" id="consumption" step="0.1" placeholder="Например: 2.5" oninput="calculate()">
        </div>
        
        <div class="input-group">
            <label>Ширина рулона (см)</label>
            <select id="width">
                <option value="150">150 см</option>
                <option value="180">180 см</option>
                <option value="220">220 см</option>
            </select>
        </div>

        <div class="input-group">
            <label>Средний % отходов (выпады)</label>
            <input type="number" id="waste" value="7" oninput="calculate()">
        </div>

        <button class="calc-btn" onclick="calculate()">Рассчитать метраж для закупа</button>

        <div class="result-box" id="resultBlock">
            <span style="font-size: 14px; color: #555; text-transform: uppercase; letter-spacing: 1px;">Необходимый объем закупки:</span><br>
            <span class="result-val" id="totalMeters">0</span> <span class="result-val">м.п.</span>
            <p id="rollsInfo" style="font-size: 14px; color: #666; margin-top: 10px; font-weight: 600;"></p>
        </div>
    </div>
</section>

<section class="section-container">
    <h2 class="section-title">Новости и статьи</h2>
    <div class="news-grid">
        <div class="news-card">
            <img src="IMG_8743.webp" alt="Скидки">
            <div class="news-body">
                <div class="news-date">26 марта 2026</div>
                <h4>Обновление сетки скидок от объема</h4>
                <p style="font-size: 14px; color: #666;">Узнайте о новых условиях для крупных оптовых партий...</p>
                <a href="#" class="read-more">Подробнее →</a>
            </div>
        </div>
        <div class="news-card">
            <img src="IMG_8807.jpeg" alt="Спецодежда">
            <div class="news-body">
                <div class="news-date">20 марта 2026</div>
                <h4>Как выбрать ткань для спецодежды?</h4>
                <p style="font-size: 14px; color: #666;">Гайд по плотности, пропиткам и износостойкости материалов...</p>
                <a href="#" class="read-more">Подробнее →</a>
            </div>
        </div>
    </div>
</section>

<footer>
    <div>
        <h4>ООО «ДАКТРА»</h4>
        <ul>
            <li>Прямые поставки тканей</li>
            <li>Работа с госзаказами</li>
            <li>Склады в Минске</li>
        </ul>
    </div>
    <div>
        <h4>Разделы</h4>
        <ul>
            <li><a href="#" style="color:white; text-decoration:none;">Каталог</a></li>
            <li><a href="#" style="color:white; text-decoration:none;">Оптовый прайс</a></li>
            <li><a href="#" style="color:white; text-decoration:none;">Сертификаты</a></li>
        </ul>
    </div>
    <div>
        <h4>Контакты</h4>
        <ul>
            <li>+375 44 506 34 72</li>
            <li>пн-пт: 9:00 — 18:00</li>
            <li>Минск, складской комплекс</li>
        </ul>
    </div>
    <div class="copyright">
        © 2026 ООО «Дактра». Прототип B2B-портала для дипломного проекта.
    </div>
</footer>

<script>
    function calculate() {
        const qty = parseFloat(document.getElementById('quantity').value);
        const cons = parseFloat(document.getElementById('consumption').value);
        const waste = parseFloat(document.getElementById('waste').value);
        const rollLength = 50; 

        if(qty > 0 && cons > 0) {
            let total = (qty * cons) * (1 + (waste / 100));
            total = Math.ceil(total); 
            
            const rolls = Math.ceil(total / rollLength);

            document.getElementById('totalMeters').innerText = total;
            document.getElementById('rollsInfo').innerText = `Итого: ~${rolls} рулонов (при намотке 50м).`;
            document.getElementById('resultBlock').style.display = 'block';
        }
    }
</script>

</body>
</html>
