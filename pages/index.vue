<template>
  <div>
    <Header />

    <Scene>
      <Projector />
      <Chat />

      <Podcasts />
      <Recursos />
      <CuadernoPupitre />
      <Email />
      <Phone />
    </Scene>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Scene from "@/components/Scene";
import Projector from "@/components/Projector";
import Email from "@/components/Email";
import Chat from "@/components/Chat";
import Podcasts from "@/components/Podcasts";
import Phone from "@/components/Phone";
import Boy from "@/components/Boy";
import Girl from "@/components/Girl";
import Whiteboard from "@/components/Whiteboard";

import Canvas from "~/components/Canvas.vue";

import Recursos from "@/components/Recursos";
import CuadernoPupitre from "@/components/CuadernoPupitre";

export default {
  components: {
    Header,
    Scene,
    Projector,
    Email,
    Chat,
    Podcasts,
    Phone,
    Boy,
    Girl,
    Whiteboard,
    Recursos,
    CuadernoPupitre
  },
  data() {
    return {
      title: "Regreso a la Escuela"
    };
  },
  head() {
    return {
      title: this.title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: "description",
          name: "description",
          content: "My custom description"
        }
      ]
    };
  }
};
</script>
<style>
html {
  background: #000;
}
.tv,
.info-tv,
.phone,
.info-phone,
.cellphone,
.info-cellphone,
.email,
.info-email,
.podcasts,
.whiteboard,
.info-podcasts,
.info-wb {
  /*border: 3px solid #17C3B2;*/
  position: absolute;
  cursor: pointer;
}
.info-prj,
.info-cellphone,
.info-email,
.info-phone,
.info-podcasts,
.info-wb {
  width: 30px;
  height: 30px;

  line-height: 30px;
  font-size: 22px;
  z-index: 10;
}
/*
 * Modal
 */

.modal-body {
  background: #fff;
  border: 10px solid #6c49b8;
  padding: 0px !important;
}

.modal-title {
  background: #6c49b8;
  color: #ffffff;
  white-space: nowrap;
  padding: 1rem 0rem;
  /*
  top: -45px;
  left: 50%;
  transform: translate(-50%, 0);
  
  */
}

/*.modal-title strong {
  border: 2px solid #ffffff;
  padding: 0.5rem 2rem;

  border-radius: 1rem 1rem 2rem 2rem;
}*/

.modal-close {
  position: absolute;
  width: 30px;
  height: 30px;
  right: -20px;
  top: -20px;
  color: #6c49b8;
  text-align: center;
  line-height: 29px;
  font-size: 15px;
  border-radius: 100%;
  background: #fff;
  border: 1px solid #6c49b8;
  cursor: pointer;
}
.green {
  background: rgb(155, 195, 85);
  background: linear-gradient(
    0deg,
    rgba(155, 195, 85, 1) 0%,
    rgba(123, 168, 56, 1) 50%,
    rgba(155, 195, 85, 1) 100%
  );
}
.green strong {
  border: 2px solid #eac858;
}
.darkgreen {
  background: #0c6259;
  background: linear-gradient(
    186.52deg,
    #0c6259 -1.25%,
    #0c6259 46.11%,
    #06312d 96.98%
  );
}
.darkgreen strong {
  border: 2px solid #ffffff;
}
.blue {
  background: rgb(34, 88, 128);
  background: linear-gradient(
    0deg,
    rgba(34, 88, 128, 1) 0%,
    rgba(30, 77, 111, 1) 50%,
    rgba(34, 88, 128, 1) 100%
  );
}
/*.blue strong {
  border: 2px solid #3f9086;
}*/
.purple {
  background: #6c49b8;
}

/*.purple strong {
  border: 2px solid #ffffff;
}*/
.tools {
  margin-top: 20px;
  margin-bottom: 20px;
  text-align: center;
}
.tools.right {
  text-align: right;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1040;
  width: 100%;
  height: 100%;
  background-color: #000;
}
.tel {
  color: #be3365;
  font-size: 1.1em;
  font-weight: bold;
}

.bg-white-rock {
  background: #e2e2e2;
}
/*
 * Buttons
 */
