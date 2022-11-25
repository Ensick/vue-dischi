<template>
    <div class="ms-card-album">
        <img :src="AlbumData.poster" alt="img">
        <h2>{{AlbumData.title}}</h2>
        <h4>{{AlbumData.author}}</h4>
        <h4>{{AlbumData.year}}</h4>
    </div>
</template>

<script>
    export default {

        name: 'AlbumComp',

        props: {

           AlbumData: Object
            
        }
    }
</script>

<style lang="scss" scoped>

    .ms-card-album{


        background-color: rgba(46, 58, 70, 1);
        width: calc((100% / 5) - 40px);
        padding: 30px 30px 50px 30px;
        aspect-ratio: 1/1;

        img{
            width: 100%;
            margin-bottom: 20px;
        }

        h2{
            padding-bottom: 15px;
            color: white;
        }
            
        h2,h4{

            text-align: center;
        }

        h4{

            color: rgba(105, 108, 110, 1);
        }
    }

</style>