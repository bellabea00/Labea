<!DOCTYPE html>
<html lang="ht">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MACHE GRÈSKOKKO</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5dc;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        h1 {
            background: linear-gradient(45deg, #ff9800, #e91e63);
            color: white;
            padding: 15px;
            margin: 0;
            font-size: 28px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: titleGlow 2s infinite alternate;
        }

        @keyframes titleGlow {
            from { text-shadow: 2px 2px 4px rgba(0,0,0,0.3); }
            to { text-shadow: 4px 4px 8px rgba(0,0,0,0.5); }
        }

        .search-box {
            margin: 20px auto;
            padding: 10px;
            width: 50%;
            border: 2px solid #ff9800;
            border-radius: 5px;
            font-size: 18px;
            outline: none;
        }

        .product-container {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            margin: auto;
        }

        .product {
            background: white;
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            animation: slideIn 0.8s ease-in-out;
        }

        .product:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .product img {
            width: 100%;
            height: auto;
            border-radius: 5px;
            cursor: pointer;
        }

        @media screen and (max-width: 1024px) {
            .product-container {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        @media screen and (max-width: 768px) {
            .product-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media screen and (max-width: 480px) {
            .product-container {
                grid-template-columns: repeat(1, 1fr);
            }
        }
    </style>
</head>
<body>

    <h1>MACHE GRÈSKOKKO</h1>

    <input type="text" class="search-box" id="search" placeholder="🔍 Chèche pwodwi...">

    <div class="product-container" id="product-list">
        <div class="product" data-name="Pwa An Poud">
            <a href="https://codepen.io/Koukoul/full/yyLejbW.html?receiver=37919464&product=Pwa%20an%20Poud&price=100" target="_blank">
                <img src="https://i.postimg.cc/9FLmPZgK/Photoroom-20250318-175013.png" alt="Pwa An Poud">
            </a>
            <p>Pwa An Poud</p>
        </div>

        <div class="product" data-name="Poud Doliv">
            <a href="https://codepen.io/Koukoul/full/yyLejbW.html?receiver=37919464&product=Poud%20F%C3%A8y%20Doliv&price=100" target="_blank">
                <img src="https://i.postimg.cc/pV7km6R6/Photoroom-20250318-174952.png" alt="Poud Doliv">
            </a>
            <p>Poud Doliv</p>
        </div>

        <div class="product" data-name="Lòt Ankò">
            <a href="https://postimages.org/" target="_blank">
                <img src="https://i.postimg.cc/vZVw3ff1/moringa-poudre-moringa-oleifera-dans-bol-bois-feuilles-moringa-fraiches-originales-isolees-blanc-100.jpg" alt="Lòt Ankò">
            </a>
            <p>Lòt Ankò</p>
        </div>

        <div class="product" data-name="Zòt">
            <a href="https://postimages.org/" target="_blank">
                <img src="https://i.postimg.cc/PrNjvBqQ/18-farina-di-fagioli-neri.jpg" alt="Zòt">
            </a>
            <p>Zòt</p>
        </div>

        <div class="product" data-name="Trafic">
            <a href="https://postimages.org/" target="_blank">
                <img src="https://i.postimg.cc/Y2V5GyG2/Photoroom-20250221-084946.png" alt="Trafic">
            </a>
            <p>Trafic</p>
        </div>
    </div>

    <script>
        document.getElementById('search').addEventListener('input', function() {
            let filter = this.value.toLowerCase();
            let products = document.querySelectorAll('.product');

            products.forEach(product => {
                let name = product.getAttribute('data-name').toLowerCase();
                if (name.includes(filter)) {
                    product.style.display = 'block';
                } else {
                    product.style.display = 'none';
                }
            });
        });
    </script>

</body>
</html>
