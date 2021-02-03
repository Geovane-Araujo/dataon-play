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
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Produtos',
          link: 'https://www.youtube.com/embed/_0lSYobz4qY',
          title: 'Cadastro de Produtos',
          img: 'https://cdn.pixabay.com/photo/2017/03/01/10/03/businessman-2108029_960_720.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro e configuração de Máquinas de Cartão',
          link: 'https://www.youtube.com/embed/BYC8HKpsTuA',
          title: 'Cadastro e Configuração de Máquinas de Cartão',
          img: 'https://cdn.pixabay.com/photo/2021/01/17/11/34/payment-terminal-5924679_960_720.png'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de contas bancárias',
          link: 'https://www.youtube.com/embed/c_C6Xs1Bs1Q',
          title: 'Cadastro de Contas Bancárias',
          img: 'https://cdn.pixabay.com/photo/2017/10/25/19/46/piggy-bank-2889046_960_720.jpg'
        },
        {
          id: 5,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de produtos a granel',
          link: 'https://www.youtube.com/embed/FLa9SQQ4jek',
          title: 'Cadastro de Produtos a Granel',
          img: 'https://i.pinimg.com/originals/ca/3d/ae/ca3daeab2e104f435658be54b6ed023e.jpg'
        }
      ]
    }
  }
}
</script>
