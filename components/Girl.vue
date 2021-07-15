<template>
    <div>
        <img class="girl" src="~/assets/girl.svg" alt="Niña">
    </div>
</template>
<script>
export default {
    
}
</script>
<style>

.girl {
    position: absolute;
    width: 100px;
    height: auto;

    top: 600px;
    left: 1050px;
    z-index: 20;
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
    .girl {
        width: 150px;

        top: 1050px;
        left: 1800px;
    }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (max-width: 1920px) {
    .girl {
        width: 100px;

        top: 600px;
        left: 1050px;
    }
}
/*
 * Medium devices (Laptops, 1680px)
 */
@media (max-width: 1680px) { 
    .girl {
        width: 100px;

        top: 550px;
        left: 920px;
    }
}
/*
 * Landscape (Tablets, 1536px)
 */
@media (max-width: 1536px) { 
    .girl {
        width: 100px;

        top: 500px;
        left: 840px;
    }
}
/*
 * Landscape (Tablets, 1024px)
 */
@media (max-width: 1024px) { 
    .girl {
        width: 60px;

        top: 340px;
        left: 550px;
    }
}
</style>