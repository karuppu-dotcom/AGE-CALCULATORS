DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Age Calculator</title>
<style>
  body {
    font-family: 'Segoe UI', Arial, sans-serif;
    background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0;
    padding: 20px;
  }
  .card {
    background: #fff;
    border-radius: 16px;
    padding: 32px 28px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.25);
    max-width: 360px;
    width: 100%;
  }
  h1 {
    text-align: center;
    font-size: 22px;
    margin-bottom: 24px;
    color: #2575fc;
  }
  label {
    display: block;
    font-size: 13px;
    font-weight: 600;
    color: #555;
    margin-bottom: 6px;
    margin-top: 16px;
  }
  input[type="date"] {
    width: 100%;
    padding: 10px 12px;
    border: 2px solid #e0e0e0;
    border-radius: 8px;
    font-size: 15px;
    box-sizing: border-box;
  }
  input[type="date"]:focus {
    outline: none;
    border-color: #2575fc;
  }
  button {
    width: 100%;
    margin-top: 22px;
    padding: 12px;
    background: #2575fc;
    color: #fff;
    border: none;
    border-radius: 8px;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.2s;
  }
  button:hover {
    background: #1a5fd6;
  }
  .result {
    margin-top: 20px;
    padding: 16px;
    background: #f5f7ff;
    border-radius: 8px;
    text-align: center;
    font-size: 18px;
    font-weight: 700;
    color: #333;
    min-height: 20px;
  }
  .note {
    margin-top: 12px;
    font-size: 12px;
    color: #999;
    text-align: center;
  }
</style>
</head>
<body>

<div class="card">
  <h1>📅 Age Calculator</h1>

  <label for="date1">First Date</label>
  <input type="date" id="date1">

  <label for="date2">Second Date</label>
  <input type="date" id="date2">

  <button onclick="calculateDifference()">Calculate</button>

  <div class="result" id="result">—</div>
  <div class="note">Result shown as years.months</div>
</div>

<script>
  function calculateDifference() {
    const d1 = document.getElementById('date1').value;
    const d2 = document.getElementById('date2').value;
    const resultEl = document.getElementById('result');

    if (!d1 || !d2) {
      resultEl.textContent = "Please pick both dates";
      return;
    }

    const date1 = new Date(d1);
    const date2 = new Date(d2);

    // Matches the original MIT App Inventor block logic:
    // simple Year - Year and Month - Month subtraction, no borrowing.
    const yearDiff = date2.getFullYear() - date1.getFullYear();
    const monthDiff = (date2.getMonth() + 1) - (date1.getMonth() + 1);

    resultEl.textContent = `${yearDiff}.${monthDiff}`;
  }
</script>

</body>
</html>
