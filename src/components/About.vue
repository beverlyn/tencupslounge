<template>
    <div class="content-container">
        <h1>
            ABOUT
        </h1>
        
        <div class="info flex gap-[72px] items-center">
            <img 
                src="../assets/ten-of-cups.jpg"
                class="h-[300px] w-auto"
            />
            <p>
                TENCUPS draws its inspiration from the tarot card "Ten of Cups," which symbolizes harmony and abundance in all relationships. We aim to provide a space where diverse communities can come together to savor, connect, and innovate. 
                <br>
                <br>
                <strong>Indulge</strong> in the rich flavors of our coffee, organically cultivated from the Akha village in Northern Thailand. 
                <br>
                <strong>Embark</strong> on a culinary journey with our thoughtfully curated menus, served on ceramics handcrafted with care in Vietnam. 
                <br>
                <strong>Delight</strong> your senses to our unique selection of captivating music. 
                <br>
                <br>
                Whether you start your day with our signature "Pandan Latte", or wind down with our innovative "Satay of the Gods" cocktail, expect nothing short of a memorable experience. So come on in and immerse yourself in a world where every moment is infused with flavor and connection.
            </p>
        </div>
    </div>
</template>

<style scoped>
h1 {
    text-shadow: 4px 4px rgb(63, 63, 63);;
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: rgb(63, 63, 63);
}

@media (max-width: 400px) {
    .info {
        flex-direction: column;
        gap: 36px;
    }
}
</style>