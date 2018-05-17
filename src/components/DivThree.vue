<template>
    <div class="div-three">
        <h1>Div3</h1>
    </div>
</template>


<script>
export default {
    name: 'DivThree',
    data: function() {
        return {
            color: 'green'
        }
    },
    mounted: function() {
        console.log('DivThree mounted!')
    }
    
}
</script>

<style>
.div-three {
    z-index: 1;
    position: fixed;
    bottom: 0;
    left: 0;
    background-color: rgb(46, 46, 46);
    height: 15vh;
    width: 100vw;
}
</style>
