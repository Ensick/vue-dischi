<template>
    <div class="ms-card-album">
        <img src="https://img.discogs.com/vknPDdrqRbT92pNRX0W4I5N91jg=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1246953-1448927086-6590.jpeg.jpg" alt="img">
        <h2>New Jersey</h2>
        <h3>1988</h3>
    </div>
</template>

<script>
    export default {
        name: 'AlbumComp'
    }
</script>

<style lang="scss" scoped>

    .ms-card-album{

        width: calc(100% / 5);
        padding: 25px 15px;
        aspect-ratio: 2/1;

        img{
            width: 100%;
        }
            
        h2,h3{

            color: white;
            text-align: center;
        }
    }

</style>