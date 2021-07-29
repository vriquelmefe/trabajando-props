import Formulario from '@/components/Formulario.vue';
<template>
  <div >
      <li >{{ tareaNueva }} <button v-on:click="$emit('eliminarTarea')">Eliminar</button></li> 
    
  </div>
</template>

<script>
export default {
  name: 'ListaTarea',
  
 
  props: {
    tareaNueva: {
      type: String,
    },
  },
  
}

</script>
