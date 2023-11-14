<template>
    <div :class="['popup', { 'popup-show': showPopup }]">
      <video autoplay muted loop class="video" controls>
        <source src="../assets/VideoOiltanking-Otamerica-10.11.23.mp4" type="video/mp4">
      </video>
      <img src="../assets/times-circle.svg" alt="" class="close-button" @click="closePopup">
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        showPopup: false,
      };
    },
    mounted() {
      this.$nextTick(() => {
        setTimeout(() => {
          this.showPopup = true;
        }, 50);
      });
    },
    methods: {
      closePopup() {
        this.showPopup = false;
        setTimeout(() => {
          this.$emit('close');
        }, 300);
      },
    },
  };
  </script>
  
  <style scoped>
  .popup {
    width: 100%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transform: translateY(-100%);
    transition: opacity 0.3s ease 0s, transform 0.3s ease 0.3s;
  }
  
  .video {
    width: 100%;
    height: 100%;
    object-fit:contain;
  }
  
  .video::-webkit-media-controls {
    opacity: 0;
  }
  
  .popup-show {
    opacity: 1;
    transform: translateY(0);
    transition: opacity 0.3s ease 0.3s, transform 0.3s ease 0s;
  }
  
  .close-button {
    position: absolute;
    top: 12px;
    right: 12px;
    height: 30px;
    width: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
    border: none;
  }
  </style>
  