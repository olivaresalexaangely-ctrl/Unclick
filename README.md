<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Unclick</title>

<style>
body {
  margin: 0;
  background: #0049F7;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  overflow: hidden;
}

img {
  width: 90%;
  max-width: 400px;
  max-height: 80vh;
  object-fit: contain;
  border-radius: 20px;
  display: none;
}

/* corazones */
.heart {
  position: fixed;
  font-size: 24px;
  animation: float 1.5s ease-out forwards;
  pointer-events: none;
}

@keyframes float {
  from { transform: translateY(0); opacity:1; }
  to { transform: translateY(-200px); opacity:0; }
}
</style>
</head>

<body>

<img id="photo">

<script>
const images = [
 "Foto1.png",
 "Foto2.jpg",
 "Foto3.png",
 "Foto4.png",
 "Foto5.png",
 "Foto6.png",
 "Foto7.png",
 "Foto8.png"
];

let index = 0;
const img = document.getElementById("photo");

document.body.addEventListener("click", () => {

  // mostrar UNA imagen
  img.style.display = "block";
  img.src = images[index];
  index = (index + 1) % images.length;

  // corazones
  for(let i=0;i<6;i++){
    let heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💗";
    heart.style.left = Math.random()*100 + "vw";
    heart.style.top = "100vh";
    document.body.appendChild(heart);
    setTimeout(()=>heart.remove(),1500);
  }
});
</script>

</body>
</html>

