<!doctype html>

<html lang="uk">

<head>

  <meta charset="utf-8" />

  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <title>Чайові — Підтримати Даню</title>

  <style>

    :root{--bg:#f6f7fb;--card:#ffffff;--accent:#0b6b3a;--muted:#6b7280}

    \*{box-sizing:border-box}

    body{margin:0;font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; background:var(--bg); color:#0f1724}

    .wrap{max-width:420px;margin:0 auto;padding:22px}

    header{display:flex;gap:12px;align-items:center}

    .avatar{

      width:80px;  /\* збільшено ширину \*/

      height:80px; /\* збільшено висоту \*/

      border-radius:14px;

      background:linear-gradient(135deg,#a8f0c2,#4caf50);

      display:flex;align-items:center;justify-content:center;

      color:white;font-weight:700;font-size:28px; /\* збільшено шрифт \*/

      user-select:none;

    }

    h1{font-size:20px;margin:0}

    p.lead{margin:6px 0 18px;color:var(--muted)}



    .card{background:var(--card);border-radius:14px;padding:16px;box-shadow:0 6px 18px rgba(12,15,22,0.06);margin-bottom:18px}

    .presets{display:flex;gap:8px;flex-wrap:wrap}

    .preset{flex:1 1 30%;min-width:90px;padding:12px;border-radius:10px;border:1px solid #e6eef0;background:transparent;text-align:center;font-weight:600}

    .preset:hover{transform:translateY(-2px);cursor:pointer}



    .amount-row{display:flex;gap:8px;margin-top:12px}

    input\[type=number]{flex:1;padding:12px;border-radius:10px;border:1px solid #e6eef0;font-size:16px}

    .btn{padding:12px 14px;border-radius:10px;border:none;background:var(--accent);color:white;font-weight:700;cursor:pointer}



    .note{font-size:13px;color:var(--muted);margin-top:12px}

    footer{margin-top:18px;text-align:center;font-size:13px;color:var(--muted)}



    @media (max-width:420px){.wrap{padding:16px}}

  </style>

</head>

<body>

  <div class="wrap">

    <header>

      <div class="avatar">Даня</div>

      <div>

        <h1>Підтримайте Даню</h1>

        <p class="lead">Відправте чайові</p>

      </div>

    </header>



    <div class="card">

      <div style="font-weight:700">Виберіть суму</div>

      <div class="presets">

        <button class="preset" onclick="sendTip(20)">20 ₴</button>

        <button class="preset" onclick="sendTip(50)">50 ₴</button>

        <button class="preset" onclick="sendTip(100)">100 ₴</button>

        <button class="preset" onclick="sendTip(200)">200 ₴</button>

      </div>

      <div class="amount-row">

        <input id="custom" type="number" min="1" placeholder="Введіть суму">

        <button class="btn" onclick="sendCustomTip()">Відправити</button>

      </div>

      <div class="note">Ви можете оплатити зручним способом: Monobank, Приват24, або інший банк.</div>

    </div>



    <div class="card" style="text-align:center">

      <div style="font-weight:700;margin-bottom:8px">Варіанти оплати</div>

      <button class="btn" style="width:100%;margin-bottom:8px" onclick="openMono()">Через Monobank</button>

      <button class="btn" style="width:100%;margin-bottom:8px;background:#1b5e20" onclick="openPrivat()">Через Приват24</button>

      <button class="btn" style="width:100%;background:#374151" onclick="copyCard()">Скопіювати номер карти</button>

    </div>



    <footer>Безпечна передача даних — не передавайте PIN-коди. Рекомендуємо використовувати Monobank Jar для прямого посилання.</footer>

  </div>



  <script>

    const monoJarUrl = 'https://send.monobank.ua/jar/3JVYDSxTxn';

    const cardNumber = '4441111053843052';



    function sendTip(amount){

      window.location.href = ${monoJarUrl}?amount=${amount};

    }



    function sendCustomTip(){

      let amount = document.getElementById('custom').value;

      if(amount > 0){

        window.location.href = ${monoJarUrl}?amount=${amount};

      } else {

        alert('Введіть суму');

      }

    }



    function openMono(){

      window.open(monoJarUrl, '\_blank');

    }



    function openPrivat(){

      window.open(https://next.privat24.ua/money-transfer/card?lang=uk, '\_blank');

    }



    **function copyCard(){**

&nbsp;     \*\*navigator.clipboard.writeText(cardNumber).then(()=>{\*\*

        \*\*alert('Номер карти скопійовано: ' + cardNumber);\*\*

      \*\*}).catch(()=>{\*\*

        \*\*prompt('Скопіюйте вручну:', cardNumber);\*\*

      \*\*});\*\*

    \*\*}\*\*


**</script>**

**</body>**

**</html>**

