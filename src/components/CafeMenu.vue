<script setup lang="ts">
import { ref } from 'vue';
import menujson from "../assets/cafeMenu.json";
import MenuItems from "./MenuItems.vue";

const coffeeItems = menujson.Coffee;
const originalsItems = menujson.Originals;
const extrasItems = menujson.Extras;
const softDrinkItems = menujson["Soft Drinks"];
const brunchCocktailItems = menujson["Brunch Cocktails"];

const isMenuVisible = ref(false);

const toggleMenu = () => {
  isMenuVisible.value = !isMenuVisible.value;
};

</script>

<template>
    <div class="flex flex-col">
        <span @click="toggleMenu" class="flex justify-between">
            <span class="flex gap-2">
                <IconMingcuteTeacupLine class="text-[20px]"/>
                <span>
                    <p class="font-extrabold tracking-[3px] text-[28px] leading-6">
                    CAFE MENU
                </p>
                <p class="">
                    09:00 ~ 17:00
                </p>
                </span>
            </span>
            <IconMaterialSymbolsKeyboardArrowDownRounded 
                :class="{ 'rotate-arrow': isMenuVisible }"
                class="arrow text-[40px] translate-y-[-16px]"/>
        </span>

        <!-- <div class="flex flex-col gap-4" v-show="isMenuVisible"> -->
        <div class="menu-content flex flex-col gap-4" :class="{'menu-visible': isMenuVisible}" >
            <hr class="my-4 bg-[#F29F94] border-2 border-[#F29F94]">
            <span>
                <h3>
                    COFFEE
                </h3>
                <ul>
                    <li v-for="item in coffeeItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </span>

            <span>
                <h3>
                    ORIGINALS
                </h3>
                <ul>
                    <li v-for="item in originalsItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </span>

            <div class="border-2 border-[#255832] py-1 mx-[36px]">
                <h3 class="text-[12px] text-center">
                    EXTRAS
                </h3>
                <ul class="extra">
                    <li v-for="item in extrasItems" :key="item.name">
                        <MenuItems class="text-[10px] tracking-widest">
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </div>

            <span>
                <h3>
                    SOFT DRINKS
                </h3>
                <ul>
                    <li v-for="item in softDrinkItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </span>

            <div class="border-2 border-[#255832] py-1 bg-[#F29F94]">
                <h3 class="text-center">
                    BRUNCH COCKTAILS
                </h3>
                <ul>
                    <li v-for="item in brunchCocktailItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<style scoped>
.menu-content {
    transition: max-height 0.3s ease, visibility 0.3s;
    overflow: hidden;
    max-height: 0; /* Start with max-height 0 to hide content */
    visibility: hidden; /* Make content not visible */
}

/* Add a class in your <script setup> that toggles these properties */
.menu-visible {
    max-height: fit-content; /* Adjust as needed based on your content's size */
    visibility: visible; /* Make content visible */
}

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
.rotate-arrow {
    transform: translatey(-15px) rotate(180deg);
    transition: transform 0.3s ease;
}

.arrow {
    transition: transform 0.3s ease;
}
</style>