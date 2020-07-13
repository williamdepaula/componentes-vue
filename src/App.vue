<template>
  <div id="app" class="container">
    <listagem />
  </div>
</template>

<script>
import listagem from './components/search-form/listagem.vue'

export default {
  name: 'App',
  components: {
    listagem
  }
}
</script>

<style>
body {
  margin-top: 40px;
}
</style>
