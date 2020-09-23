<template>
  <div class="container-fluid">
    <h1>Gift Cards</h1>
    <div class="gift-card" v-for="(image, index) in images" :key="index">
      <img :src="image" />
      <img class="gift-card__brand" :src="require('../assets/coffee-cup.svg')" />
      <div class="gift-card__trapezoid"></div>
      <p class="gift-card__price">$10</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "GiftCards",
  data() {
    return {
      images: [],
    };
  },
  mounted() {
    // Get context of entire giftcards folder to load images dynamically
    let context = require.context("../assets/gift-cards/", false, /\.jpg$/);
    context.keys().forEach((key) => {
      this.images.push(context(key));
    });
  },
};
</script>

<style scoped lang="scss">
.container-fluid {
  margin-top: 156px;
}

img {
  height: auto;
  width: 100%;

  border-radius: 3% / 5%;
}

.gift-card {
  max-width: 450px;
  max-height: 300px;
  border-radius: 3% / 5%;
  margin: 20px;

  display: inline-block;
  position: relative;
  top: 0;

  transition: all 0.3s ease;
  box-shadow: 0 2px 3px rgba(0, 0, 0, 0.25);

  .gift-card__brand {
    position: absolute;
    top: 10px;
    right: 10px;
    max-height: 40px;
    max-width: 40px;
  }
}

.gift-card::after {
  content: " ";
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100%;
  height: 100%;
  opacity: 0;
  border-radius: 3% / 5%;
  box-shadow: 0 6px 6px -2px rgba(0, 0, 0, 0.25);
  transition: opacity 0.3s ease;
}

.gift-card:hover {
  top: -8px;
}

.gift-card:hover::after {
  opacity: 1;
}

.gift-card__trapezoid {
  border-bottom: 50px solid rgba(0, 0, 0, 0.25);
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  height: 0;
  width: 200px;
  transform: rotate(135deg);
  position: absolute;
  bottom: 28px;
  right: -47px;
}

.gift-card__price {
  position: absolute;
  bottom: 15px;
  right: 30px;
  transform: rotate(315deg);
  color: white;
  font-size: 2em;
}
</style>