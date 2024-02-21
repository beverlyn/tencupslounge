<!-- <template>
    Cafe & Cocktails & Conceptual Bites

    Methods of payment accepted
    Wifi/outlets?

</template> -->


<template>
    <div class="content-container">
        <h1>
            ACCESS
        </h1>

        <p class="subtitle">
            Based in the heart of Tokyo, a short walk away from Shibuya Station.
            <br>
            Leave your comfort zone and enter ours.
        </p>

        <div class="info-section flex justify-between">
            <div class="flex flex-col gap-6">
                <span class="map-info flex gap-4">
                    <IconMaterialSymbolsMapOutline class="text-[20px]" />
                    <span>
                        <p>3-26-21 Shibuya City, Shibuya, Tokyo</p>
                        <a 
                            href="https://maps.app.goo.gl/S3VmPu3kPmJm5bP69"
                            target="_blank" rel="noopener noreferrer"
                            class="google-maps"
                        > 
                            >>> Google Maps 
                        </a>
                    </span>
                </span>
                <span class="flex gap-4">
                    <IconMaterialSymbolsCalendarMonthOutline class="text-[20px]"/>
                    <span>
                        <p>
                            Tuesday - Thursday, Sunday: 9AM - 11PM 
                        </p>
                        <p>
                            Friday & Saturday: 9AM - 12AM 
                        </p>
                        <p>
                            Monday: Closed
                        </p>
                    </span>
                </span>
                <span class="flex gap-4 items-center">
                    <IconBiTelephone class="text-[20px]"/>
                    <p>12-3456-7890</p>
                </span>
                <a 
                    href="https://www.instagram.com/tencupslounge"
                    target="_blank" rel="noopener noreferrer"  
                    class="flex gap-4 items-center"  
                >
                    <IconMdiInstagram class="text-[20px]"/>
                
                    @tencupslounge
                </a>
            </div>
            <div class="map">
                <!-- <img src="../assets/map.png"/> -->
            </div>
        </div>
    </div>
</template>

<style scoped>
h1 {
    text-shadow: 4px 4px #F29F94;
    -webkit-text-stroke-width: 2px;
    -webkit-text-stroke-color: #F29F94;
}
.info-section {
    flex-direction: row;
}

a:hover {
    color:#F29F94;
    font-weight: bold;
}
.map {
    background-image: url("../assets/map.png");
    background-size: cover;
    background-position: center;
    min-width: 300px;
    width: 100%;
    max-width: 400px;
    height: 300px;
}

.map-info {
    align-items: center;
}

.google-maps {
        display: none;
    }

@media (max-width: 750px) {
    .info-section {
        flex-direction: column;
    }
    .map {
        margin: auto;
        max-width: 100%;
    }
}

@media (max-width: 400px) {
    .map {
        display: none;
    }
    .map-info {
        align-items: start;
    }
    .google-maps {
        display: block;
    }
}
</style>
