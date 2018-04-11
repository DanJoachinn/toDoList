<template>
  <div class="container">
    <div>
      <h1 class="title">
        To do list
      </h1>
      <h2 class="subtitle">
        Pagina 0 list.
      </h2>
      <input type="text" placeholder="Mis pendientes" v-model="inputText">
      <button @click="hola">
        Agrega pendientes
      </button>
      <div class="lista">
        <ul >
          <li  v-for="(cosa, index) in cosas" :key="cosa">
            {{cosa}}<button id="quitar" @click="quitar(index)">Quitar</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
     data () {
      return {
        inputText: '',
        cosas: []
      }
    },
    methods:{
      hola: function(){
        this.cosas.push(this.inputText)
        this.inputText=""
      },
      quitar:function(i){
        this.cosas.splice(i,1)
      }
    }
  }
  

</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
