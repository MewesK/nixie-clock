<script lang="ts">
import Digit from "./components/Digit.vue";

export default {
  components: { Digit },
  data() {
    return {
      time: new Date(),
    };
  },
  mounted() {
    this.tick();
  },
  methods: {
    tick() {
      this.time.setSeconds(this.time.getSeconds() + 1);
      this.$forceUpdate();
      window.setTimeout(() => {
        this.tick();
      }, 1000);
    },
  },
};
</script>

<template>
  <div class="container">
    <Digit :value="Math.floor(time.getHours() / 10)" />
    <Digit :value="time.getHours() % 10" />
    <hr />
    <Digit :value="Math.floor(time.getMinutes() / 10)" />
    <Digit :value="time.getMinutes() % 10" />
    <hr />
    <Digit :value="Math.floor(time.getSeconds() / 10)" />
    <Digit :value="time.getSeconds() % 10" />
  </div>
</template>

<style scoped>
.container {
  margin: auto;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  display: flex;
  gap: 1rem;
}

hr {
 margin:  1rem;
 border-color: #ffffff10;
}
</style>
