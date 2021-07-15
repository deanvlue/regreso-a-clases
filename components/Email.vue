<template>
  <div>
    <div
      class="email"
      v-b-modal.modal-email
      v-tooltip.left-start="{
        content: 'email',
        open: true,
        show: true
      }"
    >
      <div class="info-email pulse" v-b-modal.modal-info-email>!</div>
    </div>
    <b-modal id="modal-email" hide-header hide-footer centered size="xl">
      <div class="modal-close" @click="$bvModal.hide('modal-email')">X</div>
      <div class="modal-title">
        <strong>¿Necesitas&nbsp;Ayuda?</strong>
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
            <b-tab
              title="Apoyo pedagógico"
              align="center"
              @click="$bvModal.show('modal-email-2')"
            >
            </b-tab>
          </b-tabs>
        </b-card>
      </b-container>
    </b-modal>
    <b-modal id="modal-email-2" hide-header hide-footer centered size="ls">
      <div class="modal-close" @click="$bvModal.hide('modal-email-2')">X</div>
      <div class="modal-title blue">
        <strong>¿Necesitas&nbsp;Ayuda?</strong>
      </div>
      <b-container>
        <p class="my-4 text-center">
          Selecciona el nivel y posteriormente el grado al que deseas consultar
          tus dudas.
        </p>
        <b-card no-body>
          <b-tabs
            class="mt-3"
            content-class="mt-3 mb-3"
            align="center"
            pills
            card
          >
            <b-tab title="Preescolar/inicial" align="center" active>
              <b-button-group>
                <a
                  href="https://tmcpre.aefcm.gob.mx/preescolar/index.php?a=add&category=1"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >1º</a
                >
                <a
                  href="https://tmcpre.aefcm.gob.mx/preescolar/index.php?a=add&category=2"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >2º</a
                >
                <a
                  href="https://tmcpre.aefcm.gob.mx/preescolar/index.php?a=add&category=3"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >3º</a
                >
              </b-button-group>
            </b-tab>
            <b-tab title="Primaria" align="center">
              <b-button-group>
                <a
                  href="https://tmcpri.aefcm.gob.mx/primaria/index.php?a=add&category=1"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >1º</a
                >
                <a
                  href="https://tmcpri.aefcm.gob.mx/primaria/index.php?a=add&category=2"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >2º</a
                >
                <a
                  href="https://tmcpri.aefcm.gob.mx/primaria/index.php?a=add&category=3"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >3º</a
                >
              </b-button-group>
              <b-button-group class="mt-1">
                <a
                  href="https://tmcpri.aefcm.gob.mx/primaria/index.php?a=add&category=4"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >4º</a
                >
                <a
                  href="https://tmcpri.aefcm.gob.mx/primaria/index.php?a=add&category=5"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >5º</a
                >
                <a
                  href="https://tmcpri.aefcm.gob.mx/primaria/index.php?a=add&category=6"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >6º</a
                >
              </b-button-group>
            </b-tab>
            <b-tab title="Secundaria" align="center">
              <b-button-group>
                <a
                  href="https://tmcsec.aefcm.gob.mx/secundaria/index.php?a=add"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >1º</a
                >
                <a
                  href="https://tmcsec.aefcm.gob.mx/secundaria/index.php?a=add"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >2º</a
                >
                <a
                  href="https://tmcsec.aefcm.gob.mx/secundaria/index.php?a=add"
                  target="_blank"
                  class="btn btn-info mr-1"
                  >3º</a
                >
              </b-button-group>
            </b-tab>
          </b-tabs>
        </b-card>
        <div class="tools">
          <a
            class="btn btn-green"
            style="color:white"
            @click="$bvModal.hide('modal-email-2')"
            >Aceptar</a
          >
          <!--<b-button class="btn-pink" @click="$bvModal.hide('modal-email')">Cerrar</b-button>-->
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
.email {
  position: absolute;
  top: 70px;
  left: 1630px;
  width: 60px; /* Viewport-width */
  height: 60px; /* Viewport-height */
  margin: 2em auto; /* Little margin */
  background: transparent url("~assets/email-sprite.png") 0 0 no-repeat; /* Our sprite as the viewport background */
  animation: emailAbre 1s steps(7) infinite; /* The Animation */
  /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
}

/* Animation keyframes for the sprite */
@keyframes emailAbre {
  100% {
    background-position: -420px 0;
  }
}
.info-email {
  position: relative;
  top: -30px;
  left: -30px;
}

@media (max-width: 736px) {
  .email {
    top: 12px;
    left: 850px;
    width: 60px; /* Viewport-width */
    height: 60px; /* Viewport-height */
    margin: 2em auto; /* Little margin */
    background: transparent url("~assets/email-sprite.png") 0 0 no-repeat; /* Our sprite as the viewport background */
    animation: emailAbre 1s steps(7) infinite; /* The Animation */
  }

  .info-email {
    visibility: hidden;
  }
}
</style>
