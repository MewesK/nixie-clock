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
  width: 12.5rem;
  height: 22rem;

  border: 1px solid #ffffff09;
  border-radius: 4rem 4rem 0 0;
  border-bottom-width: 0;
  background: radial-gradient(
    circle 30rem at 50% 77%,
    #00000000,
    #00000000 50%,
    #e0e0e070 75%
  );
}

.tube::after {
  position: relative;
  bottom: -22rem;
  left: -0.25rem;

  content: "";
  display: block;
  width: 13rem;
  height: 8rem;

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
  width: 13rem;
  position: absolute;
  top: -1rem;
  font-family: "Advent Pro", sans-serif;
  font-weight: 100;
  font-size: 20rem;
  text-align: center;
  color: #20202040;
}

.active {
  color: #ffc703d0;
  text-shadow: 0px 0px 0.5rem #ffc703, 0px 0px 2rem #ff5703,
    0px 0px 3rem #ff570340;
}

.mesh {
  width: 11rem;
  height: 20rem;
  position: absolute;
  top: 1rem;
  margin-left: 1rem;
  background-image: url("../assets/mesh.svg");
  background-repeat: no-repeat;
  background-size: 10rem;
  background-position: center, 50%, 50%;
  background-blend-mode: difference;
  opacity: 0.5;
}
</style>
