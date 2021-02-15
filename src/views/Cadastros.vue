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
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de clientes',
          link: 'https://www.youtube.com/embed/Vhy439WBP9A',
          title: 'Cadastro Clientes',
          dificudade: 2,
          img: 'D:\DataOn Videos\DataOn - Play\dataon-play\src\assets\imagensprincipal\CadCli.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Produtos',
          link: 'https://www.youtube.com/embed/_0lSYobz4qY',
          title: 'Cadastro de Produtos',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2017/03/01/10/03/businessman-2108029_960_720.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro e configuração de Máquinas de Cartão',
          link: 'https://www.youtube.com/embed/BYC8HKpsTuA',
          title: 'Máquinas de Cartão',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2021/01/17/11/34/payment-terminal-5924679_960_720.png'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de contas bancárias',
          link: 'https://www.youtube.com/embed/c_C6Xs1Bs1Q',
          title: 'Cadastro de Contas Bancárias',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2017/10/25/19/46/piggy-bank-2889046_960_720.jpg'
        },
        {
          id: 5,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de produtos a granel',
          link: 'https://www.youtube.com/embed/FLa9SQQ4jek',
          title: 'Cadastro de Produtos a Granel',
          dificudade: 2,
          img: 'https://i.pinimg.com/originals/ca/3d/ae/ca3daeab2e104f435658be54b6ed023e.jpg'
        }
      ]
    }
  }
}
</script>
