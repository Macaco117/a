<template>
 <Navbar />
 <div class="container">
    <router-view/>
 </div>
<Datos/>
</template>

<script>
import {mapActions} from 'vuex'
import Navbar from './components/Navbar.vue'
import Datos from './components/Datos.vue'

export default {
  components: {
    Navbar, Datos
  },
   
  methods: {
    ...mapActions(['cargarLocalStorage'])
  },
 
 
  created(){
    this.cargarLocalStorage()
  }
}
</script>