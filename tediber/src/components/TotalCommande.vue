<template>
  <div class="container-total">
    <div>
      <span>Sous-totale</span>
      <span>{{ CalculSousTotal() }}</span>
    </div>
    <div>
      <span>Livraison</span>
      <span v-if="order.fdp !== 0">{{ order.fdp }}</span>
      <span v-else>GRATUITE</span>
    </div>
    <div>
      <span>TOTAL</span>
      <span>{{ sommeTotal }}</span>
    </div>
  </div>
</template>

<script>
// importer la commande du client de la BDD
import data from "../data.JSON";

export default {
  name: "TotalCommande",
  data() {
    return {
      order: data,
      total: 0,
      sousTotal: 0,
    };
  },
  computed: {
    sommeTotal() {
      return this.sousTotal + this.order.fdp;
    },
  },
  methods: {
    CalculSousTotal() {
      let s = 0;
      for (let i = 0; i < this.order.cart.length; i++) {
        s += this.order.cart[i].articlePrix * this.order.cart[i].articleQte;
        this.sousTotal = s;
      }
      return this.sousTotal;
    },
  },
};
</script>

<style>
.container-total {
  margin: 9px 18px;
  padding: 16px 12px;
  border: 1px solid #979797;
  box-shadow: 0px 2px 9px 0px;
}

.container-total div {
  display: flex;
  justify-content: space-between;
}
</style>
