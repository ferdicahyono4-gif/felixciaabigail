# felixciaabigail
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Forex Dashboard Live</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- TailwindCSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- TradingView Widget -->
  <script type="text/javascript" src="https://s3.tradingview.com/tv.js"></script>
</head>
<body class="bg-slate-100 text-slate-800">

<!-- Header -->
<header class="bg-slate-800 text-white p-4 shadow">
  <h1 class="text-2xl font-bold text-center">💱 Forex Dashboard Live</h1>
</header>

<!-- Bagian 1: Chart Major Pair -->
<section class="p-4">
  <h2 class="text-xl font-semibold mb-2">📈 Chart EUR/USD</h2>
  <div class="tradingview-widget-container h-96">
    <div id="tv-chart"></div>
  </div>
</section>

<!-- Bagian 2: Quotes Streaming -->
<section class="p-4">
  <h2 class="text-xl font-semibold mb-2">💹 Live Quotes</h2>
  <div class="tradingview-widget-container">
    <div class="tradingview-widget-container__widget"></div>
    <script type="text/javascript" src="https://s3.tradingview.com/external-embedding/embed-widget-forex-cross-rates.js" async>
    {
      "width": "100%",
      "height": 400,
      "currencies": ["EUR", "USD", "GBP", "JPY", "CHF", "AUD", "CAD", "NZD", "CNY"],
      "isTransparent": true,
      "colorTheme": "light",
      "locale": "id"
    }
    </script>
  </div>
</section>

<!-- Bagian 3: Currency Converter -->
<section class="p-4">
  <h2 class="text-xl font-semibold mb-2">🔄 Konverter Mata Uang</h2>
  <div class="tradingview-widget-container">
    <div class="tradingview-widget-container__widget"></div>
    <script type="text/javascript" src="https://s3.tradingview.com/external-embedding/embed-widget-forex-calculator.js" async>
    {
      "width": "100%",
      "height": 300,
      "symbol": "FX_IDC:EURUSD",
      "isTransparent": true,
      "colorTheme": "light",
      "locale": "id"
    }
    </script>
  </div>
</section>

<!-- Bagian 4: Berita Forex -->
<section class="p-4">
  <h2 class="text-xl font-semibold mb-2">📰 Berita Forex</h2>
  <div class="tradingview-widget-container">
    <div class="tradingview-widget-container__widget"></div>
    <script type="text/javascript" src="https://s3.tradingview.com/external-embedding/embed-widget-timeline.js" async>
    {
      "feedMode": "market",
      "market": "forex",
      "height": 400,
      "colorTheme": "light",
      "isTransparent": true,
      "displayMode": "regular",
      "width": "100%",
      "locale": "id"
    }
    </script>
  </div>
</section>

<!-- Bagian 5: Mini Forum (via Disqus) -->
<section class="p-4">
  <h2 class="text-xl font-semibold mb-2">💬 Diskusi</h2>
  <div id="disqus_thread"></div>
  <script>
    (function() {
      var d = document, s = d.createElement('script');
      s.src = 'https://forex-dashboard-live.disqus.com/embed.js';
      s.setAttribute('data-timestamp', +new Date());
      (d.head || d.body).appendChild(s);
    })();
  </script>
</section>

<!-- Footer -->
<footer class="bg-slate-200 text-center p-4 text-sm text-slate-600">
  Dibuat dengan ❤️ oleh Anda | Data real-time © TradingView
</footer>

<!-- Inisialisasi Chart EUR/USD -->
<script type="text/javascript">
  new TradingView.widget({
    container_id: "tv-chart",
    symbol: "FX_IDC:EURUSD",
    interval: "15",
    timezone: "Asia/Jakarta",
    theme: "light",
    style: "1",
    locale: "id",
    toolbar_bg: "#f1f3f6",
    enable_publishing: false,
    allow_symbol_change: true,
    hide_side_toolbar: false,
    width: "100%",
    height: "100%"
  });
</script>

</body>
</html>
