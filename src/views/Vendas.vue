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
      cadastros: [
        {
          id: 1,
          context: 'Neste vídeo estaremos mostrando a rotina de abertura e fechamento de caixa',
          link: 'https://www.youtube.com/embed/bwYOwGFr7Bw',
          title: 'Abertura e Fechamento de Caixa',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/CaixaReg.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de venda de produtos no PDV',
          link: 'https://www.youtube.com/embed/TCrDhz06qKQ',
          title: 'Venda de Produtos no PDV',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/CaixaReg.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de venda parcelada no crédito',
          link: 'https://www.youtube.com/embed/x213ToBtXAw',
          title: 'Venda Parcelada no Crédito',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/VendaParcelada.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de como gerar crédito loja para o seu cliente',
          link: 'https://www.youtube.com/embed/jJ3PuFTRSQQ',
          title: 'Gerar Crédito Cliente',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/creditoloja.jpg'
        }
      ]
    }
  }
}
</script>
