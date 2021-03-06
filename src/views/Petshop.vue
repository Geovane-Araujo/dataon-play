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
          context: 'Neste vídeo estaremos mostrando a rotina de faturamento através do atendimento',
          link: 'https://www.youtube.com/embed/NiWrDu9_Ysk',
          title: 'Faturando um Atendimento',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/Fatura_Atendimento.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de agendar e executar um Pacote de Serviços ou Banho e Tosa',
          link: 'https://www.youtube.com/embed/G9Gd5ldIZXc',
          title: 'Agendar e Executar Banho e Tosa',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2016/07/16/08/53/sphynx-1521190_960_720.jpg'
        }
      ]
    }
  }
}
</script>
