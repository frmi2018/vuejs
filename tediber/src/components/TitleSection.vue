<template>
  <div class="title-section-container">
    <h2 class="hr"><slot>Texte par défaut</slot></h2>
    <img
      src="../assets/svg/zigzag.svg"
      alt="image de décoration en forme de zigzag jaune"
    />
  </div>
</template>

<script>
export default {
  name: "TitleSection",
};
</script>

<style>
.title-section-container {
  text-align: center;
  margin: 18px 0;
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
  font-size: 0.95em;
}
.title-section-container .hr::before,
.title-section-container .hr::after {
  border-top: 0.0625em solid;
  content: "";
  flex: 1;
  margin: 0 0.5em;
}
</style>
