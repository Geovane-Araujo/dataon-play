<template>
  <div id="app">
    <div style="margin-top: 20px"><img alt="Vue logo" class="imglogo" src="./assets/dataon-play.png"></div>
    <div class="groupbuttons">
      <b-button-group>
        <b-button to="/" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/cadastro.png"/> Início</b-button>
        <b-button to="/cadastros" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/cadastro.png"/> Cadastros</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/veterinaria.png"/> Veterinária</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/vendas.png"/> Vendas</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/compras.png"/> Compras</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/servicos.png"/> Serviços</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/estoque.png"/> Estoque</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/financeiro.png"/> Financeiro</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/utilitarios.png"/> Utilitários</b-button>
        <b-button style="color:#ffffff;" variant="outline-dark">Minha DataOn</b-button>
      </b-button-group>
    </div>
    <div id="nav">
<!--       <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.icons {
  max-width:25px;
  max-height:150px;
  width: auto;
  height: auto;
}
.imglogo {
  max-width:250px;
  max-height:150px;
  width: auto;
  height: auto;
}

.groupbuttons{
  width: 100%;
  height: 39px;
  margin-top: 20px;
  background-color: black;
}

#nav {
  padding: 30px;
}
</style>
