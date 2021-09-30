<template>
  <div class="container">
    <NavBar v-bind:nbArticle="nbArticle"></NavBar>

    <!-- titre suivi de commande -->
    <TitleSection>suivi de commande</TitleSection>

    <section class="container-section1">
      <div class="container-section1-left">
        <!-- infos commande -->
        <InfosCommande></InfosCommande>

        <!-- suivi de commande -->
        <SuiviCommande>Suivi de commande</SuiviCommande>

        <!-- informations sur les retours -->
        <EmptySection>informations sur les retours</EmptySection>
      </div>
      <div class="container-section1-right">
        <!-- Panier -->
        <Cart></Cart>
      </div>
    </section>

    <!-- titre informations sur la livraison -->
    <TitleSection>informations sur la livraison</TitleSection>

    <!-- informations sur la livraison -->
    <Delivery></Delivery>

    <!-- titre informations de paiement -->
    <TitleSection>informations de paiement</TitleSection>

    <!-- informations de paiement -->
    <PaiementInfos
      v-bind:visa="visa"
      v-bind:masterCard="masterCard"
    ></PaiementInfos>

    <!-- titre total commande -->
    <TitleSection>total commande</TitleSection>

    <!-- total commande -->
    <total-commande />

    <!-- titre besoin d'aide ? -->
    <TitleSection>besoin d'aide ?</TitleSection>

    <!-- foire aux questions tediber -->
    <EmptySection>foire aux questions tediber</EmptySection>
    <!-- la garantie tediber -->
    <EmptySection>la garantie tediber</EmptySection>
    <!-- reprise de l'ancienne literie -->
    <EmptySection>reprise de l'ancienne literie</EmptySection>
    <!-- comment faire un retour -->
    <EmptySection>comment faire un retour</EmptySection>
  </div>
</template>

<script>
// importer la commande du client de la BDD
import data from "./data.JSON";

// import components
import NavBar from "./components/NavBar.vue";
import TitleSection from "./components/TitleSection.vue";
import InfosCommande from "./components/InfosCommande.vue";
import SuiviCommande from "./components/SuiviCommande.vue";
import EmptySection from "./components/EmptySection.vue";
import Cart from "./components/Cart.vue";
import Delivery from "./components/Delivery.vue";
import PaiementInfos from "./components/PaiementInfos.vue";
import TotalCommande from "./components/TotalCommande.vue";

export default {
  name: "App",
  data() {
    return {
      nbArticle: data.nbArticle,
      visa: data.visa,
      masterCard: data.masterCard,
    };
  },
  components: {
    NavBar,
    TitleSection,
    InfosCommande,
    SuiviCommande,
    EmptySection,
    Cart,
    Delivery,
    PaiementInfos,
    "total-commande": TotalCommande,
  },
};
</script>

<style>
#app {
  font-family: Gill Sans Std Regular, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  font-size: calc(3vmin + 10px);

  --tdb-yellow: #f8ae00;
  --tdb-grey: #7f7c89;
  --tdb-grey2: #979797;
  --tdb-fond: #d8d8d8;
  --tdb-text: #202446;

  box-sizing: border-box;
  margin: 0;
  padding: 0;
  background-color: var(--tdb-fond);
}

.container {
  background-color: #fff;
  max-width: 1200px;
  margin: 0 auto;
  color: var(--tdb-text);
}

.container-section1 {
  display: flex;
  text-align: center;
  padding: 0 18px;
  min-width: 280px;
}

.container-section1-left {
  width: 50%;
}

.container-section1-right {
  width: 50%;
}

h2 {
  text-transform: uppercase;
}

@media screen and (max-width: 685px) {
  .container {
    min-width: 280px;
    width: 100%;
    border: none;
  }
  .container-section1 {
    flex-direction: column;
    align-items: center;
  }
  .container-section1-left {
    width: 100%;
  }

  .container-section1-right {
    width: 100%;
  }
}
</style>
