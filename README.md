<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>WARUNG DIGITAL - Pendaftaran</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      padding: 20px;
    }
    .container {
      max-width: 500px;
      margin: 0 auto;
      background: #fff;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    h2 {
      text-align: center;
    }
    input[type="text"], input[type="email"], input[type="password"], input[type="tel"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ddd;
    }
    button {
      width: 100%;
      padding: 10px;
      background-color: #28a745;
      color: white;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: #218838;
    }
  </style>
</head>
<body>

  <div class="container">
    <h2>Pendaftaran WARUNG DIGITAL</h2>
    <form id="registrationForm">
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required>

      <label for="phone">Nomor Telepon:</label>
      <input type="tel" id="phone" name="phone" required>

      <label for="password">Kata Sandi:</label>
      <input type="password" id="password" name="password" required>

      <button type="submit">Daftar</button>
    </form>
    <p id="message"></p>
  </div>

  <script>
    document.getElementById('registrationForm').addEventListener('submit', function(e) {
      e.preventDefault();

      const email = document.getElementById('email').value;
      const phone = document.getElementById('phone').value;
      const password = document.getElementById('password').value;

      fetch('https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec', {
        method: 'POST',
        body: JSON.stringify({ email: email, phone: phone, password: password }),
        headers: {
          'Content-Type': 'application/json'
        }
      })
      .then(response => response.text())
      .then(data => {
        document.getElementById('message').innerText = "Pendaftaran berhasil!";
      })
      .catch(error => {
        document.getElementById('message').innerText = "Gagal mendaftar, coba lagi!";
      });
    });
  </script>

</body>
</html>
