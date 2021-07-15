<template>
  <div id="scene" class="scene" v-on:click="printMousePos">
    <img class="image" src="~/assets/scene.svg" width="1920" height="auto" />

    <!--Este es un modal en el que se puede poner cualquier mensaje nuevo-->
    <b-modal
      v-if="$device.isMobileOrTablet"
      ref="modal-orientation"
      id="modal-orientation"
      hide-header
      hide-footer
      centered
      size="ls"
    >
      <div class="modal-title purple text-center">
        <strong>¡Importante!</strong>
      </div>
      <b-container>
        <div class="my-4 text-center">
          <b-icon class="rotate" icon="phone" font-scale="4"></b-icon>
        </div>
        <p class="my-4 text-center">
          Para una mejor experiencia. voltea tu {{ deviceName }}
        </p>
        <div class="tools">
          <b-button
            class="btn-green"
            @click="$bvModal.hide('modal-orientation')"
            >Continuar</b-button
          >
        </div>
      </b-container>
    </b-modal>

    <slot></slot>
  </div>
</template>
<script>
import { BIcon, BIconPhone, BIconPhoneLandscape } from "bootstrap-vue";
var VueScrollTo = require("vue-scrollto");

export default {
  components: {
    BIcon,
    BIconPhone,
    BIconPhoneLandscape
  },
  data() {
    return {
      visited: false,
      windowWidth: 0,
      windowHeight: 0
    };
  },
  computed: {
    deviceName() {
      if (this.$device.isMobile) {
        return "teléfono";
      } else if (this.$device.isTabled) {
        return "tablet";
      } else {
        return "dispositivo";
      }
    },

    isPortrait() {
      return this.windowHeight > this.windowWidth;
    },

    isLandscape() {
      return this.windowHeight < this.windowWidth;
    }
  },
  methods: {
    showModal() {
      if (typeof this.$refs["modal-welcome"] !== "undefined")
        this.$refs["modal-welcome"].show();
    },

    hideModal() {
      if (typeof this.$refs["modal-welcome"] !== "undefined")
        this.$refs["modal-welcome"].hide();
    },

    getWindowWidth(event) {
      this.windowWidth = document.documentElement.clientWidth;
      this.windowHeight = document.documentElement.clientHeight;

      if (this.isPortrait && this.$device.isMobileOrTablet) {
        if (typeof this.$refs["modal-orientation"] !== "undefined")
          this.$refs["modal-orientation"].show();
      }

      if (this.isLandscape && this.$device.isMobileOrTablet) {
        if (typeof this.$refs["modal-orientation"] !== "undefined")
          this.$refs["modal-orientation"].hide();
      }
    },

    getWindowHeight(event) {
      this.windowHeight = document.documentElement.clientHeight;
    },
    printMousePos(e) {
      console.log(e);
    }
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.getWindowWidth);
    window.removeEventListener("resize", this.getWindowHeight);
  },
  mounted() {
    if (this.$device.isMobile) {
      const el = document.getElementById("chat");

      var options = {
        container: "body",
        duration: 500,
        easing: "linear",
        offset: -120,
        force: true,
        cancelable: true,
        x: true,
        y: true
      };

      this.$scrollTo(el, 500, options);
    }

    if (this.visited === false) {
      this.showModal();
    }

    this.$nextTick(function() {
      window.addEventListener("resize", this.getWindowWidth);
      window.addEventListener("resize", this.getWindowHeight);

      //Init
      this.getWindowWidth();
      this.getWindowHeight();
    });
  }
};
</script>
<style>
.scene {
  z-index: 1;
}
.scene .image {
  margin-top: 60px;
  width: 1920px;
  height: auto;
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
  .scene .image {
    width: 3280px;
  }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (max-width: 1920px) {
  .scene .image {
    width: 1920px;
  }
}
/*
 * Medium devices (Laptops, 1680px)
 */
@media (max-width: 1680px) {
  .scene .image {
    width: 1680px;
  }
}
/*
 * Landscape (Tablets, 1536px)
 */
@media (max-width: 1536px) {
  .scene .image {
    margin-top: 60px;
    width: 1536px;
  }
}
/*
 * Landscape (Tablets, 1024px)
 */
@media (max-width: 1024px) {
  .scene .image {
    margin-top: 30px;
    width: 1024px;
  }
}

@media (max-width: 812px) and (min-width: 667px) {
  .scene .image {
    margin-top: 30px;
    width: 1024px;
  }
}
</style>
