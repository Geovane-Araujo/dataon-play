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
          context: 'Neste vídeo estaremos mostrando a rotina de gerar e receber duplicatas',
          link: 'https://www.youtube.com/embed/6d20NTLiBc4',
          title: 'Gerar e receber duplicatas',
          img: 'https://cdn.pixabay.com/photo/2013/07/12/14/07/bag-147782_960_720.png'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de receber e reparcelar duplicatas',
          link: 'https://www.youtube.com/embed/Tv6OCnZN49E',
          title: 'Receber e Reparcelar Duplicatas',
          img: 'https://cdn.pixabay.com/photo/2013/07/12/14/07/bag-147782_960_720.png'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de como gerar e quitar duplicatas',
          link: 'https://www.youtube.com/embed/9GZhlBWJBFo',
          title: 'Gerar e quitar duplicatas',
          img: 'https://www.arceburgo.mg.gov.br/wp-content/uploads/2017/07/despesas.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando o funcionamento da guia meu negócio',
          link: 'https://www.youtube.com/embed/L3M_Azu52-k',
          title: 'Meu Negócio',
          img: 'https://cdn.pixabay.com/photo/2016/11/03/11/57/accountant-1794122_960_720.png'
        }
      ]
    }
  }
}
</script>
