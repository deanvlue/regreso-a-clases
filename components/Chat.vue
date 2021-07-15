<template>
  <div>
    <div
      ref="chat"
      id="chat"
      class="cellphone"
      v-b-modal.modal-cellphone
      v-tooltip.top-start="{
        content: 'Chat',
        open: true,
        show: true
      }"
    >
      <img
        class="scale"
        src="~/assets/chat.png"
        alt="Chat"
        @mouseleave="mouseLeave"
        @mouseenter="mouseEnter"
      />
      <audio
        style="display:none"
        id="chatAudio"
        :src="require('@/assets/audio/chat.mp3')"
        controls
      ></audio>
    </div>
    <b-modal id="modal-cellphone" hide-header hide-footer centered size="xl">
      <div class="modal-close" @click="$bvModal.hide('modal-cellphone')">X</div>
      <div class="modal-title">
        <strong>Chat</strong>
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
            <b-tab title="Inscripciones" align="center" active>
              <p class="my-4 text-center">
                ¿Necesitas ayuda? <br />
                Sí la ayuda que requiere se relaciona con inscripciones, dé clic
                en el siguiente enlace.
              </p>
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
            <b-tab title="Consulta de correo electrónico" align="center">
              <p class="my-4 text-center">
                Sí la ayuda que requiere se relaciona con la consulta, alta o
                reseteo de contraseña del correo electrónico, dé clic en el
                siguiente enlace.
              </p>
              <b-button-group>
                <a
                  href="https://www.aprendeencasa.mx/aprende-en-casa/niveles/index.html"
                  target="_blank"
                  class="btn btn-green"
                  style="color:white"
                  >Enlace</a
                >
              </b-button-group>
            </b-tab>
            <b-tab title="Apoyo pedagógico" align="center">
              <p class="my-4 text-center"></p>
              <iframe
                src="https://tmc-chat.aefcm.gob.mx/gobMxPreinsChat/jsp/GobMxPreinsChat/"
                title="Chat"
                width="100%"
                height="600"
                frameBorder="0"
              >
                <p>Tu navegador no soporta iframes.</p>
              </iframe>
            </b-tab>
          </b-tabs>
        </b-card>
      </b-container>
    </b-modal>
    <div class="info-cellphone pulse" v-b-modal.modal-info-cellphone>!</div>
    <b-modal
      id="modal-info-cellphone"
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
          Con gusto podemos atender sus dudas o darles acompañamiento por
          nuestro chat en tiempo real,
          <button
            ref="chat"
            id="chat"
            v-b-modal.modal-cellphone
            v-tooltip.top-start="{
              content: 'Chat',
              open: true,
              show: true
            }"
            class="btn btn-primary btn-green"
          >
            da clic aquí
          </button>
          y en un momento una maestra o maestro le atenderá.
        </p>
        <div class="tools">
          <b-button
            class="btn-pink"
            @click="$bvModal.hide('modal-info-cellphone')"
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
      let chatAudio = $("#chatAudio")[0];
      chatAudio.play();
    },

    mouseLeave() {
      let chatAudio = $("#chatAudio")[0];
      chatAudio.pause();
      chatAudio.currentTime = 0;
    }
  }
};
</script>
<style>
.cellphone {
  width: 170px;
  height: 160px;

  top: 670px;
  left: 820px;
}
.cellphone img {
  width: 100%;
}
.cellphone img:hover {
  border: 3px solid #ff7200;
}
.info-cellphone {
  top: 620px;
  left: 970px;
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
  .cellphone {
    width: 280px;
    height: 260px;

    top: 1100px;
    left: 1380px;
  }
  .info-cellphone {
    top: 1040px;
    left: 1660px;
  }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (max-width: 1920px) {
  .cellphone {
    width: 170px;
    height: 160px;

    top: calc(651px - 170px);
    left: 61px;
  }
  .info-cellphone {
    top: 490px;
    left: 200px;
  }
}
/*
 * Medium devices (Laptops, 1680px)
 */
@media (max-width: 1680px) {
  .cellphone {
    width: 150px;
    height: 140px;

    top: 590px;
    left: 710px;
  }
  .info-cellphone {
    top: 540px;
    left: 830px;
  }
}
/*
 * Landscape (Tablets, 1536px)
 */
@media (max-width: 1536px) {
  .cellphone {
    width: 130px;
    height: 120px;

    top: 500px;
    left: 650px;
  }
  .info-cellphone {
    top: 500px;
    left: 770px;
  }
}
/*
 * Landscape (Tablets, 1024px)
 */
@media (max-width: 1024px) {
  .cellphone {
    width: 100px;
    height: 90px;

    top: 340px;
    left: 430px;
  }
  .info-cellphone {
    top: 330px;
    left: 510px;
  }
}

@media (max-width: 736px) {
  .cellphone {
    width: 100px;
    height: 90px;

    top: 250px;
    left: 40px;
  }
  .info-cellphone {
    visibility: hidden;
  }
}
</style>
