<template>
  <div v-if="show" class="menu-container">
    <slot>Texte par défaut</slot
    ><i class="fas fa-chevron-down" v-on:click="show = !show"></i>
  </div>

  <div v-else class="menu-container">
    <slot>Texte par défaut</slot
    ><i class="fas fa-chevron-up" v-on:click="show = !show"></i>
  </div>
</template>

<script>
export default {
  name: "EmptySection",
  data() {
    return {
      show: true,
    };
  },
};
</script>

<style>
.menu-container {
  border-top: 1px solid black;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.5em;
}

.menu-container:last-child {
  border-bottom: 1px solid black;
  margin-bottom: 18px;
}
</style>
