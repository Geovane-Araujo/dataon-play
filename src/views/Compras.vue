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
          context: 'Neste vídeo estaremos mostrando a rotina de importação de notas manualmente',
          link: 'https://www.youtube.com/embed/VoJlw_i1yyM',
          title: 'Importação de XML Manual',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/ImpManual.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de importação de notas diretamente da SEFAZ',
          link: 'https://www.youtube.com/embed/HPu3SPlpJ6o',
          title: 'Importação de XML direto da SEFAZ',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/rastreioXML.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de como Gerar Nota Devolução de Compras no sistema DataOn Pet.',
          link: 'https://www.youtube.com/embed/JKumY_RZ3lM',
          title: 'Notas Devolução de Compras',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/DevolucaoCompras.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de como Cadastrar uma nota de Compras/Entrada no sistema DataOn Pet.',
          link: 'https://www.youtube.com/embed/WQ-BkTWPaVw',
          title: 'Notas de Compra/Entrada',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/NotaEntrada.jpg'
        }
      ]
    }
  }
}
</script>
