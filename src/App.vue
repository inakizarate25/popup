<template>
  <div id="app">
<header>
  <h1>Popup</h1>
  <nav>
    aaaaaaaaaaaaa
  </nav>
</header>
    <!-- Popup -->
    <Popup @close="hidePopup" v-if="showPopup" />
  </div>
</template>

<script>
import Popup from "./components/popup.vue";

export default {
  components: {
    Popup,
  },
  data() {
    return {
      showPopup: true,
    };
  },
  methods: {
    hidePopup() {
      this.showPopup = false;
    },
  },
};
</script>
<style>
#app {
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
header {
  width: 100%;
  height: 10%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: blue;
  position: fixed;
  top: 0;
  left: 0;
}
</style>