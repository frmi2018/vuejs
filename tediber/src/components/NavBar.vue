<template>
  <div class="topnav" id="myTopnav">
    <!-- Button mobile -->
    <a class="icon" v-on:click="myFunction">
      <i class="fa fa-bars"></i>
    </a>
    <!-- ***** -->
    <a href="#">
      <img
        src="../assets/svg/logo_tediber.0d5d36f.svg"
        alt="Logo Tediber"
        width="70"
        height="50"
      />
    </a>
    <!-- ***** -->
    <a href="#">nos produits</a>
    <a href="#t">le concept</a>
    <a href="#">avis</a>
    <!-- ***** -->
    <img
      src="../assets/svg/logo_ours_noel.7c8ac03.svg"
      alt="Tete ours Tediber"
      width="60"
      height="50"
      class="logo-middle2"
    />
    <a href="#" class="logo-middle1">
      <img
        src="../assets/svg/logo_tediber.0d5d36f.svg"
        alt="Logo Tediber"
        width="70"
        height="50"
      />
    </a>
    <!-- ***** -->
    <a href="#">pub tv</a>
    <a href="#">mon compte</a>
    <a href="#">mag</a>
    <a href="#">contactez-nous</a>
    <!-- ***** -->
    <div class="cart">
      <img
        src="../assets/svg/cart.svg"
        alt="Logo panier"
        width="60"
        height="50"
      />
      <span>{{ nbArticle }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  props: ["nbArticle"],
  methods: {
    myFunction() {
      var x = document.getElementById("myTopnav");
      if (x.className === "topnav") {
        x.className += " responsive";
      } else {
        x.className = "topnav";
      }
    },
  },
};
</script>

<style>
.topnav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 18px 8px;
  border-bottom: 1px solid #979797;
}

.topnav a {
  display: block;
  color: var(--tdb-text);
  text-transform: uppercase;
  text-decoration: none;
  font-size: 12px;
  padding: 12px 0;
}

.topnav a:hover {
  color: var(--tdb-yellow);
}

.topnav a.active {
  color: var(--tdb-yellow);
}

.topnav .icon,
a.logo-middle1 {
  display: none;
}

/* ----- */

.cart {
  position: relative;
}

.cart span {
  position: absolute;
  background-color: var(--tdb-yellow);
  width: 20px;
  height: 20px;
  border-radius: 50%;
  left: 5px;
  top: 0;
  font-size: 0.7em;
  text-align: center;
}

@media screen and (max-width: 685px) {
  .topnav a:not(:first-child):not(:nth-child(2)) {
    display: none;
  }

  .topnav a.icon {
    display: block;
  }

  /* ----- */

  img.logo-middle2 {
    display: none;
  }
}
</style>
