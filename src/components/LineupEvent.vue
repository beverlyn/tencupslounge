<template>
    <div class="event-date flex flex-col gap-2">
        <p class="leading-[12px]">
            <span class="font-bold text-[16px]">
                    <slot name="date"> </slot> <slot name="weekday"> </slot>
            </span>
            <br>
            <span class="text-[12px]">
                <slot name="time"> </slot>
            </span>
        </p>
    <p class="justify-self-center">
        <slot name="artist"> </slot>
    </p>
    </div>
</template>

<style>
.event-date {
    height: 100px;
    margin: auto;
    width: 100%;
    text-align: center;
    padding: 12px;
}
</style>

