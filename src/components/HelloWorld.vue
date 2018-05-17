<template>
  <div class="hello">
    <header>
      <img class="logo" src="../assets/helmet.png" alt="gundam helmet">
      <h1>Gundam Sentou 戦闘</h1>
      <h2>{{ msg }}</h2>
    </header>
    <img src="../assets/background.jpg" alt="background" id="background">
    <div class="div-container">
      <div class="arena">
        <h1>Arena</h1>
        <hr>
        <div class="battle-slots">
          <div class="slot-one">
            <img src="../assets/matrix.jpg" alt="gundam slot">
          </div>
          <div class="battle-btn">
            FIGHT!!</div>
          <div class="slot-two">
            <img src="../assets/matrix.jpg" alt="gundam slot">
          </div>
        </div>
      </div>
      <div class="control-panel">
        <div class="controls">
            <button @click="controlView = 'create'">Create</button>
            <button @click="controlView = 'inventory'">Inventory</button>
        </div>
        <div class="control-field">
            <div v-show="controlView == 'create'">
                <h1>Create Gundam</h1>
                <hr>
                <h3>{{name}}</h3>
                <input v-model="name">
                <br>
                <h3>Attack: {{atk}}</h3>
                <input v-model="atk">
                <br>
                <h3>Defence: {{def}}</h3>
                <input v-model="def">
                <br>
                <img v-bind:src="'https://robohash.org/' + name" alt="gundam picture" class="gundam-pic">
                <div class="add-gundam">
                  <button @click="addGundam()">Add to Inventory</button>
                </div>
            </div>
            <div v-show="controlView == 'inventory'">
              <h1>Inventory</h1>
              <hr>
              <div class="gc" v-bind:key=index index v-for="(gundam, index) in gundams">
                <div class="gc-head">
                  <h3>{{gundam.name}}</h3>
                  <button @click="select(gundam)">Select</button>
                </div>
                <hr>
                <h3>Attack: {{gundam.atk}}</h3>
                <h3>Defense: {{gundam.def}}</h3>
                <img v-bind:src="'https://robohash.org/' + gundam.name" alt="gundam picture" class="gundam-pic">


              </div>
            </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      name: 'Name',
      atk: 'Attack',
      def: 'Defense',
      pic: 'Change Text Here',
      msg: 'Build your Gundams and FIGHT!',
      controlView: 'create',
      gundams: [
        {name: 'CyberJam', atk: 177, def: 80}
      ],
      arena: []
    }
  },
  methods: {
    addGundam: function() {
      this.gundams.push(
        {
          name: this.name,
          atk: this.atk,
          def: this.def,
        }
      )
    },
    select: function(gundam) {
      this.arena.length == 2 ? alert('Only two may fight...') : this.arena.push(gundam)
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  margin: 0;
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.hello {
  height: 100vh;
  background-position: top left;
  background-size: auto; 
  display: flex;
  flex-direction: column;
  overflow: none;
}

.hello img {
  height: 100;
}

header {
  z-index: 1;
  position: fixed;
  left: 37%;
}

.logo {
  padding: 10px 0 0 10px;
  position: fixed;
  left: 0;
  width: 120px;
  z-index: 1;
}

#background {
  position: fixed;
  width: 1200px;
}

.arena {
    position: fixed;
    top: 130px;
    background-color: #ffffff47;
    
    height: 70vh;
    width: 70vw;   
}

.control-panel {
    position: fixed;
    top: 130px;
    right: 0px;
    height: 553px;
    background: linear-gradient(to bottom, rgba(255,255,255,0.15) 0%, rgba(0,0,0,0.15) 100%), radial-gradient(at top center, rgba(255,255,255,0.40) 0%, rgba(0,0,0,0.40) 120%) #989898; 
    background-blend-mode: multiply,multiply;
    width: 300px;
}


.control-field {
    background: rgba(255, 255, 255, 0.767);
    width: 90%;
    height: 85%;
    margin: auto;
    display: flex;
    flex-direction: column;
    overflow-x: hidden;
    overflow-y: scroll;
}

::-webkit-scrollbar {
  width: 0px;
  background: transparent;
}

h3 {
  margin: 0;
}

.controls {
    height: 50px;
    margin-top: 10px;
}

.gundam-pic {
  height: 150px;
  width: 150px;
}

.gc {
  margin: auto;
  margin-bottom: 5px;
  width: 200px;
  border: 1px grey solid;
}

.gc img {
  height: 100px;
  width: 100px;
}
.gc button {
  position: relative;
  
}

.gc-head {
  margin-top: 6px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.arena {

}

.battle-btn {
  width: 100px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  border-radius: 5px;
  background-image: linear-gradient(to right, #243949 0%, #517fa4 100%);
  border: 1px solid black;
  transition: 2s background ease-in-out;
}

.battle-btn:hover {
  cursor: pointer;
  transition: background ease-in-out;
  animation: getReady 1s infinite;
}

@keyframes getReady {
  0%   {background-image: linear-gradient(to right, #243949 0%, #517fa4 100%)}
  50%  {background-image: linear-gradient(to right, #7c0000 0%, #fa0000 100%)}
  100% {background-image: linear-gradient(to right, #243949 0%, #517fa4 100%)}
  
}



.battle-slots {
  height: 70%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.arena img {
  width: 200px;
  height: 200px;
}

</style>
