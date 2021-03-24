<template>
  <div class="cadastros">
    <h3 style="text-align:left;margin-bottom:0px;margin-left:30px">Sequência Recomendada</h3>
    <div class="row">
      <div class="col-sm-12">
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
      </div>
      <div class="col-sm-12" style= "margin-top 35px">
        <div class="cont">
          <vue-horizontal-list :items="cadastros1" :options="options">
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
      </div>
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
          context: 'Neste vídeo estaremos mostrando a rotina para cadastro, configuração e utilização de mensagens por whatsapp',
          link: 'https://www.youtube.com/embed/7rX_S0qSo3E',
          title: 'Modelos Whatsapp',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/Whatsapp.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina para configurar e gerar XML de fechamento fiscal mensal',
          link: 'https://www.youtube.com/embed/0gduHTuRu1k',
          title: 'Automação - Fechamento Fiscal mensal',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/fechamentofiscal.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina para configurar e utilizar os modelos de documentos.',
          link: 'https://www.youtube.com/embed/R9ot-HwaEt8',
          title: 'Modelos Documentos',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/modelodocumentos.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina para configurar e utilizar os modelos de SMS.',
          link: 'https://www.youtube.com/embed/5Zt4pWVVBWw',
          title: 'Modelos SMS',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/addsms.jpg'
        }
      ],
      cadastros1: [
        {
          id: 1,
          context: 'Neste vídeo estaremos mostrando a rotina de como utilizar os atalhos no Sistema DataOn Pet para facilitar o seu dia-a-dia.',
          link: 'https://www.youtube.com/embed/eZzzjBl8BTk',
          title: 'Atalhos DataOn Pet',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/atalhos.jpg'
        }
      ]
    }
  }
}
</script>
