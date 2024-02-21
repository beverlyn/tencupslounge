<script setup lang="ts">
  import { ref } from 'vue';
import image1 from "../assets/menu-drink1.webp";
import image2 from "../assets/menu-drink3.webp";
import image3 from "../assets/menu-breakfast.webp";
import image4 from "../assets/menu-drink4.webp";
import image5 from "../assets/menu-food.webp";
import image6 from "../assets/menu-drinks.webp";
import image7 from "../assets/menu-wine.webp";
import image8 from "../assets/menu-drink2.webp"; 

const images = ref([
    { src: image1, alt: "image 1" },
    { src: image2, alt: "image 2" },
    { src: image3, alt: "image 3" },
    { src: image4, alt: "image 4" },
    { src: image5, alt: "image 5" },
    { src: image6, alt: "image 6" },
    { src: image7, alt: "image 7" },
    { src: image8, alt: "image 8" },
  ]);
</script>

<template>
    <div class="image-container overflow-hidden" ref="container">
      <div class="image-row">
        <img v-for="(image, index) in [...images,...images]" :key="index" :src="image.src" :alt="image.alt"/>
      </div>
    </div>
  </template>
  
  <style scoped>
.image-container {
    overflow-x: hidden;
    white-space: nowrap;
    height: 400px;
}
.image-row {
    display: flex;
    height: 100%;
    animation: scroll 20s linear infinite;
}
.image-container img {
    height: 100%;
    width: 400px;
    display: block;
}

@keyframes scroll {
    from {
        transform: translateX(0%);
    }
    to {
        transform: translateX(-50%);
    }
}

</style>