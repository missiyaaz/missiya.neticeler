# missiya.neticeler
<html lang="az">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Missiya İmtahan Nəticəsi Sistemi</title>

    <style>
        /* --- Ümumi Stillər --- */
        body {
            font-family: Tahoma, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }

        /* --- Giriş Forması Stilləri --- */
        #input-page {
            /* Səhifəni tam mərkəzləşdirmək üçün */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
        }

        #input-page h1 {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 20px;
            color: #333;
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

        /* --- Nəticə Şəkli Stilləri --- */
        #result-page {
            display: none; /* Başlanğıcda gizlidir */
            width: 100%;
            text-align: center;
        }

        /* Şəklin düzgün görünüşü üçün stillər */
        #result-page img {
            max-width: 100%; /* Şəklin brauzer pəncərəsindən böyük olmasının qarşısını alır */
            height: auto;
            display: block; 
            margin: 0 auto; /* Şəkli üfüqi olaraq mərkəzləşdirir */
        }
    </style>
</head>
<body>

    <div id="input-page">
        <div class="input-container">
            <h1>İş nömrəsi</h1>
            <input type="text" id="jobNumberInput" placeholder="bura daxil edin" required>
            <button type="button" class="blue-button" onclick="checkJobNumber()">Nəticəni göstər</button>
        </div>
    </div>

    <div id="result-page">
        <img src="netice-sekli.jpg" alt="İmtahan Nəticə Vərəqəsi Şəkli">
    </div>

    <script>
        function checkJobNumber() {
            const inputNumber = document.getElementById('jobNumberInput').value.trim();
            const inputPage = document.getElementById('input-page');
            const resultPage = document.getElementById('result-page');

            // Yalnız "54979" daxil edilərsə nəticə səhifəsi açılır.
            if (inputNumber === '54979') {
                // Giriş səhifəsini gizlədir
                inputPage.style.display = 'none';
                // Nəticə səhifəsini (şəkli) göstərir
                resultPage.style.display = 'block';
                // Səhifənin yuxarısına kaydırır
                window.scrollTo(0, 0); 

            } else {
                // Səhv nömrə daxil edilərsə yeni xəta mesajı
                alert('Nəticə tapılmadı.');
            }
        }
    </script>
</body>
</html>
