<template>
  <div id="app">
   <h1>{{ titulo }}</h1>
   <ul>
     <li v-for="foto in fotos" :key="foto.id">
       <img :src="foto.url" :alt="foto.titulo">
     </li>
  </ul>
  </div>
</template>

<script>
export default {
 
  data() { 
    return {
    titulo: 'Alurapic',  
     fotos: [ ]
    
     
    }
  },
    created() {
      let promise = this.$http.get('http://localhost:3000/v1/fotos')
        .then(r => r.json())
        .then(fotos1 => this.fotos = fotos1)
     
  
  },

}
</script>

<style>
</style>
