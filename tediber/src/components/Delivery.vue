<template>
  <div class="container-section">
    <div class="cont1">
      <h3>adresse de collecte</h3>
      <div class="delivery-details">
        <span>{{ order.deliveryDetails.name.toUpperCase() }}</span>
        <span
          >{{ order.deliveryDetails.streetNumber }}
          {{ order.deliveryDetails.streetName }}</span
        >
        <span>{{ order.deliveryDetails.city.toUpperCase() }}</span>
        <span>{{ order.deliveryDetails.postcode }}</span>
        <span>{{ order.deliveryDetails.country }}</span>
      </div>
    </div>

    <div class="cont1">
      <h3>vos coordonnées</h3>
      <div class="delivery-details">
        <span>{{ order.user.firstName }} {{ order.user.name }}</span>
        <span>{{ order.user.phone }}</span>
      </div>
    </div>

    <div class="cont1">
      <h3>livraison estimée</h3>
      <span>{{ order.dateLivraison }}</span>
    </div>

    <div class="cont1">
      <h3>mode de livraison</h3>
      <span>{{ order.deliveryDetails.deliveryMethod }}</span>
    </div>
  </div>
</template>

<script>
import data from "../data.JSON";

export default {
  name: "Delivery",
  data() {
    return {
      order: data,
    };
  },
};
</script>

<style>
.container-section {
  background-color: #fff;
  margin: 9px 18px;
  padding: 8px;
  border: 1px solid var(--tdb-grey2);
  box-shadow: 0px 2px 9px 0px;
  display: flex;
}

.cont1 {
  flex: 1;
  padding: 0 8px;
}

.cont1:not(:last-child) {
  border-right: 1px solid var(--tdb-grey2);
}

.cont1 h3 {
  text-transform: uppercase;
  font-size: 0.75em;
}

.cont1 span {
  display: block;
  font-size: 0.75em;
}

@media screen and (max-width: 685px) {
  .container-section {
    flex-direction: column;
  }
  .cont1 {
    padding: 8px 0;
  }
  .cont1:not(:last-child) {
    border-right: 0;
    border-bottom: 1px solid var(--tdb-grey2);
  }
}
</style>
