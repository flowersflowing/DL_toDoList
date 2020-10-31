<template>
  <div class="hello">
    <h2>Lista de tareas</h2>
    <h4>Tarea</h4>
    <input type="text" v-model="tarea">
    <span><button @click="agregarTarea(tarea, index)">Crear</button></span>
    <div v-if="tarea > 0">
      <h3>Cosas por hacer:</h3>
      <ul>
        <li v-for="(tarea, index) in tareas" :key="index">{{index}} - {{tarea}}</li>
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
        tareas: [],
    }
  },
  methods: {
    agregarTarea(tarea) {
      this.tareas.push(tarea);
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
  margin: 0 10px;
}
</style>
