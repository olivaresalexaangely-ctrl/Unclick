<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Love</title>

<style>
body{
  margin:0;
  background:#000;
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
  overflow:hidden;
}

img{
  width:90%;
  max-height:85vh;
  object-fit:cover;
  border-radius:20px;
}

/* CORAZONES */
.heart{
  position:fixed;
  font-size:24px;
  animation:float 1.8s ease-out forwards;
  pointer-events:none;
}

@keyframes float{
  from{opacity:1; transform:translateY(0);}
  to{opacity:0; transform:translateY(-200px) scale(1.5);}
}
</style>
</head>

<body onclick="nextImage();heart();">

<img id="photo">

<script>
const images = [
"https://drive.google.com/uc?export=view&id=1MYwgdZh6vQWJ3t3cbM4MAO6dQ57m4vAR",
"https://drive.google.com/uc?export=view&id=1mj_AdYuJuZQLfgsvYXE9djJnvF979I1h",
"https://drive.google.com/uc?export=view&id=1xICsIg4OOwqv-BkKeedLP-FQXz-aJEEH",
"https://drive.google.com/uc?export=view&id=1Nk5QE8TNqdQS1mF7GkZB0r26FY0t_-cd",
"https://drive.google.com/uc?export=view&id=1UwSt8Al8vivSDsh3_ayC8cen00iwuvZq",
"https://drive.google.com/uc?export=view&id=1DQdaNzBA1nCL4HMPUmjJyQx0HPxM-Rng",
"https://drive.google.com/uc?export=view&id=1OvD-10DmoJJEczDVsGTD0koEnOZMOQ6r",
"https://drive.google.com/uc?export=view&id=1dql8_CDd-I2Angh5fXJ4xTk3Z0Bp-hgF"
];

let i = 0;
const img = document.getElementById("photo");

// mostrar primera imagen
img.src = images[0];

function nextImage(){
  i++;
  if(i >= images.length) i = 0;
  img.src = images[i];
}

// corazones
function heart(){
  const h = document.createElement("div");
  h.className="heart";
  h.innerHTML="💗";
  h.style.left = Math.random()*100 + "vw";
  h.style.top = "80vh";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),1800);
}
</script>

</body>
</html>

