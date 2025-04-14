<script setup>
import { RouterLink} from 'vue-router'
import Navegacao from './components/MenudeNavegacao.vue'
</script>

<template>
  <header>
    <Navegacao/>
  </header>
  <div id="routerMain">
    <RouterView />
  </div>
  <footer>
    <p>
      &copy;Charlotte Dev & Tech - 2025
    </p>
  </footer>
</template>

<style>
#app{
  display: flex;
  flex-direction: column;
  margin: 10px;
  padding: 0;
  box-sizing: border-box;
  min-height: 100vh;
 }

 div #routerMain{
  display: flex;
  flex-direction: row;
 }
</style>
