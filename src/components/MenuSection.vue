<script setup lang="ts">
import CafeMenu from "./CafeMenu.vue";
import LoungeMenu from "./LoungeMenu.vue";
import FoodMenu from "./FoodMenu.vue";
import BrunchMenu from "./BrunchMenu.vue";
</script>

<template>
    <div class="content-container">
        <h1>
            MENUS
        </h1>
        <p class="subtitle">
            Start your morning right with a quick breakfast or swing by for a chill night with tasty drinks and bites – we've got you covered from sunrise to sunset. So grab a stool, invite your friends, and let the conversations flow!
        </p>

        <div 
            class="
            menu-container
            flex
            flex-col
            gap-4
            divide-y-4
            divide-[#255832]
            "
        >
            <CafeMenu/>
            <BrunchMenu/>
            <LoungeMenu/>
            <FoodMenu/>
        </div>
    </div>

</template>

<style scoped>
h1 {
    text-shadow: 4px 4px #4D6850;
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: #4D6850;
}

</style>