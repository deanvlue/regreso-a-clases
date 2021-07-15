<template>
  <div>
    <img
      class="Logo my-1 mx-auto"
      src="~/assets/logo_header.png"
      alt="la escuela en casa"
    />
  </div>
</template>

<style>
.Logo {
  animation: 1s appear;
  height:  90%;
  display: block;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}

@media (max-width: 1920px) {
  .Logo{
    height: 55px;
  }
}
</style>
