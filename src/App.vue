<template>
  <div id="app">
    <h2> Crea una nueva tarea</h2>
    <label for="tarea" ><b>Tarea </b></label>
    <input type="text" v-model="nuevoIngreso" placeholder="Ingresa nueva tarea">
    <button @click="agregarTarea">Crear</button>
    <h4>Lista</h4>
    <ul >
    <ListaTarea v-for="(tarea , index) in tareas" :key="index" :tareaNueva="tarea" v-on:eliminarTarea="tareas.splice(index,1)"></ListaTarea>
    </ul>    
  </div>
</template>

<script>
import ListaTarea from '@/components/ListaTarea.vue';
 

export default {
  name: "App",
  components: {
    ListaTarea
  },
  data: () => ({
    nuevoIngreso : '',
    tareas: []
  }),
  methods: {
    agregarTarea() {
      this.tareas.push( this.nuevoIngreso )
      this.nuevoIngreso = ''
    },
  }
   
  
};
</script>

<style>
#app {
  text-align: center;
}
ul{
    margin: 0 auto;
    text-align: left;
    padding-left: 15% ;
    width: 20%;
  }
</style>
