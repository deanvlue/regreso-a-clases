<template>
  <div>
    <div
      id="whiteboard"
      @click="openLink('https://laescuelaencasa.mx/escuela-en-casa/acceso.html')"
      class="whiteboard"
            v-tooltip.top="{
            content: 'La escuela en casa',
            open: true,
            show: true
        }">
            <audio style="display:none" id="wbAudio" :src="require('@/assets/audio/whiteboard.mp3')" controls></audio>
        </div>
        <div class="info-wb pulse" v-b-modal.modal-info-wb>!</div>
            <b-modal id="modal-info-wb" hide-header hide-footer centered size="ls">
      <div class="modal-title">
        <strong>Info</strong>
      </div>
      <b-container>
        <p class="my-4 text-center">La escuela en casa.</p>
        <div class="tools">
          <b-button class="btn-pink" @click="$bvModal.hide('modal-info-wb')">Cerrar</b-button>
        </div>
      </b-container>
    </b-modal>
  </div>
</template>
<script>
export default {
  data() {
    return{
      ok: 1,
    }
  },
  computed: {
  
  },
  methods: {
    openLink(link){
      window.open(link, "_self")
    }
  }
};
</script>
<style>
.whiteboard {
    background: url("~assets/blackboard.svg");
    background-repeat: no-repeat;
    background-size: contain;

  top: 460px;
  left: 900px;
}
.whiteboard:hover {
    background: url("~assets/blackboard_hover.svg");
    background-repeat: no-repeat;
    background-size: cover;
}
.info-wb {
  top: 460px;
  left: 910px;
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
    .whiteboard{
        width: 142px;
        height: 400px;
        top: 445px;
        left: 1595px;
    }
    .whiteboard:hover {
        width: 182px;
        height: 230px;
        top: 445px;
        left: 1595px;
    }
    .info-wb {
        top: 870px;
        left: 1380px;
    }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (min-width: 1681px) and (max-width: 1920px) {
  .whiteboard{
        width: 182px;
        height: 420px;
        top: 410px;
        left: 916px;
    }
    .whiteboard:hover {
        width: 182px;
        height: 230px;
        top: 410px;
        left: 916px;
    }
    .info-wb {
        top: 380px;
        left: 1050px;
    }
}
/*
 * Medium devices (Laptops, 1680px)
 */
@media (min-width: 1535px) and (max-width: 1680px) { 
    .whiteboard {
        width: 142px;
        height: 168px;
        top: 390px;
        left: 818px;
    }
    .whiteboard:hover {
        width: 142px;
        height: 168px;
        top: 390px;
        left: 818px;
    }
    .info-wb {
      top: 326px;
      left: 910px;
    }
}
/*
 * Landscape (Tablets, 1536px)
 */
@media (min-width: 1025px) and (max-width: 1536px) { 
    .whiteboard {
        width: 142px;
        height: 163px;
        top: 352px;
        left: 748px;
    }
    .whiteboard:hover {
        width: 142px;
        height: 163px;
        top: 352px;
        left: 748px;
    }
    .info-wb {
      top: 306px;
      left: 833px;
    }
}
/*
 * Landscape (Tablets, 1024px)
 */
@media (min-width: 813px) and (max-width: 1024px) { 
    .whiteboard {
        width: 98px;
        height: 200px;
        top: 210px;
        left: 496px;
    }
    .whiteboard:hover {
        width: 98px;
        height: 124px;
        top: 210px;
        left: 496px;
    }
    .info-wb {
      top: 190px;
      left: 557px;
    }
}

@media  (min-width: 667px) and (max-width: 812px) { 
  .whiteboard{
        width: 80px;
        height: 120px;
        top: 230px;
        left: 496px;
    }
    .whiteboard:hover {
        width: 80px;
        height: 120px;
        top: 230px;
        left: 496px;
    }
    .info-wb {
  top: 203px;
  left: 550px;
}
}
</style>