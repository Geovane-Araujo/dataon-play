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
          context: 'Neste vídeo estaremos mostrando a rotina de gerar e receber duplicatas',
          link: 'https://www.youtube.com/embed/6d20NTLiBc4',
          title: 'Gerar e receber duplicatas',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2013/07/12/14/07/bag-147782_960_720.png'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de receber e reparcelar duplicatas',
          link: 'https://www.youtube.com/embed/Tv6OCnZN49E',
          title: 'Receber e Reparcelar Duplicatas',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2013/07/12/14/07/bag-147782_960_720.png'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de como gerar e quitar duplicatas',
          link: 'https://www.youtube.com/embed/9GZhlBWJBFo',
          title: 'Gerar e quitar duplicatas',
          dificudade: 2,
          img: 'https://www.arceburgo.mg.gov.br/wp-content/uploads/2017/07/despesas.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando o funcionamento da guia meu negócio',
          link: 'https://www.youtube.com/embed/L3M_Azu52-k',
          title: 'Meu Negócio',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2016/11/03/11/57/accountant-1794122_960_720.png'
        }
        {
          id: 5,
          context: 'Neste vídeo estaremos mostrando o a rotina de estornar e excluir duplicatas no sistema DataOn Pet',
          link: 'https://www.youtube.com/embed/txYiLRJOo3k',
          title: 'Estorno/Exclusão de Duplicatas',
          dificudade: 2,
          img: 'https://cdn.pixabay.com/photo/2018/10/01/22/27/arrows-3717468_960_720.png'
        }
      ]
    }
  }
}
</script>
