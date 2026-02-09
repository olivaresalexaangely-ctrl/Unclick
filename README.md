<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Unclick</title>

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
  cursor: pointer;
  overflow: hidden;
}

.container {
  text-align: center;
  width: 100%;
  max-width: 500px;
}

img {
  width: 100%;
  max-height: 300px;
  object-fit: contain;
  border-radius: 16px;
  margin-bottom: 10px;
  display: none;
}

/* 💗 corazones */
.heart {
  position: fixed;
  font-size: 24px;
  animation: floatUp 1.5s ease-out forwards;
  pointer-events: none;
}

@keyframes floatUp {
  0% {
    transform: translate(-50%, 0) scale(1);
    opacity: 1;
  }
  100% {
    transform: translate(-50%, -150%) scale(1.5);
    opacity: 0;
  }
}
</style>
</head>

<body>

<div class="container">
  <img id="img1" src="Foto1.png">
  <img id="img2" src="Foto2.jpg">
  <img id="img3" src="Foto3.png">
  <img id="img4" src="Foto4.png">
  <img id="img5" src="Foto5.png">
  <img id="img6" src="Foto6.png">
  <img id="img7" src="Foto7.png">
  <img id="img8" src="Foto8.png">
</div>

<script>
let step = 0;
const images = ["img1","img2","img3","img4","img5","img6","img7","img8"];

document.body.addEventListener("click", () => {

  // mostrar imagen en orden
  if(step < images.length){
    document.getElementById(images[step]).style.display = "block";
  }

  // corazones
  for(let i=0;i<8;i++){
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💗";
    heart.style.left = Math.random()*100 + "vw";
    heart.style.top = "100vh";
    document.body.appendChild(heart);

    setTimeout(()=>heart.remove(),1500);
  }

  step++;
});
</script>

</body>
</html>

