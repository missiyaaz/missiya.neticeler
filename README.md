# Вывод изображений и текстовое поле
<html lang="az">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Missiya İmtahan Nəticəsi Sistemi</title>

    <style>
        /* --- Ümumi Stillər --- */
        body {
            font-family: Tahoma, sans-serif;
            background-color: #ffffff;
            margin: 0;
            padding: 0;
        }

        /* --- Giriş Forması Stilləri --- */
        #input-page {
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

        /* --- Nəticə Vərəqəsi Stilləri --- */
        #result-page {
            display: none; /* Başlanğıcda gizli saxlayırıq */
            padding: 20px;
        }

        .page-container {
            width: 900px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        /* Başlıq və Loqo */
        .header-section {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 20px;
        }

        .result-title-box {
            background-color: #f0f0f0;
            padding: 8px;
            font-size: 16px;
            font-weight: bold;
            text-align: center;
            border: 1px solid #ccc;
            width: 50%;
        }

        .logo-box {
            text-align: center;
            font-weight: bold;
            line-height: 1.1;
        }

        .logo-box p {
            margin: 0;
            font-size: 14px;
        }

        /* Şagird Məlumat Cədvəli */
        .info-table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }

        .info-table td {
            border: 1px solid #000;
            padding: 5px 10px;
            font-size: 12px;
        }

        .info-table .label {
            background-color: #f0f0f0;
            font-weight: bold;
            width: 15%;
        }

        /* Fənn Hissəsi */
        .subject-box {
            margin-bottom: 20px;
            border: 1px solid #ccc;
            padding: 5px;
        }

        .subject-name {
            background-color: #f0f0f0;
            padding: 5px;
            font-weight: bold;
            font-size: 14px;
            margin-bottom: 5px;
            border-bottom: 1px solid #ccc;
        }

        /* Bal Cədvəli (Sual/Cavab) */
        .score-table {
            width: 100%;
            border-collapse: collapse;
            text-align: center;
            font-size: 10px;
            margin-bottom: 5px;
        }

        .score-table td {
            border: 1px solid #ccc;
            padding: 3px;
            white-space: nowrap;
        }

        .score-table thead td {
            background-color: #e0e0e0;
            font-weight: bold;
        }

        .score-table .correct {
            color: green;
            font-weight: bold;
        }

        .score-table .wrong {
            color: red;
            font-weight: bold;
        }

        /* Fənnin Ümumi Göstəriciləri Cədvəli */
        .summary-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 12px;
        }

        .summary-table td {
            border: 1px solid #000;
            padding: 5px;
            font-weight: bold;
            text-align: center;
        }

        .summary-table .highlight-value {
            background-color: #f0f0f0;
        }

        /* Yeni şəkil stilləri */
        .result-image-container {
            text-align: center; /* Şəkli mərkəzə gətirir */
            margin-top: 15px;
            margin-bottom: 15px;
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
        <div class="page-container">
            
            <div class="header-section">
                <div class="result-title-box">
                    İMTAHAN NƏTİCƏ VƏRƏQƏSİ
                </div>
                <div class="logo-box">
                    <img src="https://example.com/missiya_logo.png" alt="Missiya Təhsil Şirkəti Loqosu" style="max-width: 80px;">
                    <p>MİSSİYA</p>
                    <p>TƏHSİL ŞİRKƏTİ</p>
                </div>
            </div>

            <table class="info-table">
                <tr><td class="label">İmtahan Bloku</td><td class="value"></td><td class="label">Adı</td><td class="value"></td></tr>
                <tr><td class="label">Keçirilmə tarixi</td><td class="value"></td><td class="label">Soyadı</td><td class="value"></td></tr>
                <tr><td class="label">İş nömrəsi</td><td class="value"></td><td class="label">Sinif</td><td class="value"></td></tr>
                <tr><td class="label">Bölmə</td><td class="value"></td><td class="label">Variant</td><td class="value"></td></tr>
                <tr><td class="label">Blok</td><td class="value"></td><td class="label">Bal</td><td class="value"></td></tr>
                <tr><td class="label">Faiz</td><td class="value"></td><td class="label">Doğru</td><td class="value"></td></tr>
                <tr><td class="label">Yanlış</td><td class="value"></td><td class="label">Cavabsız</td><td class="value"></td></tr>
            </table>

            <div class="result-image-container">
                <img src="Uğurlu_Nəticə.png" alt="Təbrik Şəkli" style="max-width: 250px; height: auto; border: 3px solid #007aff; border-radius: 10px;">
                <p style="font-size: 16px; font-weight: bold; color: #007aff; margin-top: 10px;">Təbrik edirik!</p>
            </div>
            
            <div class="subject-box">
                <div class="subject-name">Biologiya (1-30)</div>
                <table class="summary-table">
                    <tr><td>Bal</td><td class="highlight-value"></td><td>Faiz</td><td class="highlight-value"></td><td>Doğru</td><td class="highlight-value"></td><td>Yanlış</td><td class="highlight-value"></td><td>Cavabsız</td><td class="highlight-value"></td></tr>
                </table>
            </div>
            
            <div class="subject-box">
                <div class="subject-name">Kimya (31-60)</div>
                <table class="summary-table">
                    <tr><td>Bal</td><td class="highlight-value"></td><td>Faiz</td><td class="highlight-value"></td><td>Doğru</td><td class="highlight-value"></td><td>Yanlış</td><td class="highlight-value"></td><td>Cavabsız</td><td class="highlight-value"></td></tr>
                </table>
            </div>

            <div class="subject-box">
                <div class="subject-name">Fizika (61-90)</div>
                <table class="summary-table">
                    <tr><td>Bal</td><td class="highlight-value"></td><td>Faiz</td><td class="highlight-value"></td><td>Doğru</td><td class="highlight-value"></td><td>Yanlış</td><td class="highlight-value"></td><td>Cavabsız</td><td class="highlight-value"></td></tr>
                </table>
            </div>

        </div>
    </div>

    <script>
        function checkJobNumber() {
            const inputNumber = document.getElementById('jobNumberInput').value.trim();
            const inputPage = document.getElementById('input-page');
            const resultPage = document.getElementById('result-page');

            // JavaScript yalnız 54979 nömrəsini qəbul edir
            if (inputNumber === '54979') {
                // Giriş səhifəsini gizlədir, nəticəni göstərir
                inputPage.style.display = 'none';
                resultPage.style.display = 'block';
                window.scrollTo(0, 0); 

            } else {
                // Başqa nömrə daxil edilərsə xəta mesajı
                alert('iş nömrəsi tapılmadı.');
            }
        }
    </script>
</body>
</html>
