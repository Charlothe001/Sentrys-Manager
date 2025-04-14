<script>
  import { RouterLink } from 'vue-router'
  export default {
    name: "Funcionarios",
    data() {
      return {
        listaDeColaboradores: [
          { id: 1, classe: "operacional", nome: "claudio", funcao: "eletricista" },
          { id: 2, classe: "administrativo", nome: "fabiana", funcao: "administradora" },
          { id: 3, classe: "engenharia", nome: "rubens", funcao: "engenheiro" }
        ],
        pesquisa: "", // Para vincular com a caixa de pesquisa
        colaboradorEncontrado: null // Para exibir as informações do colaborador pesquisado
      };
    },
    computed: {
      // Filtra colaboradores com base no nome digitado
      colaboradoresFiltrados() {
        return this.listaDeColaboradores.filter(c =>
          c.nome.toLowerCase().includes(this.pesquisa.toLowerCase())
        );
      }
    },
    methods: {
      pesquisaDeFuncionario() {
        // O Vue já faz isso reativamente com a propriedade 'pesquisa'
        const collaborator = this.listaDeColaboradores.find(c => c.nome.toLowerCase() === this.pesquisa.toLowerCase());
        if (collaborator) {
          this.colaboradorEncontrado = collaborator;
        } else {
          this.colaboradorEncontrado = null; // Se não encontrar
        }
      }
    }
  }
</script>

<template>
  <aside>
    <main>
      <div>
        <form @submit.prevent="pesquisaDeFuncionario">
          <label>Procurar
            <input type="text" v-model="pesquisa" placeholder="Digite o nome">
          </label>
          <button type="submit">Buscar</button>
        </form>
      </div>

      <!-- Cards dos colaboradores -->
      <div v-for="(collaborator) in colaboradoresFiltrados" :key="collaborator.id">
        <RouterLink :to="`/colaboradores/${collaborator.id}`">
          <article id="cards">
            <div>
              <h4>{{ collaborator.classe }}</h4>
            </div>
            <div>
              <figure>
                <img :src="`../../public/image/img-3x4.jpg`" alt="img">
              </figure>
            </div>
          </article>
        </RouterLink>
      </div>
    </main>
  </aside>

  <!-- Seção de detalhes do colaborador -->
  <section>
    <header>
      <div>
        <h1>Lista de Funcionários</h1>
      </div>
    </header>

    <main>
      <div id="employeesMainFrame">
        <div v-if="colaboradorEncontrado" class="cardFuncionarios">
          <div>
            <img :src="`../../public/image/img-3x4.jpg`" alt="Funcionario">
          </div>
          <div id="info">
            <p>Classe: {{ colaboradorEncontrado.classe }}</p>
            <p>ID: {{ colaboradorEncontrado.id }}</p>
            <p id="nometest">Nome: {{ colaboradorEncontrado.nome }}</p>
            <p>Função: {{ colaboradorEncontrado.funcao }}</p>
          </div>
        </div>
      </div>
    </main>
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: row;
}
aside {
  display: flex;
  flex-direction: column;
  width: 25%;
}
section {
  width: 75%;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
}

#cards {
  display: flex;
  flex-direction: column;
  background-color: rgb(197, 195, 199);
  align-items: center;
  border: 2px solid gray;
  margin: 10px;
  padding: 10px;
  height: 100px;
  width: 150px;
}

a #cards {
  color: white;
}

img {
  width: 20px;
  height: 30px;
  border: 2px solid gray;
  border-radius: 5px;
}

#employeesMainFrame {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  border-radius: 2px;
}

.cardFuncionarios {
  display: flex;
  flex-direction: row;
  padding: 10px;
}

.cardFuncionarios img {
  width: 40px;
  height: 60px;
}

.cardFuncionarios div {
  margin: 10px;
}
</style>