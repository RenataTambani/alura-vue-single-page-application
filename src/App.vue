

<template>
  <div id="app" class="corpo">
   <h1 class="centralizado">{{ titulo }}</h1>
   <input type="search" class="filtro" v-on:input="filtro = $event.target.value" placeholder="Filtre por parte do título">
   {{ filtro }}
    <ul class="lista-fotos">
      <li v-for="foto in fotos" :key="foto.id" class="lista-fotos-item"> 
        <meu-painel :titulo="foto.titulo">
          <img :src="foto.url" :alt="foto.titulo" class="imagem-responsiva">
        </meu-painel>
      </li>
    </ul>
  </div>
</template>

<script>
import Painel from './components/shared/painel/painel.vue'

export default {

  components: {
    "meu-painel": Painel
  },
  data() { 
    return {
      titulo: 'Alurapic',  
      fotos: [ ],
      filtro: "",
    
     
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

  .centralizado {
    text-align: center;
  }

  .corpo {
    font-family: Helvetica, sans-serif;
    margin: 0 auto;
    width: 96%;
  }

  .lista-fotos {
    list-style: none;
  }

  .lista-fotos .lista-fotos-item {
    display: inline-block;
  }
  .filtro {
    display: block;
    width: 100%;
  }
</style>