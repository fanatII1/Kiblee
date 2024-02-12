<template>
  <section id="intro">
    <nav id="main-nav">
      <div class="item-container item-1">
        <RouterLink to="/">Home</RouterLink>
        <div class="animation start-home"></div>
      </div>
      
      <div class="item-container item-2">
        <RouterLink to="/books">Books</RouterLink>
        <div class="animation start-home"></div>
      </div>
      
      <div class="item-container item-3">
        <RouterLink to="/">Contact</RouterLink>
        <div class="animation start-home"></div>
      </div>

      <div class="item-container item-4">
        <RouterLink to="/">Home</RouterLink>
        <div class="animation start-home"></div>
      </div>

      <!-- <div class="animation start-home"></div> -->
    </nav>

    <div class="banner">
      <div class="banner-resizer"></div>
      <img :src="bannerImage" alt="banner image" class="banner-img">

      
      <div class="banner-intro-text">
        <div class="bible-quote">
          <p class="chapter-verse">EFESUS 4:5</p>
          <p class="verse-text">Satu iman, satu <br/> Tuhan, satu <br/> baptisan</p>
          <button id="learn-more">Learn More</button>
        </div>
        <div class="controls">
          1
          2
        </div>
      </div>

      <div class="banner-overlay"></div>
    </div>
  </section>

  <section id="about-us">
    <div class="about-description">
      <p class="about-heading">
        SHARE YOUR <br/>
        TESTIMONY
      </p>
      <p class="about-text">
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptates unde ullam quod iste quo cum. Nemo natus animi ipsa quaerat similique harum odit sint atque, at nulla esse dolor quisquam voluptate veritatis perferendis vero hic.
      </p>
    </div>

    <div class="about-image-wrapper">
      <img :src="aboutImage" alt="sharing the testimony" id="about-description">
    </div>
  </section>

  <section id="Top-books">
    <p id="Books-Heading">Top Books</p>

    <div class="books">
      <div class="book">
        <img :src="bookImg1" alt="book" class="book-img">
        <p class="book-title">Book 1</p>
        <p class="book-description">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Delectus, illum. Reprehenderit aliquid eligendi iusto a.
        </p>
      </div>
      
      <div class="book">
        <img :src="bookImg2" alt="book" class="book-img">
        <p class="book-title">Book 2</p>
        <p class="book-description">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Delectus, illum. Reprehenderit aliquid eligendi iusto a.
        </p>     
      </div>
      
      <div class="book">
        <img :src="bookImg3" alt="book" class="book-img">
        <p class="book-title">Book 3</p>
        <p class="book-description">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Delectus, illum. Reprehenderit aliquid eligendi iusto a.
        </p>      
      </div>
    </div>
  </section>
  
</template>

<script setup>
import bannerImage from '../assets/images/church.jpg';
import aboutImage from '../assets/images/online-bible-study.png';
import bookImg1 from '../assets/images/book-1.jpg';
import bookImg2 from '../assets/images/book-2.webp';
import bookImg3 from '../assets/images/book-3.jpeg';
import { RouterLink, RouterView } from 'vue-router';

import { ref, onMounted, watch } from 'vue';
import { useAuthStore } from '../stores/authentication';
import { auth } from '../../firebase';
import { signOut } from 'firebase/auth';

const authStore = useAuthStore();

//check authentication 
function checkAuth(){
  console.log(authStore.user, authStore.loginState)
  authStore.setLoginState(authStore.user);
}

function logout(){
  signOut(auth)
  .then(() => {
    auth.setLoginState(authStore.user);
    alert('You have logged out')
  })
  .catch((error) => {
    // alert('error logging out' + " " + error.code )
    console.log('error logging out' + " " + error.code)
  })
}
</script>

<style scoped>
#intro {
  height: 95%;
  /* background: url('../assets/images/church.jpg'); */
  position: relative;
}

.banner{
  height: 100%;
  display: flex;
  justify-content: center;
  position: relative;
}

.banner-img{
  display: block;
  height: 100%;
  width: 90%;
}

.banner-resizer{
  width: 10%;
  background-color: black;
}

.banner-overlay{
  position: absolute;
  top: 0;
  left:0;
  width: 100%;
  height: 100%;
  z-index: 2;
  background-color: rgba(0, 0, 0, 0.297);
}

#main-nav {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 70%;
  height: 7%;
  z-index: 4;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  font-weight: 600;
  /* border-bottom: 1px solid #fff; */
}

#main-nav a {
  margin: 0 5%;
  text-decoration: none;
}

.item-container a{
  color:#fff;
}

.start-home {
  height: 2px;
  background-color: #fff;
  width: 0;
}

.item-1 .start-home,
.item-2 .start-home,
.item-3 .start-home,
.item-4 .start-home{
  width: 0;
  transition: width 0.3s;
}

.item-1, .item-2, .item-3, .item-4 {
  width: 10%;
  text-align: center;
}

.item-1:hover .start-home,
.item-2:hover .start-home,
.item-3:hover .start-home,
.item-4:hover .start-home{
  width: 100%;
}

.banner-intro-text {
  position: absolute;
  bottom: 0;
  height: 100%;
  width: 70%;
  z-index: 3;
  display: flex;
  align-items: center;
  /* justify-content: center; */
  color: #fff;
}

.chapter-verse {
  font-size: 2rem;
}

.verse-text {
  font-size: 6rem;
  font-weight: 500;
}

#learn-more {
  height: 55px;
  width: 215px;
  background: transparent;
  border: 1px solid #fff;
  cursor: pointer;
  font-size: 0.95rem;
  font-weight: bold;
  font-family: "Montserrat Alternates", sans-serif;
  color: #fff;
  margin: 3% 0;
  transition: .25s;
}

#learn-more:hover {
  background-color: #ffffff5c;
  font-weight: bold;
  transform: scale(1.05);
  cursor: pointer;
}




#about-us {
  /* height: 100%;
  max-height: 635px; */
  display: flex;
  padding: 0 15%;
  margin: 2%;
}

.about-heading {
  font-size: 4.5rem;
  font-weight: 500;
}

.about-text {
  font-size: 1.1rem;
  line-height: 1.5;
  margin-top: 5%;
  max-width: 625px;
}

.about-image-wrapper {
  width: 755px;
  height: 480px;
  max-height: 500px;
}

.about-image-wrapper img {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

#Top-books {
  margin: 2%;
  padding: 5% 15% 0 15%;
}

#Books-Heading{
  font-size: 4.5rem;
  font-weight: 500;
  margin-bottom: 5%;
}

.books {
  display: flex;
  justify-content: space-between;
}

.book {
  width: 300px;
  height: 460px;
  max-height: 400px;
}

.book-img {
  display: block;
  width: 100%;
  height: 40%;
  object-fit: cover;
  -webkit-box-shadow: -10px 15px 0 3px #98844e;
  -moz-box-shadow: -10px 15px 0 3px #98844e;
  box-shadow: -10px 15px 0 3px #98844e;
}

.book-title {
  margin-top: 20%;
  margin-bottom: 5%;
  font-weight: bold;
}
</style>