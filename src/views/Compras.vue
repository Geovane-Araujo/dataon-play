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
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de clientes',
          link: 'https://www.youtube.com/embed/Vhy439WBP9A',
          title: 'Cadastro Clientes',
          img: 'https://cdn.pixabay.com/photo/2016/02/07/21/03/computer-1185626_960_720.jpg'
        }
      ]
    }
  }
}
</script>
