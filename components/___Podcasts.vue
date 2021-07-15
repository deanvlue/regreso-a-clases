<template>
  <div>
    <!-- Podcasts -->
    <div
      id="podcasts"
      class="podcasts"
      v-b-modal.modal-podcasts
      v-tooltip.left-start="{
        content: 'Podcasts',
        open: true,
        show: true
      }"
    >
      <img
        class="scale"
        src="~/assets/podcasts.svg"
        alt="Podcasts"
        @mouseleave="mouseLeave"
        @mouseenter="mouseEnter"
      />
      <audio
        style="display:none"
        id="podcastsAudio"
        :src="require('@/assets/audio/podcasts.mp3')"
        controls
      ></audio>
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
    <div class="info-podcasts pulse" v-b-modal.modal-info-podcasts>!</div>
    <b-modal
      id="modal-info-podcasts"
      hide-header
      hide-footer
      centered
      size="ls"
    >
      <div class="modal-title">
        <strong>Info</strong>
      </div>
      <b-container>
        <p class="my-4 text-center">
          En esta sección podrán escuchar podcast que maestras y maestros
          especialistas han realizado sobre los temas y asignaturas de las que
          más dudas hay, así como de apoyo socioemocional para la comunidad
          educativa. Les invitamos a explorarlos y escuchar todos los que sean
          de su interés.
        </p>
        <div class="tools">
          <b-button
            class="btn-pink"
            @click="$bvModal.hide('modal-info-podcasts')"
            >Cerrar</b-button
          >
        </div>
      </b-container>
    </b-modal>
  </div>
</template>
<script>
export default {
  methods: {
    mouseEnter() {
      let podcastsAudio = $("#podcastsAudio")[0];
      podcastsAudio.play();
    },

    mouseLeave() {
      let podcastsAudio = $("#podcastsAudio")[0];
      podcastsAudio.pause();
      podcastsAudio.currentTime = 0;
    }
  }
};
</script>
<style>
.podcasts {
  width: 110px;
  height: 80px;

  top: 350px;
  left: 1600px;

  /*-moz-transform: skew(0deg, 30deg);
    -webkit-transform: skew(0deg, 30deg);
    -o-transform: skew(0deg, 30deg);
    -ms-transform: skew(0deg, 30deg);
    transform: skew(0deg, 30deg);*/
}
.podcasts img {
  width: 100%;
}
.podcasts img:hover {
  border: 3px solid #70b215;
}
.info-podcasts {
  top: 270px;
  left: 1580px;
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
  .podcasts {
    width: 180px;
    height: 140px;

    top: 495px;
    left: 2700px;
  }
  .info-podcasts {
    top: 450px;
    left: 2620px;
  }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (max-width: 1920px) {
  .podcasts {
    width: 110px;
    height: 80px;

    top: 310px;
    left: 1580px;

    /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
  }
  .info-podcasts {
    top: 270px;
    left: 1580px;
  }
}
/*
 * Medium devices (Laptops, 1680px)
 */
@media (max-width: 1680px) {
  .podcasts {
    width: 100px;
    height: 70px;

    top: 275px;
    left: 1380px;
  }
  .info-podcasts {
    top: 240px;
    left: 1380px;
  }
}
/*
 * Landscape (Tablets, 1536px)
 */
@media (max-width: 1536px) {
  .podcasts {
    width: 80px;
    height: 60px;

    top: 265px;
    left: 1265px;
  }
  .info-podcasts {
    top: 220px;
    left: 1260px;
  }
}
/*
 * Landscape (Tablets, 1024px)
 */
@media (max-width: 1024px) {
  .podcasts {
    width: 60px;
    height: 40px;

    top: 190px;
    left: 840px;
  }
  .info-podcasts {
    top: 170px;
    left: 860px;
  }
}
</style>
