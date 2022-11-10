<script lang="ts">
export default {
  props: {
    value: Number,
  },
};
</script>

<template>
  <div class="tube">
    <div
      v-for="number in [6, 7, 5, 8, 4, 3, 9, 2, 0, 1]"
      class="digit"
      :class="{ active: number === value }"
    >
      {{ number }}
    </div>
    <div class="mesh"></div>
  </div>
</template>

<style scoped>
.tube {
  width: 12vmin;
  height: 21vmin;

  border: 0.005vmin solid #ffffff09;
  border-radius: 4vmin 4vmin 0 0;
  border-bottom-width: 0;
  background: radial-gradient(
    circle 29vmin at 50% 77%,
    #00000000,
    #00000000 50%,
    #e0e0e070 75%
  );
}

.tube::after {
  position: relative;
  width: 13vmin;
  height: 7vmin;
  bottom: -21vmin;
  left: -0.5vmin;

  content: "";
  display: block;
  background: linear-gradient(
    0.25turn,
    #ffffffa0,
    #020202 5%,
    #020202 20%,
    #ffffff30,
    #040404 40%,
    #020202 55%,
    #ffffff20,
    #020202 85%,
    #020202 95%,
    #ffffffa0
  );
}

.digit {
  position: absolute;
  width: inherit;
  top: -1vmin;

  font-family: "Advent Pro", sans-serif;
  font-weight: 100;
  font-size: 20vmin;
  text-align: center;
  color: #20202040;
}

.active {
  color: #ffc703d0;
  text-shadow: 0px 0px 1vmin #ffc703, 0px 0px 3vmin #ff5703, 0px 0px 4vmin #ff570340;
}

.mesh {
  position: absolute;
  width: 10vmin;
  height: 19vmin;
  top: 2.2vmin;
  margin-left: 1vmin;
  
  background-image: url("../assets/mesh.svg");
  background-repeat: no-repeat;
  background-position: center, 50%, 50%;
  opacity: 0.5;
}
</style>
