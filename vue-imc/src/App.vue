<template>
  <div id="app">
    <img src="./assets/logo.png" width="50px">
    <h1>{{ msg }}</h1>
    <div class="content">
      <label>
        Altura<br>
        <input id="height" autofocus type="text">
      </label>
    </div>
    <div class="content">
      <label>
        Peso<br>
        <input id="weight" autofocus type="text">
      </label>
      <div class="content">
        <button @click="calcImc()">Calcular</button>
      </div>
      <div id="resultField" class="input">
      <label>
        Resultado:<br>
        <input disabled type="text" v-model="result">
      </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Cálculo IMC com VUE',
      result: this.calcImc.value
    }
   },
   methods:{ 
     calcImc: function(){
       let height = document.getElementById('height').value.replace(',', '.');
       let weight = document.getElementById('weight').value.replace(',', '.');
       this.result = ((weight)/(height**2)).toFixed(2);
       console.log(this.result);
       return;
     }
  }
}
</script>

<style>
#app {
  margin: 200px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color:darkgray;
}

#resultField{
  margin-top: 15px;
}

input {
  display:inline-table;
}

h1, h2 {
  font-weight: normal;
}

.content {
  padding: 10px;
  flex-direction: row;
  justify-content: flex-start;
}


a {
  color: #42b983;
}
</style>
