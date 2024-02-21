<script setup lang="ts">
defineProps({
  showYenSymbol: {
    type: Boolean,
    default: true,
  }
});
</script>

<template>
    <span 
        class="
            grid 
            grid-cols-5 
            gap-4
        "
    >
        <span class="col-span-4">
            <p 
                class="font-[500]"
            >
                <slot name="item-name"></slot>
            </p>
            <p class="text-[10px] tracking-widest">
                <slot name="item-desc"></slot>
            </p>
        </span>
        <p>
            <span v-if="showYenSymbol">¥</span>
            <span class="font-bold"><slot name="item-price"></slot></span>
        </p>
    </span>
</template>