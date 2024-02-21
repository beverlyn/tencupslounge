<script setup lang="ts">
import eventjson from "../assets/lineup.json";
import LineupEvent from './LineupEvent.vue';

const lineupItems = eventjson.february2024events;

const isPastEvent = (dateStr: string) => {
  const today = new Date();
  const currentYear = today.getFullYear(); // Use the current year for comparison
  const months = { JAN: 0, FEB: 1, MAR: 2, APR: 3, MAY: 4, JUN: 5, JUL: 6, AUG: 7, SEP: 8, OCT: 9, NOV: 10, DEC: 11 };
  const [month, day] = dateStr.split(' ');
  const eventDate = new Date(currentYear, months[month], day);

  today.setHours(0, 0, 0, 0);
  return eventDate < today;
};
</script>

<template>
    <div class="content-container">
        <h1>
            EVENTS
        </h1>

        <p class="subtitle">
            Come lounge with us and discover new sounds
        </p>

        <div class="flex m-auto w-fit gap-8 items-center pb-[32px]">
            <img src="../assets/tencups-selects.png" 
            class="w-[100px]"/>
            <h2 class="text-left font-[800] tracking-[3px]">
                FEBRUARY 
                <br>
                LINEUP
            </h2>
        </div>
        <ul>
            <li v-for="item in lineupItems" :key="item.date">
                <a 
                    :href="`https://www.instagram.com/${item.instagram}`"
                    target="_blank" rel="noopener noreferrer"
                >
                    <LineupEvent
                        :class="{ 'past-event': isPastEvent(item.date), 'event-item': !isPastEvent(item.date)}"
                    >
                        <template #date>{{ item.date }}</template>
                        <template #weekday>{{ item.weekday }}</template>
                        <template #time>{{ item.time }}</template>
                        <template #artist>{{ item.name }}</template>
                    </LineupEvent>
                </a>
            </li>
        </ul>
    </div>
</template>

<style scoped>
h1 {
    text-shadow: 4px 4px #558ABB;
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: #558ABB;
}

ul {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-rows: minmax(0, 1fr);
    column-gap: 32px;
    row-gap: 32px;
}
.past-event {
    background-color: #bba88e;
    box-shadow: 8px 8px #558ABB;
}
.event-item {
    background-color: #E8BB7A;
    box-shadow: 8px 8px #558ABB;
}

.event-item:hover, .past-event:hover {
    outline: 2px solid #EE9F95;
    box-shadow: 12px 12px #EE9F95;
}

@media (max-width: 400px) {
    ul {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-auto-rows: minmax(0, 1fr);
        column-gap: 32px;
        row-gap: 32px;
    }
}
</style>