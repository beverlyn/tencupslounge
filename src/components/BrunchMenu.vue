<script setup lang="ts">
import { ref } from 'vue';
import menujson from "../assets/brunchMenu.json";
import MenuItems from "./MenuItems.vue";

const brunchItems = menujson.brunchFood;
const setItems = menujson.setDrinks;
const extraItems = menujson.extras;

const isMenuVisible = ref(false);

const toggleMenu = () => {
  isMenuVisible.value = !isMenuVisible.value;
};
</script>

<template>
    <div class="flex flex-col pt-6">
        <span @click="toggleMenu" class="flex justify-between">
            <span class="flex gap-2">
                <IconLucideCroissant class="text-[20px]"/>
                <span>
                    <p class="font-extrabold tracking-[3px] text-[28px] leading-6">
                        BRUNCH MENU
                    </p>
                    <p class="">
                        09:00 ~14:00
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
                    <li v-for="item in brunchItems" :key="item.name">
                        <MenuItems>
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </span>

            <div class="border-2 border-[#255832] py-1 mx-[36px] bg-[#F29F94]">
                <h3 class="text-[12px] text-center">
                    EXTRAS
                </h3>
                <ul class="extra">
                    <li v-for="item in extraItems" :key="item.name">
                        <MenuItems class="text-[10px] tracking-widest">
                            <template #item-name>{{ item.name }}</template>
                            <template #item-price>{{ item.price }}</template>
                            <template #item-desc>{{ item.description }}</template>
                        </MenuItems>
                    </li>
                </ul>
            </div>

            <span>
                <h3>
                    SET DRINKS +¥600
                </h3>
                <ul>
                    <li v-for="item in setItems" :key="item.name">
                        <MenuItems  :showYenSymbol=false>
                            <template #item-name>{{ item.name }}</template>
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