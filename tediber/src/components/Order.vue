<template>
  <div class="title-section-container" v-if="show" v-on:click="show = !show">
    <h2 class="hr"><slot>Texte par défaut</slot></h2>
    <img
      src="../assets/svg/zigzag.svg"
      alt="image de décoration en forme de zigzag jaune"
    />
    <!-- ***** -->
    <Cart />
  </div>

  <div v-else class="menu-close">
    <slot>Texte par défaut</slot
    ><i class="fas fa-chevron-up" v-on:click="show = !show"></i>
  </div>
</template>

<script>
import Cart from "./Cart.vue";
export default {
  name: "Order",
  data() {
    return {
      show: true,
    };
  },
  components: {
    Cart,
  },
};
</script>

<style>
.title-section-container {
  text-align: center;
  margin: 18px;
  text-transform: uppercase;
}

.title-section-container img:hover,
i:hover {
  cursor: pointer;
}

.title-section-container .hr {
  align-items: center;
  display: flex;
  text-align: center;
  margin: 0;
}
.title-section-container .hr::before,
.title-section-container .hr::after {
  border-top: 0.0625em solid;
  content: "";
  flex: 1;
  margin: 0 0.5em;
}

.menu-close {
  border-top: 1px solid black;
  border-bottom: 1px solid black;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.5em;
  line-height: 19px;
  margin: 0 18px;
}
</style>
