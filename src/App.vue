<template>
  <div id="app">
    <!-- Contenido de tu sitio -->
    <!-- ... -->

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
