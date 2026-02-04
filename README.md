<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>unclick+</title>

  <style>
    * { box-sizing: border-box; }

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
      overflow: hidden;
    }

    .container {
      text-align: center;
      width: 100%;
      max-width: 500px;
      padding: 24px;
      border-radius: 20px;
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

    /* 💗 CORAZONES */
    .heart {
      position: fixed;
      font-size: 22px;
      animation: floatUp 1.6s ease-out forwards;
      pointer-events: none;
    }

    @keyframes floatUp {
      0% {
        transform: translate(-50%, -50%) scale(1);
        opacity: 1;
      }
      100% {
        transform: translate(-50%, -120%) scale(1.4);
        opacity: 0;
        imageEl.style.display = "block";
        phraseEl.style.display = "none";
      }

      step++;
    }
  </script>
</body>
</html>
