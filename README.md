# Вывод изображений и текстовое поле
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tam Ekran Resim</title>
    <style>
        /* CSS kodu: Resmin tüm ekranı kaplamasını sağlar */
        body, html {
            /* Varsayılan tarayıcı boşluklarını kaldırır */
            margin: 0;
            padding: 0;
            /* Yüksekliğin %100 olmasını sağlar */
            height: 100%;
            /* Taşmaları gizler (scroll çubuklarını önler) */
            overflow: hidden;
        }

        #tam-ekran-resim {
            /* Resmin kaplayacağı alanı belirler */
            width: 100%;
            height: 100%;
            /* Resim URL'sini burada belirtin */
            background-image: url('netice-sekli.jpg');
            /* Resmin en boy oranını koruyarak alanı doldurmasını sağlar */
            background-size: cover;
            /* Resmi ortalar */
            background-position: center;
            /* Arka plan resminin tekrarlanmamasını sağlar */
            background-repeat: no-repeat;
        }
    </style>
</head>
<body>

    <div id="tam-ekran-resim"></div>

</body>
</html>
