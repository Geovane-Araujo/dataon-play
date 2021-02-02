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
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Animais',
          link: 'https://www.youtube.com/embed/R-Q50WPjRpc',
          title: 'Cadastro de Animais',
          img: 'https://cdn.pixabay.com/photo/2017/11/14/13/06/kitty-2948404_960_720.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Produtos',
          link: 'https://www.youtube.com/embed/_0lSYobz4qY',
          title: 'Cadastro de Produtos',
          img: 'https://cdn.pixabay.com/photo/2017/03/01/10/03/businessman-2108029_960_720.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Cirurgias',
          link: 'https://www.youtube.com/embed/8I5tePqt2GU',
          title: 'Cadastro de Cirurgias',
          img: 'https://cdn.pixabay.com/photo/2020/08/03/09/43/medical-5459650_960_720.png'
        },
        {
          id: 5,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de vacinas',
          link: 'https://www.youtube.com/embed/wANcIV_CIVU',
          title: 'Cadastro de Vacinas',
          img: 'https://cdn.pixabay.com/photo/2016/09/16/19/17/injection-1674900_960_720.png'
        },
        {
          id: 6,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de exames',
          link: 'https://www.youtube.com/embed/-K2u8xB62pA',
          title: 'Cadastro Exames',
          img: 'https://cdn.pixabay.com/photo/2019/08/13/08/15/analysis-4402809_960_720.jpg'
        },
        {
          id: 7,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Pacotes de Serviço/Banho e Tosa',
          link: 'https://www.youtube.com/embed/XZFQAoBeiAg',
          title: 'Cadastro Pacotes de Serviço/Banho e Tosa',
          img: 'https://cdn.pixabay.com/photo/2015/10/16/01/08/dog-990304_960_720.jpg'
        },
        {
          id: 8,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro e configuração de Máquinas de Cartão',
          link: 'https://www.youtube.com/embed/BYC8HKpsTuA',
          title: 'Cadastro e Configuração de Máquinas de Cartão',
          img: 'https://cdn.pixabay.com/photo/2021/01/17/11/34/payment-terminal-5924679_960_720.png'
        },
        {
          id: 9,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de consultas',
          link: 'https://www.youtube.com/embed/CfuQab6QhI8',
          title: 'Cadastro de Consultas',
          img: 'https://cdn.pixabay.com/photo/2018/06/09/17/37/doctor-3464798_960_720.jpg'
        },
        {
          id: 10,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de internações',
          link: 'https://www.youtube.com/embed/4UFiiUUJVwQ',
          title: 'Cadastro de Internações',
          img: 'https://cdn.pixabay.com/photo/2012/04/02/12/50/ambulance-24405_960_720.png'
        },
        {
          id: 11,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro taxi pet',
          link: 'https://www.youtube.com/embed/yykc5RxFNiM',
          title: 'Cadastro de Taxi Pet',
          img: 'https://cdn.pixabay.com/photo/2016/11/21/14/20/automobile-1845650_960_720.jpg'
        },
        {
          id: 12,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro Creche/Day Care Pet',
          link: 'https://www.youtube.com/embed/KQlTDTR9mFI',
          title: 'Cadastro de Creche/Day Care Pet',
          img: 'https://cdn.pixabay.com/photo/2016/10/19/12/50/happy-1752901_960_720.jpg'
        },
        {
          id: 13,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de contas bancárias',
          link: 'https://www.youtube.com/embed/c_C6Xs1Bs1Q',
          title: 'Cadastro de Contas Bancárias',
          img: 'https://cdn.pixabay.com/photo/2017/10/25/19/46/piggy-bank-2889046_960_720.jpg'
        }
      ]
    }
  }
}
</script>
