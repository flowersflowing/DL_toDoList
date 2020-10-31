<template>
  <div class="hello">
    <h2>Lista de tareas</h2>
    <form @submit.prevent="agregarTarea">
      <label for="tarea">Tarea: </label>
      <input type="text" v-model="tarea">
      <span><button type="submit">Crear</button></span>
    </form>
    <div v-if="tarea">
      <h3>Cosas por hacer:</h3>
      <ul>
        <li v-for="(tarea, index) in tareas" :key="index">{{index+1}} - {{tarea}}</li>
      </ul>
    </div>
    <div v-else>
        <p>Ingrese una tarea</p>
    </div>    
  </div>
</template>

<script>
export default {
  name: 'Formulario',
  data () {
    return {
        tarea: '',
        tareas: [],
    }
  },
  methods: {
    agregarTarea() {
      this.tareas.push(this.tarea);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h4 {
  margin: 40px 0 0;
}
h3 {
  margin: 40px 7px 0 3px;
}
ul {
  padding: 0;
}
li {
  margin: 0 60px;
}
</style>
