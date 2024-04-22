<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Random Color Generator</title>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
<style>
  .card {
      display: inline-block;
      width: 100px;
      height: 150px; /* ปรับความสูงให้เหมาะสมกับขนาดของการ์ด */
      margin: 10px;
      background-size: contain;
      background-position: center;
      background-repeat: no-repeat;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  }
  </style>
</head>
<body>
  <header class="p-3 text-bg-dark">
    <div class="container">
      <div class="d-flex flex-wrap align-items-center justify-content-center justify-content-lg-start">
        <a href="/" class="d-flex align-items-center mb-2 mb-lg-0 text-white text-decoration-none">
          <svg class="bi me-2" width="40" height="32" role="img" aria-label="Bootstrap"><use xlink:href="#bootstrap"></use></svg>
        </a>

        <ul class="nav col-12 col-lg-auto me-lg-auto mb-2 justify-content-center mb-md-0">
          <div class="dropdown text-end">
            <a href="#" class="d-block  text-white text-decoration-none dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
              เลือกประเภทกาชา
            </a>
            <ul class="dropdown-menu text-small">
              <li><a class="dropdown-item" href="index.html">อัญเชิญพาหนะแห่งแสงอาทิตย์อัสดง</a></li>
              <li><a class="dropdown-item" href="index2.html">อัญเชิญพาหนะเจิดจริสแห่งใกล้รุ่ง</a></li>
              <li><a class="dropdown-item" href="index3.html">อัญเชิญพาหนะเจิดจ้าแห่งแสงอาทิตย์อัสดง</a></li>
         
            </ul>
          </div>
        </ul>

        <form class="col-12 col-lg-auto mb-3 mb-lg-0 me-lg-3" role="search">
          <input type="search" class="form-control form-control-dark text-bg-dark" placeholder="Search..." aria-label="Search">
        </form>

        <div class="text-end">
          <button type="button" class="btn btn-outline-light me-2">Login</button>
          <button type="button" class="btn btn-warning">Sign-up</button>
        </div>
      </div>
    </div>
  </header>
 

  <div class="container">
    <div>
<h1>อัญเชิญพาหนะเจิดจริสแห่งใกล้รุ่ง</h1>
<button onclick="generateColors()">กดสุ่มตรงนี้</button>
<div id="colorResults"></div>
</div>
<script>
function randomColor(rate) {
    const randNum = Math.random() * 100;
    let cumulativeRate = 0;
    for (const color in rate) {
        cumulativeRate += rate[color];
        if (randNum <= cumulativeRate) {
            return color;
        }
    }
}

function generateColors() {
    const rate = {
        "white": 70.9456990,
        "green": 27.5624824,
        "blue": 1.3229786,
        "purple": 0.1587599,
        "yellow": 0.0100800
    };

    const numOfColors = 11;
    const colorResults = document.getElementById("colorResults");
    colorResults.innerHTML = "";

    for (let i = 0; i < numOfColors; i++) {
        const color = randomColor(rate);
        const colorCard = document.createElement("div");
        colorCard.classList.add("card");
        colorCard.style.backgroundColor = color;
        colorResults.appendChild(colorCard);
    }
}
</script>

</div>
</body>
</html>