.btn {
  padding: 0.375rem 2.75rem;
}
.btn.btn-secondary {
  border-bottom: 5px solid #5b6066;
}
.btn.btn-green {
  background: #17c3b2;
  border-color: #56c0b2;
  border-bottom: 5px solid #109d8c;
}
.btn-green:not(:disabled):not(.disabled):active {
  background: #109d8c;
  border-color: #109d8c;
  border-bottom: 5px solid #109d8c;
}
.btn-green:hover {
  background: #109d8c;
  border-color: #109d8c;
  border-bottom: 5px solid #109d8c;
}
.btn.btn-purple {
  background: #6e79e0;
  border-color: #6e79e0;
  border-bottom: 5px solid #6765ae;
}
.btn-purple:not(:disabled):not(.disabled):active {
  background: #6765ae;
  border-color: #6765ae;
  border-bottom: 5px solid #6765ae;
}
.btn-purple:hover {
  background: #6765ae;
  border-color: #6765ae;
  border-bottom: 5px solid #6765ae;
}
.btn.btn-pink {
  background: #be3365;
  border-color: #be3365;
  border-bottom: 5px solid #931341;
}
.btn-pink:not(:disabled):not(.disabled):active {
  background: #931341;
  border-color: #931341;
  border-bottom: 5px solid #931341;
}
.btn-pink:hover {
  background: #931341;
  border-color: #931341;
  border-bottom: 5px solid #931341;
}
/*
 * Pagination
 */
.page-item.disabled .page-link {
  color: #aeadd8;
  pointer-events: none;
  cursor: auto;
  background-color: #6765ae;
  border-color: #6765ae;
  border-bottom: 5px solid #6765ae;
}
.page-item.active .page-link {
  z-index: 3;
  color: #fff;
  background-color: #17c3b2;
  border-color: #17c3b2;
  border-bottom: 5px solid #109d8c;
}
.page-link {
  position: relative;
  display: block;
  padding: 0.5rem 0.75rem;
  margin-left: -1px;
  line-height: 1.25;
  color: #ffffff;
  background-color: #6e79e0;
  border: 1px solid #6e79e0;
  border-bottom: 5px solid #6765ae;
}
.page-link:hover {
  z-index: 2;
  color: #ffffff;
  text-decoration: none;
  background-color: #6765ae;
  border-color: #6765ae;
}
/*
 * Cards
 */
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  grid-auto-rows: auto;
  grid-gap: 2rem 1rem;
}
.card-item {
  position: relative;
  justify-self: center;
  float: left;
}
.card-item object {
  width: 100%;
  height: auto;
  border: 5px solid rgba(177, 64, 101, 1);
  border-radius: 13px;
}
/*
 * Tooltip
 */
.tooltip {
  display: block !important;
  z-index: 1;
}

.tooltip .tooltip-inner {
  background: black;
  color: white;
  border-radius: 16px;
  padding: 5px 10px 4px;
}

.tooltip .tooltip-arrow {
  width: 0;
  height: 0;
  border-style: solid;
  position: absolute;
  margin: 5px;
  border-color: black;
  z-index: 1;
}

.tooltip[x-placement^="top"] {
  margin-bottom: 5px;
}

.tooltip[x-placement^="top"] .tooltip-arrow {
  border-width: 5px 5px 0 5px;
  border-left-color: transparent !important;
  border-right-color: transparent !important;
  border-bottom-color: transparent !important;
  bottom: -5px;
  left: calc(50% - 5px) !important;
  margin-top: 0;
  margin-bottom: 0;
}

.tooltip[x-placement^="bottom"] {
  margin-top: 5px;
}

.tooltip[x-placement^="bottom"] .tooltip-arrow {
  border-width: 0 5px 5px 5px;
  border-left-color: transparent !important;
  border-right-color: transparent !important;
  border-top-color: transparent !important;
  top: -5px;
  left: calc(50% - 5px) !important;
  margin-top: 0;
  margin-bottom: 0;
}

.tooltip[x-placement^="right"] {
  margin-left: 5px;
}

