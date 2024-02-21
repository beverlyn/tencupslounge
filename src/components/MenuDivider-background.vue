<script setup lang="ts">
import { ref } from 'vue';
import image1 from "../assets/menu-background/menu-eggspresso-yellow-background.png"
import image2 from "../assets/menu-background/menu-pandan-pink-background.png"
import image3 from "../assets/menu-background/menu-satayofthegods-blue-background.png"
import image4 from "../assets/menu-background/menu-cake-green-background.png"
import image5 from "../assets/menu-background/menu-coffee-yellow-background.png"
import image6 from "../assets/menu-background/menu-wine-pink-background.png"
import image7 from "../assets/menu-background/menu-croissant-blue-background.png"
import image8 from "../assets/menu-background/menu-cocktail-green-background.png"

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

// Explicitly type marqueeRef as a ref to an HTMLDivElement
// const marqueeRef = ref<HTMLDivElement | null>(null);

// onMounted(() => {
//     if (marqueeRef.value) {
//         const totalWidth = images.value.length * 250 * 2; // Total width for duplicated images
//         marqueeRef.value.style.width = `${totalWidth}px`;
//     }
// });
</script>

<template>
    <div class="image-container">
        <div class="marquee">
        <!-- <div class="marquee" ref="marqueeRef"> -->
            <div class="marquee-items">
                <img 
                    v-for="(image, index) in images" 
                    :key="index" 
                    :src="image.src" 
                    :alt="image.alt"
                />
            </div>
            <div class="marquee-items">
                <img 
                    v-for="(image, index) in images" 
                    :key="index" 
                    :src="image.src" 
                    :alt="image.alt"
                />
            </div>
        </div>
    </div>
  </template>
  
<style scoped>
.image-container {
    overflow: hidden;
    white-space: nowrap;
}

img {
    height: auto;
    width: 250px;
    margin: 0;
    padding: 0;
}

.marquee-items {
    width: 2000px;
    display: flex;
    justify-content: start;
    align-items: center;
}

.marquee {
    width: 4000px;
    display: flex;
    animation: marqueeSlide 20s linear infinite;
}

@keyframes marqueeSlide {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
}

@media (max-width: 400px) {
    img {
        width: 150px;
    }
    .marquee-items {
        width: 1200px;
    }

    .marquee {
        width: 2400px;
    }
    
}

</style>