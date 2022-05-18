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
                <b-form-rating class="stars" id="rating-sm" size="sm" color="#ff8800" v-model="item.dificudade" stars="5" readonly></b-form-rating>
              </div>
            </template>
          </vue-horizontal-list>
        </div>
      </div>
      <div class="col-sm-12" style="margin-top: 35px">
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
                <b-form-rating class="stars" id="rating-sm" size="sm" color="#ff8800" v-model="item.dificudade"  stars="5" readonly></b-form-rating>
              </div>
            </template>
          </vue-horizontal-list>
        </div>
       </div>
       <div class="col-sm-12" style="margin-top: 35px">
          <div class="cont">
          <vue-horizontal-list :items="cadastros2" :options="options">
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
                <b-form-rating class="stars" id="rating-sm" size="sm" color="#ff8800" v-model="item.dificudade" stars="5" readonly></b-form-rating>
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
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de clientes',
          link: 'https://www.youtube.com/embed/Vhy439WBP9A',
          title: 'Cadastro Clientes',
          dificudade: 1,
          img: 'https://videos.dataon.com.br/imagensprincipal/CadCli.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Produtos',
          link: 'https://www.youtube.com/embed/_0lSYobz4qY',
          title: 'Cadastro de Produtos',
          dificudade: 3,
          img: 'https://videos.dataon.com.br/imagensprincipal/CadProd.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro e configuração de Máquinas de Cartão',
          link: 'https://www.youtube.com/embed/weULiUsECnQ',
          title: 'Máquinas de Cartão',
          dificudade: 3,
          img: 'https://videos.dataon.com.br/imagensprincipal/CadMaq.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de contas bancárias',
          link: 'https://www.youtube.com/embed/c_C6Xs1Bs1Q',
          title: 'Cadastro de Contas Bancárias',
          dificudade: 2,
          img: 'https://videos.dataon.com.br/imagensprincipal/CadCB.jpg'
        }
      ],
      cadastros1: [
        {
          id: 1,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de produtos a granel',
          link: 'https://www.youtube.com/embed/FLa9SQQ4jek',
          title: 'Cadastro de Produtos a Granel',
          dificudade: 3,
          img: 'https://videos.dataon.com.br/imagensprincipal/CadGranel.jpg'
        },
        {
          id: 2,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de usuários',
          link: 'https://www.youtube.com/embed/hz3yfpQ6rcg',
          title: 'Cadastro de usuários',
          dificudade: 1,
          img: 'https://videos.dataon.com.br/imagensprincipal/CadUsuario.jpg'
        },
        {
          id: 3,
          context: 'Neste vídeo estaremos mostrando a rotina de como cadastrar contas PIX',
          link: 'https://www.youtube.com/embed/Tuy5709yYW8',
          title: 'Cadastro de Contas PIXX',
          dificudade: 1,
          img: 'https://videos.dataon.com.br/imagensprincipal/contapix.jpg'
        },
        {
          id: 4,
          context: 'Neste vídeo estaremos mostrando a rotina de como Copiarmos Permissões de Usuário',
          link: 'https://www.youtube.com/embed/-3hoRzo2NLM',
          title: 'Cópia de Permissões de Usuário',
          dificudade: 1,
          img: 'https://videos.dataon.com.br/imagensprincipal/CopiaPermissoUsr.jpg'
        }
      ],
      cadastros2: [
        {
          id: 1,
          context: 'Neste vídeo estaremos mostrando a rotina de cadastro de Convênios no Sistema DataOn Pet',
          link: 'https://www.youtube.com/embed/k2LxAXcCcjk',
          title: 'Cadastro de Convênios',
          dificudade: 1,
          img: 'https://videos.dataon.com.br/imagensprincipal/convenio.jpg'
        }
      ]
    }
  }
}
</script>
