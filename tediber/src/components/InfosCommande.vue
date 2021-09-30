<template>
  <div class="details-container">
    <p>
      N&#176; de commande :
      <span class="details-datas" v-text="order.numeroCommande"></span>
    </p>
    <p>
      Date de commande :
      <span class="details-datas"
        >{{ order.jourCommande }}&nbsp;{{ order.moisCommande }}&nbsp;{{
          order.anneeCommande
        }}</span
      >
    </p>
    <p>
      Date d'expédition :
      <span class="details-datas">
        {{ order.jourExpedition }}&nbsp;{{ order.moisExpedition }}&nbsp;{{
          order.anneeExpedition
        }}</span
      >
    </p>
  </div>
</template>

<script>
import data from "../data.JSON";
export default {
  name: "InfosCommande",
  data() {
    return {
      order: data,
    };
  },
};
</script>

<style>
.details-container {
  margin: 18px;
  text-align: left;
  font-size: 0.75em;
}

.details-datas {
  text-transform: initial;
  font-weight: bold;
}
@media screen and (max-width: 685px) {
  .details-container {
    margin: 0px;
  }
}
</style>