<template>
    <div>
        <!-- Phone -->
    <div
      class="phone"
      v-b-modal.modal-phone
      v-tooltip.left-start="{
        content: 'Teléfono',
        open: true,
        show: true
      }"
    >
      <div class="info-phone pulse" v-b-modal.modal-info-phone>!</div>
    </div>
        <b-modal id="modal-phone" hide-header hide-footer centered size="lg">
            <div class="modal-close" @click="$bvModal.hide('modal-phone')">X</div>
            <div class="modal-title"><strong>Contáctanos</strong></div>
            <b-container>
                <b-row>
                    <b-col> <p class="my-4 text-center">Haznos saber cualquier duda que tengas a través de nuestras líneas telefónicas</p></b-col>
                </b-row>
                <b-row>
                    <b-col>
                                        <div class="p-1 mt-2 bg-phone-preescolar">
                    <h2 class="my-4 text-center">Preescolar</h2>
                    <p class="my-4 text-center"><a class="tel" href="tel:5536018720">55 3601 8720</a></p>
                </div>
                    </b-col>
                    <b-col>
                                       <div class="p-1 mt-2 bg-phone-primaria">
                    <h2 class="my-4 text-center">Primaria</h2>
                    <p class="my-4 text-center"><a class="tel" href="tel:5541720413">55 4172 0413</a></p>
                </div>
                    </b-col>
                    <b-col>
                                        <div class="p-1 mt-2 bg-phone-secundaria">
                    <h2 class="my-4 text-center">Secundaria</h2>
                    <p class="my-4 text-center"><a class="tel" href="tel:5536017123">55 3601 7123</a></p>
                    <p class="my-4 text-center">Reproducción de menú con con 4 materias:</p>
                    <ul class="my-4" style="list-style-type: none;">
                        <li>1. Matemáticas</li>
                        <li>2. Ciencias</li>
                        <li>3. Español</li>
                        <li>4. Otra asignatura</li>
                    </ul>
                </div>
                    </b-col>

                </b-row>
                <b-row>
                    <b-col>
                                        <div class="tools">
                    <b-button class="btn-green" @click="$bvModal.hide('modal-phone')">Aceptar</b-button>
                </div>
                    </b-col>

                </b-row>

            </b-container>
        </b-modal>
        <b-modal id="modal-info-phone" hide-header hide-footer centered size="ls">
            <div class="modal-title"><strong>Contáctanos</strong></div>
            <b-container>
                <p class="my-4">
                Con gusto una maestra o un maestro atenderá sus dudas, los números telefónicos de atención son: <br />
                
                <ul>
                    <li>
                    Educación Inicial y Preescolar: <a class="tel" href="tel:5536018720">55 3601 8720</a>
                    </li>
                    <li>
                    Educación Primaria: <a class="tel" href="tel:5541720413">55 4172 0413</a>
                    </li>
                    <li>
                        Educación Secundaria: <a class="tel" href="tel:5536017123">55 3601 7123</a>
                    </li>

                </ul>
                    Horario de atención es de lunes a viernes de 8:00 am a 8:00 pm

                </p>
                <div class="tools">
                    <b-button class="btn-pink" @click="$bvModal.hide('modal-info-phone')">Cerrar</b-button>
                </div>
            </b-container>
            
        </b-modal>
    </div>
</template>
<script>
export default {
  data: function(){
    return
  }
};
</script>
<style>
.phone {
  position: absolute;
  top: 130px;
  left: 1700px;
  width: 60px; /* Viewport-width */
  height: 60px; /* Viewport-height */
  margin: 2em auto; /* Little margin */
  background: transparent url("~assets/telefono-sprite.png") 0 0 no-repeat; /* Our sprite as the viewport background */
  animation: phoneRing 1s steps(10) infinite; /* The Animation */
  /*-moz-transform: skew(0deg, 30deg);
        -webkit-transform: skew(0deg, 30deg);
        -o-transform: skew(0deg, 30deg);
        -ms-transform: skew(0deg, 30deg);
        transform: skew(0deg, 30deg);*/
}

/* Animation keyframes for the sprite */
@keyframes phoneRing {
  100% {
    background-position: -600px 0;
  }
}
.info-phone {
  position: relative;
  top: -20px;
  left: -20px;
}

.bg-phone-preescolar{
  background: #6C49B811;
  border-radius: 20px;

}

.bg-phone-preescolar a{
  color: #6C49B8;

}

.bg-phone-primaria{
  background: #17C3B211;
  border-radius: 20px;

}
.bg-phone-primaria a {
  color: #17C3B2;

}


.bg-phone-secundaria{
  background: #B22F6511;
  border-radius: 20px;

}


@media (max-width: 736px){
    .phone {
    top: 32px;
    left: 890px;
    width: 60px; /* Viewport-width */
    height: 60px; /* Viewport-height */
    }
    .info-phone{
      visibility: hidden;
    }
}


</style>