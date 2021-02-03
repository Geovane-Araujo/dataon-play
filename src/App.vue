<template>
  <div id="app">
    <div style="margin-top: 20px"><img alt="Vue logo" class="imglogo" src="./assets/dataon-play.png"></div>
    <div class="groupbuttons">
      <b-button-group>
        <b-button to="/" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/cadastro.png"/> Início</b-button>
        <b-button to="/cadastros" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/cadastro.png"/> Cadastros</b-button>
        <b-button to="/veterinaria" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/veterinaria.png"/> Veterinária</b-button>
        <b-button to="/vendas" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/vendas.png"/> Vendas</b-button>
        <b-button to="/compras" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/compras.png"/> Compras</b-button>
        <b-button to="/servicos" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/servicos.png"/> Serviços</b-button>
        <b-button v-show="visible" to="/estoque" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/estoque.png"/> Estoque</b-button>
        <b-button to="/financeiro" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/financeiro.png"/> Financeiro</b-button>
        <b-button v-show="visible"  to="/utilitarios" style="color:#ffffff;" variant="outline-dark"><img class="icons" src="./assets/utilitarios.png"/> Utilitários</b-button>
        <b-button v-show="visible"  style="color:#ffffff;" variant="outline-dark">Minha DataOn</b-button>
      </b-button-group>
    </div>
    <div id="nav">
<!--       <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  data () {
    return {
      visible: false
    }
  }
}
</script>

<style lang="scss">
body{
    background-image: url('./assets/fundo.png');
    background-repeat: repeat-y;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  position: relative;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100vh;
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
