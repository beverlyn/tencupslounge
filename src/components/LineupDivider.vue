<script setup lang="ts">
import { onMounted, onUnmounted } from 'vue';

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

function handleScroll() {
  const container = document.getElementById('lineup-divider');

  if (container) { // Check if container is not null
    const backgroundPositionX = window.scrollY * 0.7;
    container.style.backgroundPosition = `-${backgroundPositionX}px 0px`;
  } else {
    console.error('Element with ID "mosaic-div" was not found.');
  }
}
</script>


<template>
    <div id="lineup-divider" class="lineup-divider"></div>
</template>

<style scoped>

.lineup-divider {
    width: 100%;
    height: 400px;
    background-repeat: repeat;
    background-image: url("../assets/lineup-divider.png");
    background-size: auto 100%; 
}
</style>