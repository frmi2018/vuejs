<template>
  <div class="container-paiement">
    <div v-if="visa" class="container-paiement-items">
      <img
        class="img-paiement"
        src="../assets/logo/Logo_CB-1-1024x503.jpg"
        alt="logo CB Visa"
      />
      <span class="text-paiement">visa</span>
    </div>
    <div v-else-if="masterCard" class="container-paiement-items">
      <img
        class="img-paiement"
        src="../assets/logo/mastercard.png"
        alt="logo CB Visa"
      />
      <span class="text-paiement">mastercard</span>
    </div>
    <div v-else>
      <span>Choisir un moyen de paiement</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "PaiementInfos",
  props: ["visa", "masterCard"],
  data() {
    return {
      show: true,
    };
  },
};
</script>

<style>
.container-paiement {
  margin: 9px 18px;
  padding: 16px 12px;
  border: 1px solid #979797;
  box-shadow: 0px 2px 9px 0px;
}

.container-paiement-items {
  display: flex;
  align-items: center;
}

.container-paiement .img-paiement {
  width: 53px;
  height: 34px;
}

.container-paiement .text-paiement {
  margin-left: 9px;
  text-transform: uppercase;
}
</style>
