<script setup lang="ts">
import { ref } from 'vue';
import menujson from "../assets/foodMenu.json";
import MenuItems from "./MenuItems.vue";

const foodItems = menujson.food;
const dessertItems = menujson.dessert;

const isMenuVisible = ref(false);

const toggleMenu = () => {
  isMenuVisible.value = !isMenuVisible.value;
};
</script>

<template>
    <div class="flex flex-col pt-6">
        <span @click="toggleMenu" class="flex justify-between">
            <span class="flex gap-2">
                <IconLucideUtensils class="text-[20px]"/>
                <span>
                    <p class="font-extrabold tracking-[3px] text-[28px] leading-6">
                        FOOD MENU
                    </p>
                    <p class="">
                        18:00 ~ 22:00
                    </p>
                </span>
            </span>
            <IconMaterialSymbolsKeyboardArrowDownRounded 
                :class="{ 'rotate-arrow': isMenuVisible }"
                class="arrow text-[40px] translate-y-[-16px]"/>
        </span>

        <div class="flex flex-col gap-4" v-show="isMenuVisible">
            <hr class="my-4 bg-[#F29F94] border-2 border-[#F29F94]">
            <span>
                <h3>
                    FOOD
                </h3>
                <ul>
                    <li v-for="item in foodItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </span>

            <span>
                <h3>
                    DESSERT
                </h3>
                <ul>
                    <li v-for="item in dessertItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </span>
        </div>
    </div>
</template>

<style scoped>
h3 {
    text-decoration: underline;
    margin-bottom: 8px;
}

ul {
    display: flex;
    flex-direction: column;
    gap: 8px;
    padding: 0 16px 0 16px;
    text-transform: uppercase;
}

.extra {
    gap: 1px;
}
.rotate-arrow {
    transform: translatey(-15px) rotate(180deg);
    transition: transform 0.3s ease;
}

.arrow {
    transition: transform 0.3s ease;
}
</style>