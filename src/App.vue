<template>
  <div id="app" class="corpo">
 <!-- EXIBE UM COMPONENTE OU OUTRO (HOME OU APP) trabalhar com rotas nao é algo padrão do vue, por isso é importante instalar o módulo vue router,e importar no main.js-->
      <router-view></router-view>
  </div>
</template>

<script>

  export default {

  }
</script>


<style>
  .corpo {
    font-family: Helvetica, sans-serif;
    margin: 0 auto;
    width: 96%;
  }
</style>