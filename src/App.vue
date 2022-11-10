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
  <main class="container">
    <Digit :value="Math.floor(time.getHours() / 10)" />
    <Digit :value="time.getHours() % 10" />
    <hr />
    <Digit :value="Math.floor(time.getMinutes() / 10)" />
    <Digit :value="time.getMinutes() % 10" />
    <hr />
    <Digit :value="Math.floor(time.getSeconds() / 10)" />
    <Digit :value="time.getSeconds() % 10" />
  </main>
  <footer>
    Made with <span style="color:#e25555">♥</span> by <a href="https://github.com/MewesK" target="_blank"><strong>mewk</strong></a>
  </footer>
</template>

<style scoped>
.container {
  margin: auto;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  display: flex;
  gap: 2vmin;
}

hr {
  border-color: #ffffff10;
}

footer {
  position: fixed;
  bottom: 1vmin;
  left: 50%;
  transform: translateX(-50%);
  color: #ffffff;
  font-family: "Manrope", sans-serif;
  font-weight: 100;
  font-size: 1.1vmin;
  opacity: 0.03;
}

footer:hover {
  opacity: 0.33;
}

footer a {
  color: #ffffff;
  text-decoration: none;
}
</style>
