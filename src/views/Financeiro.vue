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
          context: 'Neste vídeo estaremos mostrando a rotina de como gerar e quitar duplicatas',
          link: 'https://www.youtube.com/embed/9GZhlBWJBFo',
          title: 'Gerar e quitar duplicatas',
          img: 'https://www.google.com/url?sa=i&url=https%3A%2F%2Falpinopolis.mg.gov.br%2Fcategory%2Ftransparencia%2Fdespesas%2F&psig=AOvVaw3xs9aopdAh1zgnbddZB86P&ust=1612442375050000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCPi5v47eze4CFQAAAAAdAAAAABAE'
        }
      ]
    }
  }
}
</script>
