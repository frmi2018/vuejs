<template>
  <div v-if="show">
    <div class="menu-container">
      <slot>Texte par défaut</slot
      ><i class="fas fa-chevron-up" v-on:click="show = !show"></i>
    </div>

    <div class="suivi-container">
      <div class="step-container">
        <img src="../assets/svg/Group.svg" alt="" />

        <label v-if="!step1">
          <input type="checkbox" disabled="disabled" />
          <span></span>
        </label>
        <label v-else>
          <input type="checkbox" checked disabled="disabled" />
          <span></span>
        </label>
      </div>
      <div class="step-container">
        <img src="../assets/svg/Group-2.svg" alt="" />
        <label v-if="!step2">
          <input type="checkbox" disabled="disabled" />
          <span></span>
        </label>
        <label v-else>
          <input type="checkbox" checked disabled="disabled" />
          <span></span>
        </label>
      </div>
      <div class="step-container">
        <img src="../assets/svg/Group-3.svg" alt="" />
        <label v-if="!step3">
          <input type="checkbox" disabled="disabled" />
          <span></span>
        </label>
        <label v-else>
          <input type="checkbox" checked disabled="disabled" />
          <span></span>
        </label>
      </div>
      <div class="step-container">
        <img src="../assets/svg/Group-4.svg" alt="" />

        <label v-if="!step4">
          <input type="checkbox" disabled="disabled" />
          <span></span>
        </label>
        <label v-else>
          <input type="checkbox" checked disabled="disabled" />
          <span></span>
        </label>
      </div>
    </div>
  </div>

  <div v-else class="menu-container">
    <slot>Texte par défaut</slot
    ><i class="fas fa-chevron-down" v-on:click="show = !show"></i>
  </div>
</template>

<script>
// importer la commande du client de la BDD
import data from "../data.JSON";

export default {
  name: "SuiviCommande",
  data() {
    return {
      show: true,
      step1: data.suiviCommande.step1,
      step2: data.suiviCommande.step2,
      step3: data.suiviCommande.step3,
      step4: data.suiviCommande.step4,
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
  padding: 8px;
}
.suivi-container {
  display: flex;
  margin-bottom: 8px;
}

.step-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.step-container img {
  width: 100%;
  height: 74px;
  margin: 8px;
}

label input {
  display: none; /* Hide the default checkbox */
}

/* Style the artificial checkbox */
label span {
  height: 10px;
  width: 10px;
  border: 1px solid grey;
  display: inline-block;
  position: relative;
}

/* Style its checked state...with a ticked icon */
[type="checkbox"]:checked + span:before {
  content: "\2714";
  position: absolute;
  top: -0.7em;
  left: -0.05em;
  color: green;
}
</style>
