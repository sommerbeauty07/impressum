<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Impressum</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
      line-height: 1.6;
      background-color: #f9f9f9;
      color: #333;
      max-width: 800px;
      margin: 2rem auto;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 10px;
    }
    h1 {
      text-align: center;
    }
  </style>
</head>
<body>
  <h1>Impressum</h1>
  <div id="impressum">Lade Impressum...</div>

  <script>
    const fileUrl = "https://drive.google.com/uc?export=download&id=1m4j16plg_pG0QmzVXaH6du28I78kREpQ";

    fetch(fileUrl)
      .then(response => response.text())
      .then(html => {
        const parser = new DOMParser();
        const doc = parser.parseFromString(html, "text/html");
        const text = doc.body.innerText;
        document.getElementById("impressum").innerText = text;
      })
      .catch(err => {
        document.getElementById("impressum").innerText = "Fehler beim Laden des Impressums.";
        console.error(err);
      });
  </script>
</body>
</html>
