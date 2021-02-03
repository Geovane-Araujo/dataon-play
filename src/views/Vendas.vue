<template>
  <div class="cadastros">
    <div class="row" style="margin: 10px; justify-content:center;">
      <div class="col-sm-3"  v-for="item in cadastros" :key="item.id">
        <b-card
        :title="item.title"
        :img-src="item.img"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-3"
      >
        <b-card-text>
          {{ item.context }}
        </b-card-text>
        <b-button v-b-modal.modal-center @click="obj=item" variant="outline-dark">Assistir</b-button>
      </b-card>
      </div>
    </div>
    <b-modal id="modal-center" size="lg" centered :title="obj.title">
      <iframe :src="obj.link" type="application/x-shockwave-flash" width="760" height="500"></iframe>
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
          img: 'https://cdn.pixabay.com/photo/2014/12/21/23/51/cash-register-576181_960_720.png'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de venda de produtos no PDV',
          link: 'https://www.youtube.com/embed/TCrDhz06qKQ',
          title: 'Venda de Produtos no PDV',
          img: 'https://cdn.pixabay.com/photo/2014/12/21/23/51/cash-register-576181_960_720.png'
        }
      ]
    }
  }
}
</script>
