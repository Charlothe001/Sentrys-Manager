<script setup>
 
</script>

<template>
  <section>
    <header>
      <div>
        <h1>Sentrys Manager - Gestão Empresarial.</h1>
      </div>
      <div>
        <h2>
          Bem Vindo ao Sentrys Manager, Aqui você pode gerenciar seus Funcionharios, produtos, vendas, clientes e fornecedores, e muito mais.
        </h2>
      </div>
    </header>
    <main>
      <RouterLink to="/funcionarios">
        <article id="cards">        
          <div>
            <h4>Funcionario</h4>
          </div>
          <div>
            <figure>
              <img src="../../public/image/img-3x4.jpg" alt="img">              
            </figure>            
          </div>
        </article>
      </RouterLink>
      <RouterLink to="">
        <article id="cards">        
          <div>
            <h4>Orçamento</h4>
          </div>
          <div>
            <figure>
              <img src="../../public/image/orcamento.bmp" alt="img">              
            </figure>            
          </div>
        </article>
      </RouterLink>
      <RouterLink to="">
        <article id="cards">        
          <div>
            <h4>Contrato</h4>
          </div>
          <div>
            <figure>
              <img src="../../public/image/orcamento.bmp" alt="img">              
            </figure>            
          </div>
        </article>
      </RouterLink>
      <RouterLink to="">
        <article id="cards">        
          <div>
            <h4>Orden de Serviço</h4>
          </div>
          <div>
            <figure>
              <img src="../../public/image/orcamento.bmp" alt="img">              
            </figure>            
          </div>
        </article>
      </RouterLink>
      <RouterLink to="">
        <article id="cards">        
          <div>
            <h4>Fornecedor</h4>
          </div>
          <div>
            <figure>
              <img src="../../public/image/fornecedores.jpeg" alt="img">              
            </figure>            
          </div>
        </article>
      </RouterLink>
      <RouterLink to="">
        <article id="cards">        
          <div>
            <h4>Projetos</h4>
          </div>
          <div>
            <figure>
              <img src="../../public/image/projetos.jpeg" alt="img">              
            </figure>            
          </div>
        </article>
      </RouterLink>
      
    </main>
  </section>
</template>

<style scoped>
main{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

div{
  display: flex;
}

#cards :nth-child(2){
  display:flex;
  flex-direction: row;
  margin: 10px;
  padding: 5px;
  align-content:center;
}

#cards{
  display:flex;
  flex-direction:column; 
  background-color: rgb(197, 195, 199);  
  align-items: center;
  border:2px solid gray;
  margin: 10px;
  padding: 10px;
  height: 300px;
  width: 400px;
}

#card-article{
  display: flex;
  flex-direction: column;
  align-items: center;
}

a #cards{
  color: white;
}

img{
  width: 100px;
  height: 150px;
  border: 2px solid gray;
  border-radius: 5px;
}


</style>