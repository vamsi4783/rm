[index.html](https://github.com/user-attachments/files/32961925/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>RetailManager</title>
  <style>
    body{font-family:system-ui,sans-serif;display:flex;flex-direction:column;
         align-items:center;justify-content:center;min-height:100vh;margin:0;
         background:#fff;color:#333;text-align:center;padding:1rem}
    h2{margin-bottom:.5rem}
    p{color:#666;font-size:.9rem}
    a{display:inline-block;margin-top:1.5rem;padding:.75rem 2rem;
      background:#1976D2;color:#fff;border-radius:8px;text-decoration:none;
      font-size:1rem;font-weight:600}
  </style>
</head>
<body>
  <h2>RetailManager</h2>
  <p>Opening activation screen…</p>
  <a id="btn" href="#">Open RetailManager</a>
  <script>
    var token = new URLSearchParams(window.location.search).get("token") || "";
    if (/^[0-9a-f]{64}$/i.test(token)) {
      var deep = "retailmanager://staff-invite?token=" + token;
      document.getElementById("btn").href = deep;
      window.location.replace(deep);
    } else {
      document.querySelector("p").textContent = "Invalid or expired invitation link.";
      document.getElementById("btn").style.display = "none";
    }
  </script>
</body>
</html>
