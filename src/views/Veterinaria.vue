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
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Animais',
          link: 'https://www.youtube.com/embed/R-Q50WPjRpc',
          title: 'Cadastro de Animais',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2017/11/14/13/06/kitty-2948404_960_720.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Cirurgias',
          link: 'https://www.youtube.com/embed/8I5tePqt2GU',
          title: 'Cadastro de Cirurgias',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2020/08/03/09/43/medical-5459650_960_720.png'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de vacinas',
          link: 'https://www.youtube.com/embed/wANcIV_CIVU',
          title: 'Cadastro de Vacinas',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2016/09/16/19/17/injection-1674900_960_720.png'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de exames',
          link: 'https://www.youtube.com/embed/-K2u8xB62pA',
          title: 'Cadastro Exames',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2019/08/13/08/15/analysis-4402809_960_720.jpg'
        },
        {
          id: 5,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Pacotes de Serviço/Banho e Tosa',
          link: 'https://www.youtube.com/embed/XZFQAoBeiAg',
          title: 'Cadastro Pacotes de Serviço/Banho e Tosa',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2015/10/16/01/08/dog-990304_960_720.jpg'
        },
        {
          id: 6,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de consultas',
          link: 'https://www.youtube.com/embed/CfuQab6QhI8',
          title: 'Cadastro de Consultas',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2018/06/09/17/37/doctor-3464798_960_720.jpg'
        },
        {
          id: 7,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de internações',
          link: 'https://www.youtube.com/embed/4UFiiUUJVwQ',
          title: 'Cadastro de Internações',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2012/04/02/12/50/ambulance-24405_960_720.png'
        },
        {
          id: 8,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro taxi pet',
          link: 'https://www.youtube.com/embed/yykc5RxFNiM',
          title: 'Cadastro de Taxi Pet',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2016/11/21/14/20/automobile-1845650_960_720.jpg'
        },
        {
          id: 9,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro Creche/Day Care Pet',
          link: 'https://www.youtube.com/embed/KQlTDTR9mFI',
          title: 'Cadastro de Creche/Day Care Pet',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2016/10/19/12/50/happy-1752901_960_720.jpg'
        },        
      ]
    }
  }
}
</script>
