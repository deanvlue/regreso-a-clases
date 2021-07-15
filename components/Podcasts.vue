<template>
  <div>
    <div
      class="bocinas"
      v-b-modal.modal-podcasts
      v-tooltip.left-start="{
        content: 'Podcasts',
        open: true,
        show: true
      }"
    >
      <div class="info-podcasts pulse" v-b-modal.modal-info-podcasts>!</div>
    </div>
    <b-modal id="modal-podcasts" hide-header hide-footer centered size="ls">
      <div class="modal-close" @click="$bvModal.hide('modal-podcasts')">X</div>
      <div class="modal-title purple">
        <strong>Podcasts</strong>
      </div>
      <b-container>
        <p class="my-4 text-center">
          Escucha todos los Podcast que tenemos para ti:
        </p>
        <p class="my-4 text-center">
          <strong>01 - Aprendiendo desde casa</strong>
        </p>
        <p class="my-4 text-center">
          <img
            src="~/assets/audio.png"
            style="max-width: 230px"
            width="100%"
            alt="Audio"
          />
        </p>
        <p class="my-4 text-center">
          <img
            src="~/assets/controls.png"
            style="max-width: 372px"
            width="100%"
            alt="Audio"
          />
        </p>
        <div class="tools">
          <b-button class="btn-green">Anterior</b-button>
          <b-button class="btn-purple">Siguiente</b-button>
          <!--<b-button class="btn-pink" @click="$bvModal.hide('modal-podcasts')">Cerrar</b-button>-->
        </div>
      </b-container>
    </b-modal>
  </div>
</template>
<script>
export default {
  methods: {}
};
</script>
<style>
.bocinas {
  position: absolute;
  top: 200px;
  left: 730px;
  width: 120px; /* Viewport-width */
  height: 120px; /* Viewport-height */
  margin: 2em auto; /* Little margin */
  background: transparent url("~assets/bocina-sprite.png") 0 0 no-repeat; /* Our sprite as the viewport background */
  animation: bocinasRuido 1s steps(6) infinite; /* The Animation */
  /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
}

/* Animation keyframes for the sprite */
@keyframes bocinasRuido {
  100% {
    background-position: -720px 0;
  }
}

@keyframes bocinasRuidoMin {
  100% {
    background-position: -360px 0;
  }
}

@media (max-width: 736px) {
  .bocinas {
    top: 75px;
    left: 400px;
    width: 60px; /* Viewport-width */
    height: 60px; /* Viewport-height */
    margin: 2em auto; /* Little margin */
    background: transparent url("~assets/bocina-sprite_min.png") 0 0 no-repeat; /* Our sprite as the viewport background */
    animation: bocinasRuidoMin 1s steps(6) infinite; /* The Animation */
  }
  .info-podcasts {
    visibility: hidden;
  }
}
</style>
