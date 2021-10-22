<template>
  <h1 class="my-5">Formularios con Vue.js</h1>
 <form @submit.prevent="procesarFormulario">
   <Input :tarea="tarea"/>
  </form>
 <hr>
 <!-- <p>
   {{ tarea }}
 </p> -->
 <ListaTareas />

</template>

<script>
 import Input  from '../components/Input.vue'
 import ListaTareas  from '../components/ListaTareas.vue'
 import {mapActions} from 'vuex'
 const shortid = require ('shortid');



export default {
  name: 'Home',
  components: {
     Input, ListaTareas
    
    },
  
   data() {
    return {
      tarea: {
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0,
      }
    }
  },

   methods: {
     ...mapActions(['setTareas']),

     procesarFormulario () {
      console.log(this.tarea)
      if(this.tarea.nombre.trim() === "") {
        console.log('Campo vacio...')    
        return
      }
      console.log('No esta vacio..')
    
      //generar id
      this.tarea.id = shortid.generate()
      console.log(this.tarea.id)

      //enviamos los datos
      this.setTareas(this.tarea)

      this.tarea = {
        id: '',
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0,
      }
    }
  },
  
}
</script>
