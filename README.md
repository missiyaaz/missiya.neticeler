# Вывод изображений и текстовое поле
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nəticə Girişi</title>
    <style>
        /* --- Ümumi Stillər --- */
        body {
            font-family: Tahoma, sans-serif;
            background-color: #ffffff;
            margin: 0;
            padding: 0;
            /* Tam ekran için her zaman 100vh kullanıyoruz */
            height: 100vh;
            overflow: hidden; /* Scroll çubuklarını önlemek için */
        }

        /* --------------------------------- */
        /* --- 1. GİRİŞ FORMU SAYFASI --- */
        /* --------------------------------- */

        #input-page {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            /* Varsayılan olarak gösteriyoruz */
        }

        #input-page h1 {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        #jobNumberInput {
            padding: 10px 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
            width: 250px;
            margin-right: 10px;
        }

        .blue-button {
            background-color: #007aff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .blue-button:hover {
            background-color: #005bb5;
        }

        /* --------------------------------- */
        /* --- 2. TAM EKRAN RESİM SAYFASI --- */
        /* --------------------------------- */

        #result-page {
            /* Başlangıçta gizli tutuyoruz */
            display: none; 
            width: 100%;
            height: 100%;
        }
        
        #tam-ekran-resim {
            /* Önceki tam ekran kodunuzdan alındı */
            width: 100%;
            height: 100%;
            
            /* Sizin verdiğiniz link kullanıldı */
            background-image: url('https://i.ibb.co/4ZkcJZTc/Screenshot-2025-12-07-20-42-55-253-com-miui-gallery.png');
            
            /* Tam ekranı kaplama ayarları */
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }

    </style>
</head>
<body>

    <div id="input-page">
        <div>
            <h1>İmtahan Nömrəsini Daxil Edin</h1>
            <input type="text" id="jobNumberInput" placeholder="Nömrəni yazın...">
            <button class="blue-button" onclick="showResult()">Nəticəni Göstər</button>
        </div>
    </div>

    <div id="result-page">
        <div id="tam-ekran-resim">
            </div>
    </div>

    <script>
        function showResult() {
            // Giriş sayfasını gizle
            document.getElementById('input-page').style.display = 'none';
            
            // Sonuç sayfasını (Tam Ekran Resmi) göster
            document.getElementById('result-page').style.display = 'block';
            
            // Not: Eğer farklı numaralar için farklı resimler göstermek isterseniz,
            // burada 'jobNumberInput' değerini kontrol edip 'tam-ekran-resim' div'inin
            // background-image özelliğini dinamik olarak değiştirmelisiniz.
        }
    </script>

</body>
</html>
