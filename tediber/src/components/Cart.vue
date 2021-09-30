<template>
  <div class="cart-container">
    <h2>articles ({{ nbArticle }})</h2>
    <div v-for="item in cart" :key="item.articleId" class="article-container">
      <div class="article-img-container">
        <img
          :src="require(`../assets/images/${item.articleImg}`)"
          v-bind:alt="item.articleNom"
        />
      </div>
      <div class="article-infos-container">
        <h3>l'incroyable {{ item.articleNom }} tediber</h3>
        <p>taille : <span v-text="item.articleTaille"></span></p>
        <p>qté : <span v-text="item.articleQte"></span></p>
        <span> {{ item.articlePrix }} &nbsp;&euro;</span>
      </div>
    </div>
  </div>
</template>

<script>
import data from "../data.JSON";

export default {
  name: "Cart",
  data() {
    return {
      cart: data.cart,
      nbArticle: data.nbArticle,
      order: data,
    };
  },
};
</script>

<style>
.cart-container {
  display: flex;
  flex-direction: column;
  text-align: left;
  padding-left: 18px;
}

.cart-container h2 {
  text-transform: uppercase;
  font-size: 0.7em;
}

.article-container {
  background-color: #fff;
  padding: 8px;
  display: flex;
  border: 1px solid #979797;
  box-shadow: 0px 2px 9px 0px;
  margin-bottom: 18px;
}

.article-img-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.article-img-container img {
  width: 116px;
  height: 103px;
}

.article-infos-container {
  margin: 0 0 0 11px;
  color: var(--tdb-text);
  font-size: 0.6em;
  text-transform: uppercase;
}

.article-infos-container h3 {
  margin: 0;
}

@media screen and (max-width: 685px) {
  .cart-container {
    padding-left: 0;
  }
  .article-container {
    margin-bottom: 18px;
  }
}
</style>