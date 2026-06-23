# -dhikr--counter
<!DOCTYPE html>
<html>
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dhikr Counter</title>
  <style>
    body {
      font-family: Arial;
      text-align: center;
      margin-top: 80px;
      background: #f6f6f6;
    }

    .count {
      font-size: 80px;
      margin: 30px 0;
    }

    button {
      font-size: 40px;
      padding: 30px 60px;
      border: none;
      border-radius: 20px;
      background: #2e7d32;
      color: white;
      width: 80%;
      max-width: 400px;
    }

    .reset {
      margin-top: 20px;
      font-size: 18px;
      background: #b71c1c;
    }
  </style>
</head>
<body>

  <h1>Dhikr Counter</h1>
  <div class="count" id="count">0</div>

  <button onclick="add()">Tap for Dhikr</button>
  <br>
  <button class="reset" onclick="reset()">Reset</button>

  <script>
    let count = 0;

    function add() {
      count++;
      document.getElementById("count").innerText = count;
      localStorage.setItem("dhikrCount", count);
    }

    function reset() {
      count = 0;
      document.getElementById("count").innerText = count;
      localStorage.setItem("dhikrCount", count);
    }

    window.onload = function() {
      let saved = localStorage.getItem("dhikrCount");
      if (saved !== null) {
        count = parseInt(saved);
        document.getElementById("count").innerText = count;
      }
    }
  </script>

</body>
</html>
