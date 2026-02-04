<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>unclick+</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      background: #0049F7;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: Tahoma, sans-serif;
      color: #FFA6E7;
      cursor: pointer;
      padding: 20px;
    }

    .container {
      text-align: center;
      width: 100%;
      max-width: 500px;
      padding: 24px;
      border-radius: 20px;
      backdrop-filter: blur(10px);
    }

    img {
      width: 100%;
      max-height: 300px;
      object-fit: cover;
      border-radius: 16px;
      margin-bottom: 18px;
      display: none;
    }

    h1 {
      font-size: 1.4rem;
      line-height: 1.4;
      margin: 0;
    }
  </style>
</head>

<body onclick="nextStep()">
  <div class="container">
    <img id="vibeImage" />
    <h1 id="phrase">Feliz 14 de febrero, linda 👩🏻‍❤️‍👩🏻</h1>
  </div>

  <script>
    // 🔹 FRASES (NO LAS CAMBIÉ)
    const phrases = [
      "Feliz 14 de febrero, linda 👩🏻‍❤️‍👩🏻",
      "A person like you is the most special thing to me.",
      "Between the same days, I get happier every time I meet you.",
      "Even though we're far apart now, our hearts are the same. Even without you by my side, yes, even without me by your side."
    ];

    // 🔹 IMÁGENES (tus links de Drive ya convertidos)
    const images = [
      "https://drive.google.com/uc?export=view&id=1Ua7Pah8a6mRCoUJ1GuZ2sYPLpqWUcDUV",
      "https://drive.google.com/uc?export=view&id=1I7igPxyRtjwdthF6Ts5l3SXEXnUG2RSs",
      "https://drive.google.com/uc?export=view&id=1vWvi1pf61cH2KMnNTH8VGlh79H5Qx3Le",
      "https://drive.google.com/uc?export=view&id=1h1R8_2O03gCoBLFVHmarCO8j6tIbotv5"
    ];

    const phraseEl = document.getElementById("phrase");
    const imageEl = document.getElementById("vibeImage");

    let index = 0;
    let showingText = true;

    function nextStep() {
      // si ya llegó al final, no hace nada
      if (index >= phrases.length - 1 && !showingText) return;

      if (showingText) {
        // mostrar imagen
        imageEl.src = images[index]()
