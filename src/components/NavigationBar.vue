<script setup lang="ts">
import { ref } from 'vue';

const isToggled = ref(false);

function toggleMenu() {
  isToggled.value = !isToggled.value;
}

const screenWidth = ref(window.innerWidth);
</script>

<template>
    <div 
	    class="
			header-container
			w-full
			header-text
            flex 
            justify-between 
			items-center
            py-4
            px-10 
            font-[900]
        "
	>
		<a
			href="#hero"
			class="
				header-name 
				flex
				flex-col
				gap-2
				items-center
				leading-none
			"
		>
			<img 
                src="../assets/tencups-name-black.svg"
                class="w-[200px]"
            />
		</a>
		
		<a class="menu-toggle" @click="toggleMenu">
			<span :class="{ 'rotate-first': isToggled }"></span>
			<span :class="{ 'fade-out': isToggled }"></span>
			<span :class="{ 'rotate-third': isToggled }"></span>
		</a>

		<nav 
			v-if="isToggled || screenWidth > 400"
			class="flex gap-[48px] leading-none tracking-[2px] text-[16px]"
		>
			<a href="#about" class="about">
				ABOUT
			</a>
			<a href="#menu" class="menu">
				MENU
			</a>
			<a href="#lineup" class="lineup">
				EVENTS
			</a>
			<a href="info" class="access">
				ACCESS
			</a>
		</nav>
	</div>
</template>

<style scoped>
.header-container {
    background-color: rgba(255,244,228, 0.80);
}

svg {
    fill: rgb(63, 63, 63);
}
.about:hover {
    text-decoration: underline;
    text-decoration-color: rgb(63, 63, 63);
    text-decoration-thickness: 3px;
}

.menu:hover {
    text-decoration: underline;
    text-decoration-color: #4D6850;
    text-decoration-thickness: 3px;
}

.lineup:hover {
    text-decoration: underline;
    text-decoration-color: #58B5D0;
    text-decoration-thickness: 3px;
}

.access:hover {
    text-decoration: underline;
    text-decoration-color: #F29F94;
    text-decoration-thickness: 3px;
}

@media (max-width: 400px) {
	.header-name {
		margin: auto;
	}
	.menu-toggle{
		position: absolute;
		left: 24px;
		top: 28px;
		display: flex;
		flex-direction: column;
		gap: 4px;
	}
	.menu-toggle span {
		background-color: rgb(63, 63, 63);
		height: 2px;
		width: 20px;
		transition: all 0.5s ease;
	}
	.rotate-first {
		transform: rotate(45deg) translate(2px, 6px);
	}
	.rotate-third {
		transform: rotate(-45deg) translate(2px, -6px);
	}
	.fade-out {
		opacity: 0;
	}
	.header-container {
		flex-direction: column;
		gap: 32px;
		text-align: center;
	}
	nav {
		flex-direction: column;
	}
}
</style>