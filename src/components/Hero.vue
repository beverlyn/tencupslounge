<script setup lang="ts">
import { ref, watchEffect } from 'vue';

const opacity = ref(0.2);

function updateBackground() {
  const scrollY = window.scrollY;
  const opacityRate = 0.002;
  opacity.value = Math.max(0, 0.2 + scrollY * opacityRate);
}

const backgroundStyle = ref({
  opacity: opacity.value, 
});

watchEffect(() => {
  backgroundStyle.value.opacity = opacity.value;
  window.addEventListener('scroll', updateBackground);
});

watchEffect(onCleanup => {
  onCleanup(() => {
    window.removeEventListener('scroll', updateBackground);
  });
});
</script>

<template>
    <div class="hero w-screen h-[120vh]"> 
        <div 
            class="hero-green w-full h-full bg-[#255832] relative"
            :style="backgroundStyle">
            <img 
                src="../assets/tencups-full-logo.svg" 
                class="logo sticky top-[20%]"
            />
        </div>
        
    </div>
</template>

<style scoped>
    .hero {
        background-image: url("../assets/bar-image.webp");
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
    }
    .logo {
        width: 50%;
        height: auto;
        margin: auto;
    }

    .hero-green {
        transition: transform 0.2s, opacity 0.2s ease;
    }

@media (max-width:400px) {
    .logo {
        width: 100%;
    }
}
</style>