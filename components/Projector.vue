<template>
  <div>
    <div
      class="projector"
      v-b-modal.modal-prj
      v-tooltip.left-start="{
        content: 'Videos',
        open: true,
        show: true
      }"
    >
      <div class="info-prj pulse" v-b-modal.modal-info-phone>!</div>
    </div>
    <b-modal id="modal-prj" hide-header hide-footer centered size="xl">
      <div class="modal-close" @click="$bvModal.hide('modal-prj')">X</div>
      <div class="modal-title"><strong>Videos</strong></div>
      <b-container>
        <p class="my-4 text-center">
          Tenemos videos para ti, para que en este regreso a clases desde casa
          puedas pasar un buen rato.
        </p>

        <div id="videos" class="cards">
          <div
            class="card-item"
            v-for="(video, index) in paginateVideos"
            :key="index"
          >
            <object :data="video.link"></object>
          </div>
        </div>

        <b-pagination
          v-model="currentPage"
          :total-rows="rows"
          :per-page="perPage"
          aria-controls="videos"
          align="center"
          class="mt-4 mb-4"
        >
          <template v-slot:prev-text>
            <span>Anterior</span>
          </template>
          <template v-slot:next-text>
            <span>Siguiente</span>
          </template>
        </b-pagination>

        <div class="tools">
          <!--<b-button class="btn-green" @click="hideModal">Anterior</b-button>
          <b-button class="btn-purple" @click="hideModal">Siguiente</b-button>-->
          <!--<b-button class="btn-pink" @click="$bvModal.hide('modal-prj')">Cerrar</b-button>-->
        </div>
      </b-container>
    </b-modal>

    <b-modal id="modal-info-prj" hide-header hide-footer centered size="ls">
      <div class="modal-title">
        <strong>Info</strong>
      </div>
      <b-container>
        <p class="my-4 text-center">Videos.</p>
        <div class="tools">
          <b-button class="btn-pink" @click="$bvModal.hide('modal-info-prj')"
            >Cerrar</b-button
          >
        </div>
      </b-container>
    </b-modal>
  </div>
</template>
<script>
export default {
  data() {
    return {
      perPage: 8,
      currentPage: 1,
      videos: [
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1t_4unPTIRn-D3pDN2fYcmCJR06DiDWnz/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1b6W30uG-U_9J1HdwPxEpXC8sZS_etGo1/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1p9ETk7KE7TANikMiUpaDu5Hm4mJdLFnL/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/11onN5wldrb5-c_53_rsHKlTR13GOX0qn/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1dGCIAkCT0x1xGhqnb28I2p0n_N6MG5zX/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1hP9NVLcY-PDlcuxAHSz7rcY1WEYGQsp0/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1oFw7Ei41MLh3ZQR4AqScBde5npmoqaWW/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1ZYUJNe2inXcf18xiYKvpuRNBS15skrxs/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1meJuGjGhcSLF4Yhy0QKnbYeO0VJXdX4y/preview"
        },
        {
          name: "",
          link:
            "https://drive.google.com/file/d/1zfLNPiPCaEsNbS7JgmZkN-quKsWFuVMP/preview"
        }
      ]
    };
  },
  computed: {
    rows() {
      return this.videos.length;
    },
    paginateVideos() {
      return this.videos.slice(
        (this.currentPage - 1) * this.perPage,
        this.currentPage * this.perPage
      );
    }
  },
  methods: {
    openLink(link) {
      window.open(link, "_self");
    }
  }
};
</script>
<style>
.projector {
  position: absolute;
  top: 860px;
  left: 120px;
  width: 120px; /* Viewport-width */
  height: 120px; /* Viewport-height */
  margin: 2em auto; /* Little margin */
  background: transparent url("~assets/projector-sprite.png") 0 0 no-repeat; /* Our sprite as the viewport background */
  animation: displayVideo 1s steps(10) infinite; /* The Animation */
  /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
}

/* Animation keyframes for the sprite */
@keyframes displayVideo {
  100% {
    background-position: -1200px 0;
  }
}

.info-prj {
  position: relative;
  top: -20px;
  left: -20px;
}
</style>
