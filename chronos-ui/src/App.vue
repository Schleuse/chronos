<template>
  <div id="app">
    <div id="nav">
      <Navigation />
    </div>
    <div class="content">
      <router-view />
    </div>

    <ConfirmModal />
  </div>
</template>

<script>
import Navigation from "@/components/Navigation";
import ConfirmModal from "@/components/ConfirmModal";
import api from "@/api";

export default {
  name: "App",
  components: {
    Navigation,
    ConfirmModal
  },
  mounted() {
    api.loadScripts();
  }
};
</script>

<style lang="scss">
@import "styles/fonts.scss";
@import "styles/buttons.scss";
@import "styles/syntax.scss";
@import "styles/snackbar.scss";

:root {
  --grey: #1f1f1f;
  --blue: #007aff;
  --blue-dark: #006ee6;
  --green: #04cd00;
  --yellow: #dcac00;
  --red: #dc0000;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: "Inter";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #fff;
  background: var(--grey);
  min-height: 100vh;

  display: grid;
  grid-template-columns: 90px auto;
}

h1.page-title {
  padding-top: 70px;
  padding-left: 40px;
  padding-bottom: 40px;
  font-weight: 400;
  font-size: 3rem;
  margin: 0;
  opacity: 0.9;
}

.vm--overlay {
  background: rgba(0, 0, 0, 0.7) !important;
  backdrop-filter: blur(10px);
}

.vm--modal {
  background: #101010 !important;
  box-shadow: 0 20px 60px -2px rgba(0, 0, 0, 0.3) !important;
}

h2.modal-title {
  font-weight: 400;
  text-align: center;
  margin-bottom: 45px;
}
</style>
