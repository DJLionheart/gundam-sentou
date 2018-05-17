<template>
    <div class="div-two">
        <div class="controls">
            <button @click="view == 'create'">Create</button>
            <button @click="view == 'suitUp'">Suit Up</button>
        </div>
        <div id="control-field">
            <div v-show="view == 'create'">
                <h1>Create Gundam</h1>
            </div>
            <div v-show="view == 'suitUp'">
                <h1>Suit up</h1>
            </div>
        </div>

    </div>
</template>


<script>
export default {
    name: 'DivTwo',
    data: function() {
        return {
            view: 'create'
        }
    },

    mounted: function() {
        console.log('DivTwo mounted!')
    }
    
}
</script>

<style>
.div-two {
    position: fixed;
    top: 130px;
    right: 8px;
    height: 70vh;
    background: linear-gradient(to bottom, rgba(255,255,255,0.15) 0%, rgba(0,0,0,0.15) 100%), radial-gradient(at top center, rgba(255,255,255,0.40) 0%, rgba(0,0,0,0.40) 120%) #989898; 
    background-blend-mode: multiply,multiply;
    width: 30vw;
}

#control-field {
    background: rgba(255, 255, 255, 0.767);
    width: 90%;
    height: 85%;
    margin: auto;
}

.controls {
    height: 50px;
    margin-top: 10px;
}
</style>
