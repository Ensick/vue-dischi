<template>
    <header>
        <div>
            <img src="../assets/logo-small.svg" alt="img">
        </div>
    </header>
</template>

<script>
    export default {
        name:'HeaderComp'
    }
</script>

<style lang="scss" scoped>

    header{

        display: flex;
        align-items: center;
        background-color: rgba(46, 58, 70, 1);
        padding-inline: 15px;
        height: 100px;
        
        div{
           
            img{

                width: 50px;
                color: green;
            }
        }
    }

</style>