<template>
    <section id="books">
        <h1 id="books-heading">Books</h1>
        <div class="gallery">
            <div class="column">
              <div class="book-photo">
                  <img :src="img1" alt="book-img">
                  <div class="overlay">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                  </div>
              </div>
              <div class="book-photo">
                  <img :src="img2" alt="book-img">
                  <div class="overlay">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                  </div>
              </div>
              <div class="book-photo">
                  <img :src="img3" alt="book-img">
                  <div class="overlay">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                  </div>
              </div>
            </div>

            <div class="column">
                <div class="book-photo">
                    <img :src="img4" alt="book-img">
                    <div class="overlay">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                    </div>
                </div>
                <div class="book-photo">
                    <img :src="img5" alt="book-img">
                    <div class="overlay">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                    </div>
                </div>
                <div class="book-photo">
                    <img :src="img6" alt="book-img">
                    <div class="overlay">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                    </div>
                </div>
            </div>

            <div class="column">
                <div class="book-photo">
                    <img :src="img1" alt="book-img">
                    <div class="overlay">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                    </div>
                </div>
                <div class="book-photo">
                    <img :src="img2" alt="book-img">
                    <div class="overlay">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                    </div>
                </div>
                <div class="book-photo">
                    <img :src="img3" alt="book-img">
                    <div class="overlay">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda repellendus repudiandae, dolorum quam perferendis sapiente.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import img1 from '../assets/images/book-1.jpg';
import img2 from '../assets/images/book-2.webp';
import img3 from '../assets/images/book-3.jpeg';
import img4 from '../assets/images/book-4.jpg';
import img5 from '../assets/images/book-5.jpg';
import img6 from '../assets/images/book-1.jpg';

</script>

<style scoped>
#books-heading {
    font-size: 4.3rem;
}
#books {
    max-width:1224;
    width: 90%;
    margin: auto;
    padding: 40px 0;
}


.gallery {
    display: flex;
    gap: 20px;
}

.column {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.book-photo img {
    width: 100%;
    height: 100%;
    border-radius: 5px;
}

.book-photo {
    position: relative;
}

.book-photo .overlay {
    position: absolute;
    left: 0;
    top: 0;
    z-index: 2;
    background-color: rgba(0, 0, 0, 0.204);
    height: 0%;
    width: 100%;
    transition: height 0.3s;
}

.overlay p {
    display: none;
    transition: display 0.3s;
}

.book-photo:hover .overlay p {
    display: block;
    line-height: 1.5;
    font-size: 1.25rem;
    margin: 0 5%;
}

.book-photo:hover .overlay{
    height: 100%;
    background-color: rgba(0, 0, 0, 0.518);
}

.overlay{
    color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>