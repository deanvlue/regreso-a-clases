<template>
  <div>
    <div class="header mx-auto">
      <Logo />
    </div>
  </div>
</template>
<script>
import Logo from "@/components/Logo";
import Alert from "@/components/Alert";

export default {
  components: {
    Alert,
    Logo
  }
};
</script>
<style>
.header {
  width: 100%;
  height: 60px;
  position: fixed;
  top: 0;
  left: 0;
  background-color: white;
  z-index: 2;
}

@media (max-width: 812px) {
  .header {
    height: 30px;
  }
  .Logo {
    height: 25px;
  }
}
@media (max-width: 1024px) {
  .header {
    height: 30px;
  }
  .Logo {
    height: 25px;
  }
}

@media (max-width: 1112px) {
  .header {
    height: 60px;
  }
  .Logo {
    height: 55px;
  }
}

@media (max-width: 1920px) {
  .header {
    height: 60px;
  }
  .Logo {
    height: 55px;
  }
}

@media (min-width: 667px) and (max-width: 812px) {
  .header {
    height: 30px;
  }
  .Logo {
    height: 25px;
  }
}
</style>
