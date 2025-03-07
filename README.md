
<!DOCTYPE html>
<html lang="en">
  <head>
   <meta charset="utf-8">
   <meta name="viewport" content="width=device-width, initial-scale=1">
   <script src="https://kit.fontawesome.com/1147679ae7.js" crossorigin="anonymous"></script>
   <link rel="stylesheet" href="css/pages.css">
   <title>IVY project</title>
  </head>
  <body>
    <header>
    <div class="logo">
      <img src="https://pubcdn.ivymoda.com/ivy2/images/logo.png">
    </div>
    <div class="menu">
      <li><a href="./cartegory.html"> NỮ</a> 
        <ul class="sub-menu">
          <li><a href="">Hàng mới về  </a></li>
          <li><a href="">Collection</a></li>
          <li><a href="" class="bold-text">Áo</a></li>
            <ul>
              <li><a href="">Áo sơ mi</a></li>
              <li><a href="">Áo thun</a></li>
              <li><a href="">Áo vest</a></li>
              <li><a href="">Áo Khoác</a></li>
              <li><a href="">Áo len</a></li>
            </ul>
          </li>
          <li><a href="">Quần</a></li>
            <ul>
              <li><a href="">Quần jean</a></li>
              <li><a href="">Quần lửng</a></li>
              <li><a href="">Quần dài</a></li>
            </ul>
          </li>
        </ul>
      </li>
      <li><a href="">NAM</a></li>
      <ul class="sub-menu">
        <li><a href="">Hàng mới về</a></li>
        <li><a href="">Collection</a></li>
        <li><a href="" class="bold-text">Áo</a></li>
        <ul>
          <li><a href="">Áo sơ mi</a></li>
          <li><a href="">Áo thun</a></li>
          <li><a href="">Áo len</a></li>
          <li><a href="">Áo Khoác</a></li>
          <li><a href="">Áo polo</a></li>
          <li><a href="">Áo Sweater/Hoodie</a></li>
          </ul>
        </li>
        <li><a href="">Quần</a>
        <ul>
          <li><a href="">Quần jean</a></li>
          <li><a href="">Quần dài</a></li>
          <li><a href="">Quần kaki</a></li>
          <li><a href="">Quần short</a></li>
        </ul>
      </li>
      </ul>
    </li>
      <li><a href="">TRẺ EM</a> </li>
      <li><a href="">SALE</a></li>
      <li><a href="">BỘ SƯU TẬP</a> </li>
      <li><a href="">THÔNG TIN</a></li>
     
    </div>
    <div class="others">
      <li><input placeholder="Tìm kiếm" type="text"> <i class="fas fa-search"></i></li>
        <li><a class="fa fa-paw" href=""></a></li>
        <li><a class="fa fa-user" href=""></a></li>
        <li><a class="fa fa-shopping-bag" href=""></a></li>
    </div>
  </header>
  <!-- --------------------------slide------------------------- -->
  <section id="slider">
    <div class="aspect-ratio-169">
      <img src="../img/slide1.png">
      <img src="../img/slide2.webp">
    </div>

  </section>
  <section class="app-container">
    <p>Ứng dụng IVY moda</p>
    <p>Download App</p>
    <div class="app-google">
      <img src="../img/googleplay.png">
      <img src="../img/appstore.png">

    </div>
    <p>Nhập các thông tin</p>
    <input type="text" placeholder="Nhập email của bạn">

  </section>
  <!------------------------ footer ------------------------------>
  <div class="footer-top">
    <li><a href="" alt=""><img src="../img/img-congthuong.png"></a></li>
    <li><a href="" alt="">Liên hệ </a></li>
    <li><a href="" alt="">Tuyển dụng</a></li>
    <li><a href="" alt="">Giới thiệu</a></li>
    <li> 
      <a href="" class="fab fa-facebook-f" ></a>
      <a href="" class="fab fa-youtuber-y" ><img src="../img/ic_ytb.svg"> </a>
      <a href="" class="fab fa-pinterset-p" ><img src="../img/ic_pinterest.svg"> </a>
    </li>

  </div>
  <div class="footer-center">
  Công ty Cổ phần IVYmoda với số đăng kí kinh doanh:123456<br>
  Địa chỉ:số 43 Trần Duy Hưng - Cầu Giấy - Hà Nội<br>Đặt hàng hottline:
  <span>19001001</span></div>
  <div class="footer-bottom">©IVYmoda All rights reserved</div>
  
  </body>
  <!----------------------------------- script------------------------------ -->
  <script>
    const header = document.querySelector("header")
  window.addEventListener("scroll", function() {
    x = window.pageYOffset
    if(x>0) {
      header.classList.add("sticky")
    } else {
      header.classList.remove("sticky")
    }
  }
)
    const imgPosition = document.querySelectorAll('.aspect-ratio-169 img');
    const imgContainer = document.querySelector('.aspect-ratio-169');
    const dots = document.querySelectorAll('.dot');
    let imgNumber = imgPosition.length;
    let currentIndex = 0;

    imgPosition.forEach((img, index) => {
      img.style.left = index * 100 + '%';
    });

    function showSlide(index) {
      if (index >= imgNumber) {
        currentIndex = 0;
      } else if (index < 0) {
        currentIndex = imgNumber - 1;
      } else {
        currentIndex = index;
      }
      const offset = -currentIndex * 100;
      imgContainer.style.transform = `translateX(${offset}%)`;
      updateDots();
    }

    function nextSlide() {
      showSlide(currentIndex + 1);
    }

    function prevSlide() 
    {
      showSlide(currentIndex - 1);
    }

    function updateDots() {
      dots.forEach((dot, index) => {
        dot.classList.remove('active');
        if (index === currentIndex) {
          dot.classList.add('active');
        }
      });
    }

    dots.forEach((dot, index) => {
      dot.addEventListener('click', () => {
        showSlide(index);
      });
    });

    setInterval(nextSlide, 3000); // Tự động chuyển slide sau mỗi 3 giây
    showSlide(currentIndex); // Hiển thị slide đầu tiên khi tải trang
    
  </script>
</body>
</html>