.tooltip[x-placement^="right"] .tooltip-arrow {
  border-width: 5px 5px 5px 0;
  border-left-color: transparent !important;
  border-top-color: transparent !important;
  border-bottom-color: transparent !important;
  left: -5px;
  top: calc(50% - 5px) !important;
  margin-left: 0;
  margin-right: 0;
}

.tooltip[x-placement^="left"] {
  margin-right: 5px;
}

.tooltip[x-placement^="left"] .tooltip-arrow {
  border-width: 5px 0 5px 5px;
  border-top-color: transparent !important;
  border-right-color: transparent !important;
  border-bottom-color: transparent !important;
  right: -4px;
  top: calc(34% - 5px) !important;
  margin-left: 0;
  margin-right: 0;
}

.tooltip.popover .popover-inner {
  background: #f9f9f9;
  color: black;
  padding: 24px;
  border-radius: 5px;
  box-shadow: 0 5px 30px rgba(black, 0.1);
}

.tooltip.popover .popover-arrow {
  border-color: #f9f9f9;
}

.tooltip[aria-hidden="true"] {
  visibility: hidden;
  opacity: 0;
  transition: opacity 0.15s, visibility 0.15s;
}

.tooltip[aria-hidden="false"] {
  visibility: visible;
  opacity: 1;
  transition: opacity 0.15s;
}
/*
 * Animations 
 */
.rotate {
  animation: rotate 2s infinite;
}
.scale {
  animation: scale 2s infinite;
}
.pulse {
  color: #ffffff;
  font-weight: bold;
  font-size: 24px;
  margin: 0 auto;
  text-align: center;
  line-height: 29px;

  background: #17c3b2;
  box-shadow: 0 0 0 0 #118f82;
  border-radius: 50%;
  margin: 10px;
  height: 30px;
  width: 30px;
  transform: scale(1);
  animation: pulse 2s infinite;
}
@keyframes rotate {
  0% {
    transform: rotate(0deg);
  }

  50% {
    transform: rotate(-90deg);
  }

  100% {
    transform: rotate(0deg);
  }
}
@keyframes scale {
  0% {
    transform: scale(1);
  }

  50% {
    transform: scale(0.97);
  }

  100% {
    transform: scale(1);
  }
}
@keyframes pulse {
  0% {
    transform: scale(0.95);
    /*box-shadow: 0 0 0 0 rgba(177, 64, 101, 0.7);*/
    box-shadow: 0 0 0 0 rgba(255, 255, 255, 0.7);
  }

  70% {
    transform: scale(1);
    box-shadow: 0 0 0 10px rgba(255, 82, 82, 0);
  }

  100% {
    transform: scale(0.95);
    box-shadow: 0 0 0 0 rgba(255, 82, 82, 0);
  }
}
/*
 * Forms
 */
.form-control {
  border-radius: 30px;
  text-align: center;
  height: calc(1.5em + 0.75rem + 10px);
  -webkit-box-shadow: inset 2px 9px 4px -8px rgba(0, 0, 0, 0.22);
  -moz-box-shadow: inset 2px 9px 4px -8px rgba(0, 0, 0, 0.22);
  box-shadow: inset 2px 9px 4px -8px rgba(0, 0, 0, 0.22);
}
/*
 * Large devices (Desktop, 3280px)
 */
@media (min-width: 1920px) and (max-width: 3280px) {
  .info-tv,
  .info-cellphone,
  .info-email,
  .info-phone,
  .info-podcasts {
    width: 60px;
    height: 60px;

    line-height: 60px;

    font-size: 40px;
  }
}
/*
 * Large devices (Desktop, 1920px)
 */
@media (max-width: 1920px) {
  .info-tv,
  .info-cellphone,
  .info-email,
  .info-phone,
  .info-podcasts {
    width: 35px;
    height: 35px;

    line-height: 35px;

    font-size: 25px;
  }
}

.nav-pills .nav-link.active,
.nav-pills .show > .nav-link {
  color: #fff;
  background-color: #17c3b2;
}

.nav-link {
  display: block;
  padding: 0.5rem 1rem;
  color: #17c3b2;
}
</style>
