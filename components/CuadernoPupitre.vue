<template>
  <div>
    <div
      class="cuaderno"
      v-b-modal.modal-cuaderno
      v-tooltip.left-start="{
        content: 'Cuaderno',
        open: true,
        show: true
      }"
    >
      <div class="info-cuaderno pulse" v-b-modal.modal-info-cuaderno>!</div>
    </div>
    <b-modal id="modal-cuaderno" hide-header hide-footer centered size="xl">
      <div class="modal-close" @click="$bvModal.hide('modal-cuaderno')">X</div>
      <div class="modal-title">
        <strong>cuaderno Pedagógicos</strong>
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
            <b-tab title="Matrices de aprendizaje" align="center" active>
              <p class="my-4 text-center">Matrices de aprendizaje<br /></p>
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
.cuaderno {
  position: absolute;
  top: 1002px;
  left: 703px;
  width: 120px; /* Viewport-width */
  height: 120px; /* Viewport-height */
  margin: 2em auto; /* Little margin */
  background: transparent url("~assets/cuaderno-pupitre-sprite.png") 0 0
    no-repeat; /* Our sprite as the viewport background */
  animation: cuadernoAbre 1s steps(10) infinite; /* The Animation */
  /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
}

/* Animation keyframes for the sprite */
@keyframes cuadernoAbre {
  100% {
    background-position: -1200px 0;
  }
}

@keyframes cuadernoAbreMin {
  100% {
    background-position: -600px 0;
  }
}
@media (max-width: 736px) {
  .cuaderno {
    top: 510px;
    left: 380px;
    width: 60px; /* Viewport-width */
    height: 60px; /* Viewport-height */
    margin: 2em auto; /* Little margin */
    background: transparent url("~assets/cuaderno-pupitre-sprite_min.png") 0 0
      no-repeat; /* Our sprite as the viewport background */
    animation: cuadernoAbreMin 1s steps(10) infinite; /* The Animation */
  }

  .info-cuaderno {
    visibility: hidden;
  }
}
</style>
