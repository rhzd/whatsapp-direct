<template>
  <div>
    <lottie :width="230" :height="230" :options="lottieOptions" v-on:animCreated="handleAnimation" />
  </div>
</template>

<script>
import lottie from "vue-lottie/src/lottie.vue";
import * as animationData from "~/assets/animation/whatsapp.json";

export default {
  components: {
    lottie,
  },
  data() {
    return {
      anim: null, // for saving the reference to the animation
      lottieOptions: { animationData: animationData.default },
    };
  },
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim;
    },
  },
};
</script>
