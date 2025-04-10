<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>IRL Counter</title>
  <style>
    body {
      background: transparent;
      font-family: Arial, sans-serif;
      color: white;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
    .counter {
      font-size: 2em;
      margin: 10px;
    }
    .buttons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    button {
      margin: 5px;
      padding: 10px 20px;
      font-size: 1em;
      border: none;
      border-radius: 8px;
      background-color: #333;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background-color: #555;
    }
  </style>
</head>
<body>
  <div class="counter" id="drinks">🍻 Drinks: 0</div>
  <div class="counter" id="girls">💃 Girls: 0</div>
  <div class="counter" id="rejects">❌ Rejects: 0</div>
  <div class="counter" id="kisses">💋 Kisses: 0</div>

  <div class="buttons">
    <button onclick="increment('drinks')">+1 Drink</button>
    <button onclick="increment('girls')">+1 Girl</button>
    <button onclick="increment('rejects')">+1 Reject</button>
    <button onclick="increment('kisses')">+1 Kiss</button>
    <button onclick="resetAll()">Reset All</button>
  </div>

  <script>
    const counters = {
      drinks: 0,
      girls: 0,
      rejects: 0,
      kisses: 0
    };

    function increment(type) {
      counters[type]++;
      updateDisplay(type);
    }

    function updateDisplay(type) {
      document.getElementById(type).innerText = `${getIcon(type)} ${capitalize(type)}: ${counters[type]}`;
    }

    function resetAll() {
      for (const key in counters) {
        counters[key] = 0;
        updateDisplay(key);
      }
    }

    function getIcon(type) {
      return {
        drinks: '🍻',
        girls: '💃',
        rejects: '❌',
        kisses: '💋'
      }[type];
    }

    function capitalize(s) {
      return s.charAt(0).toUpperCase() + s.slice(1);
    }
  </script>
</body>
</html>
