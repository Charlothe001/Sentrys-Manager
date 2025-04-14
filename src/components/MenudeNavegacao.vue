<script>
  export default{
    name:"Navegacao"
  }
</script>
<template>
      <nav class="container">
        <div><RouterLink class="nav-link" to="/">Principal</RouterLink></div>
        <div><RouterLink class="nav-link" to="/login">Login</RouterLink></div>
        <div><RouterLink class="nav-link" to="/about">Sobre</RouterLink></div>
      </nav>
</template>
<style>
.container {
  display: flex;
  flex-wrap: wrap; /* Permite que os itens se movam para novas linhas se necessário */
  flex-direction: row; /* Alinha os itens na horizontal */
  justify-content: center; /* Centraliza os itens horizontalmente */
  align-items: center; /* Centraliza os itens verticalmente */
  margin: auto;
  gap: 20px; /* Espaçamento entre os itens (divs) */
}

.nav-link:hover{
  color: #a1540c;
  background-color: transparent;
}

</style>