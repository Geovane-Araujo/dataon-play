<template>
  <div class="cadastros">
    <h3 style="text-align:left;margin-bottom:0px;margin-left:30px">Sequência Recomendada</h3>
    <div class="cont">
      <vue-horizontal-list :items="cadastros" :options="options">
        <template v-slot:default="{ item }">
          <div class="master">
            <div class="image-container">
              <button v-b-modal.modal-center @click="obj=item"><img class="img" :src="item.img"/></button>
            </div>
            <div class="subtitle">
              <div>Sequência</div>
              <div>{{ item.id + "/" + cadastros.length }}</div>
            </div>
            <h4 style="text-align:left;">{{ item.title }}</h4>
            <p style="text-align:left;" >{{ item.context }}</p>
            <h6 style="text-align:left;font-size: 10px" >Dificuldade</h6>
            <b-form-rating class="stars" id="rating-sm" size="sm" color="#ff8800" v-model="item.dificudade" stars="5"></b-form-rating>
          </div>
        </template>
      </vue-horizontal-list>
    </div>
    <b-modal id="modal-center" size="lg" centered :title="obj.title">
      <iframe allowfullscreen="allowfullscreen" :src="obj.link" type="application/x-shockwave-flash" width="760" height="500"></iframe>
    </b-modal>
  </div>
</template>

<script>

export default {
  data () {
    return {
      obj: {
        context: '',
        link: '',
        title: '',
        img: ''
      },
      options: {
        responsive: [
          { end: 576, size: 1 },
          { start: 576, end: 768, size: 2 },
          { start: 768, end: 992, size: 3 },
          { size: 4 }
        ]
      },
      cadastros: [
        {
          id: 1,
          context: 'Neste vídeo estaremos mostrando a rotina de gerar e receber duplicatas',
          link: 'https://www.youtube.com/embed/6d20NTLiBc4',
          title: 'Gerar e receber duplicatas',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/receitas.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de receber e reparcelar duplicatas',
          link: 'https://www.youtube.com/embed/Tv6OCnZN49E',
          title: 'Receber e Reparcelar Duplicatas',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/receitas.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de como gerar e quitar duplicatas',
          link: 'https://www.youtube.com/embed/9GZhlBWJBFo',
          title: 'Gerar e quitar duplicatas',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/despesas.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando o funcionamento da guia meu negócio',
          link: 'https://www.youtube.com/embed/L3M_Azu52-k',
          title: 'Meu Negócio',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/MeuNegocio.jpg'
        },
        {
          id: 5,
          context: 'Neste vídeo estaremos mostrando o a rotina de estornar e excluir duplicatas no sistema DataOn Pet',
          link: 'https://www.youtube.com/embed/txYiLRJOo3k',
          title: 'Estorno/Exclusão de Duplicatas',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/estornoexclusao.jpg'
        },
        {
          id: 6,
          context: 'Neste vídeo estaremos mostrando o a rotina de cadastrar, listar e gerar pontos do programa fidelidade',
          link: 'https://www.youtube.com/embed/kJRy5YFg-Vw',
          title: 'Programa Fidelidade',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/programafidelidade.jpg'
        }
      ]
    }
  }
}
</script>
