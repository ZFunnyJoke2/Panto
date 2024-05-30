<script>
export default {
  name: 'TheFooter',
  data(){
    return{

    }
  }
}
</script>

<template>
  <div class="footer">
    <div class="footer-info">
      <div class="panto">
        <h2>Panto</h2>
        <p>The advantage of hiring a workspace with<br>
          us is that gives you comfortable service<br>
          and all-around facilities.</p>
      </div>
      <div class="block-of-lists">
        <ul class="list">
          <li><span class="orange">Services</span></li>
          <li><a href="#">Marketing</a></li>
          <li><a href="#">Campaigns</a></li>
          <li><a href="#">Branding</a></li>
        </ul>
        <ul class="list">
          <li><span class="orange">Furniture</span></li>
          <li><a href="#">Beds</a></li>
          <li><a href="#">Chair</a></li>
          <li><a href="#">Sofa</a></li>
        </ul>
        <ul class="list">
          <li><span class="orange">Follow Us</span></li>
          <li><img src="@/assets/img/001-facebook.png" alt="Facebook"><a href="#">Facebook</a></li>
          <li><img src="@/assets/img/003-twitter.png" alt="Twitter"><a href="#">Twitter</a></li>
          <li><img src="@/assets/img/004-instagram.png" alt="Instagram"><a href="#">Instagram</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <p>Copyright ©2024</p>
      <a href="#">Privacy Policy</a>
    </div>
  </div>
</template>

<style>
.footer{
  height: 450px;
  margin-top: 10rem;
  background: #F7F7F7;
}
.footer-info{
  display: flex;
  margin-top: 120px;
}
.block-of-lists{
  display: flex;
  margin-top: 10rem;
}
.orange{
  color: darkorange;
}
.list{
  list-style: none;
  padding-right: 110px;
}
.list img{
  padding-right: 10px;
}
.list li{
  margin-bottom: 15px;
}
.list li a{
  text-decoration: none;
  color: #1E1E1E;
  font-size: 18px;
}
.panto{
  padding-left: 180px;
  padding-top: 10rem;
  padding-right: 10rem;
}
.panto h2{
  font-size: 28px;
}
.panto p{
  font-size: 18px;
}
.footer-bottom{
  display: flex;
  justify-content: space-between;
  max-width: 1300px;
  padding-left: 180px;
  padding-top: 30px;
}
.footer-bottom a{
  text-decoration: none;
  color: #1E1E1E;
  font-size: 18px;
}

</style>