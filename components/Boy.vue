<template>
    <div>
        <img class="boy" src="~/assets/boy.svg" alt="Niño">
    </div>
</template>
<script>
export default {
    
}
</script>
<style>

.boy {
    position: absolute;
    width: 100px;
    height: auto;

    top: 350px;
    left: 400px;
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
    .boy {
        width: 150px;

        top: 650px;
        left: 700px;
    }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (max-width: 1920px) {
    .boy {
        width: 100px;

        top: 350px;
        left: 400px;
    }
}
/*
 * Medium devices (Laptops, 1680px)
 */
@media (max-width: 1680px) { 
    
}
/*
 * Landscape (Tablets, 1536px)
 */
@media (max-width: 1536px) { 
    .boy {
        width: 100px;

        top: 300px;
        left: 350px;
    }
}
/*
 * Landscape (Tablets, 1024px)
 */
@media (max-width: 1024px) { 
    .boy {
        width: 60px;

        top: 230px;
        left: 220px;
    }
}
</style>