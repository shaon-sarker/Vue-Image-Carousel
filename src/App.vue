<script setup>
import {ref,reactive} from "vue"
const images = reactive([
    {
        picture: "/img1.jpg",
    },
    {
        picture: "/img2.jpg",
    },
    {
        picture: "/img3.jpg",
    }
])

const i = ref(0)
const currentPhoto = ref(images[0].picture)

function nextButton() {
    if(i.value !== images.length-1) {
        i.value = i.value+1
    }
    currentPhoto.value = images[i.value].picture
}
function prevButton() {
    if(i.value > 0) {
        i.value = i.value-1
    }
    currentPhoto.value = images[i.value].picture
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <h2>Image Carousel Using Vue js 03</h2>
                <div id="carouselExample" class="carousel slide">
                  <div class="carousel-inner">
                    <div class="carousel-item active">
                      <img :src="currentPhoto" class="d-block w-100" alt="...">
                    </div>
                  </div>
                  <button class="carousel-control-prev" type="button">
                    <span @click="prevButton()" class="carousel-control-prev-icon" aria-hidden="true"></span>
                  </button>
                  <button class="carousel-control-next" type="button">
                    <span @click="nextButton()" class="carousel-control-next-icon" aria-hidden="true"></span>
                  </button>
                </div>
            </div>
        </div>
    </div>
</template>