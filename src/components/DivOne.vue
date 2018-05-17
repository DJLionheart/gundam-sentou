<template>
    <div class="div-one">
        <h1>Arena</h1>
    </div>
</template>


<script>
export default {
    name: 'DivOne',
    data: function() {
        return {
            color: 'green'
        }
    },
    mounted: function() {
        console.log('DivOne mounted!')
    }
    
}
</script>

<style>
h1 {
    margin: 0;
    padding: 0;
}
.div-one {
    position: fixed;
    top: 130px;
    background-color: #ffffff47;
    
    height: 70vh;
    width: 70vw;
    
}
</style>
