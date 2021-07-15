<template>
  <div>
    <div
      class="recursos"
      v-b-modal.modal-recursos
      v-tooltip.left-start="{
        content: 'Recursos',
        open: true,
        show: true
      }"
    >
      <div class="info-recursos pulse" v-b-modal.modal-info-recursos>!</div>
    </div>
    <b-modal id="modal-recursos" hide-header hide-footer centered size="xl">
      <div class="modal-close" @click="$bvModal.hide('modal-recursos')">X</div>
      <div class="modal-title">
        <strong>Recursos Pedagógicos</strong>
      </div>
      <b-container>
        <b-card no-body>
          <b-tabs
            class="mt-3"
            content-class="mt-3 mb-3"
            align="center"
            pills
            card
          >
            <b-tab title="Recursos" align="center" active>
              <p class="my-4 text-center">Recursos Pedagógicos<br /></p>
              <b-button-group>
                <a
                  href="https://www.gob.mx/aefcm/articulos/alumnas-y-alumnos-de-escuelas-publicas-de-educacion-basica?idiom=es"
                  target="_blank"
                  class="btn btn-green"
                  style="color:white"
                  >Enlace</a
                >
              </b-button-group>
            </b-tab>
          </b-tabs>
        </b-card>
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
.recursos {
  position: absolute;
  top: 302px;
  left: 1401px;
  width: 120px; /* Viewport-width */
  height: 120px; /* Viewport-height */
  margin: 2em auto; /* Little margin */
  background: transparent url("~assets/recursos-pedagogicos-sprite.png") 0 0
    no-repeat; /* Our sprite as the viewport background */
  animation: libroAbre 1s steps(12) infinite; /* The Animation */
  /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
}

/* Animation keyframes for the sprite */
@keyframes libroAbre {
  100% {
    background-position: -1440px 0;
  }
}
/* Small Animation keyframes for the sprite */
@keyframes libroAbreMin {
  100% {
    background-position: -720px 0;
  }
}

@media (max-width: 736px) {
  .recursos {
    top: 136px;
    left: 741px;

    width: 60px; /* Viewport-width */
    height: 60px; /* Viewport-height */
    margin: 2em auto; /* Little margin */
    background: transparent url("~assets/recursos-pedagogicos-sprite_min.png") 0
      0 no-repeat; /* Our sprite as the viewport background */
    animation: libroAbreMin 1s steps(12) infinite; /* The Animation */
  }

  .info-recursos {
    visibility: hidden;
  }
}
</style>
