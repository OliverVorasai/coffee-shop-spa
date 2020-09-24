<template>
  <div>
    <div class="int-coffee-day-container">
      <b-container>
        <b-row align-h="center">
          <h1>Celebrate International Coffee Day with us!</h1>
        </b-row>
        <b-row align-h="center">
          <b-img :src="require('../assets/int-coffee-day.jpg')" fluid></b-img>
        </b-row>
        <b-row align-h="center">
          <h2>Visit us within the next week and receive a 20% discount on all purchases!</h2>
        </b-row>
      </b-container>
    </div>
    <div class="gift-cards-container">
      <b-container>
        <b-row align-h="center">
          <h1>Check out our line-up of designer gift cards!</h1>
        </b-row>
        <b-row align-h="around">
          <b-img class="gift-card" :src="require('../assets/gift-cards/coffee-3.jpg')" fluid></b-img>
          <b-img class="gift-card" :src="require('../assets/gift-cards/thanksgiving-4.jpg')" fluid></b-img>
        </b-row>
        <b-row align-h="center">
          <h2>
            Find more gift cards
            <b-button to="/gift">here!</b-button>
          </h2>
        </b-row>
      </b-container>
    </div>
    <div class="visit-store-container">
      <b-container>
        <b-row align-h="center">
          <h1>Visit our store. Now with takeout discount!</h1>
        </b-row>
        <b-row align-h="center">
          <b-img :src="require('../assets/coffee-shop-interior.jpg')" fluid></b-img>
        </b-row>
        <b-row>
          <p>Coffee Shop focuses on exceptional coffee stemming from exceptional beans to amazing relationships This tradition starts with our founder's family coffee shop which began back in the 1970s. We are deeply committed to always ethically sourcing our ingredients and always striving to provide the highest quality coffee in the west. We are proud to invite you to try our great coffee.</p>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
};
</script>

<style scoped lang="scss">
@import "../../node_modules/bootstrap/scss/functions";
@import "../../node_modules/bootstrap/scss/variables";
@import "../../node_modules/bootstrap/scss/mixins/breakpoints";
.int-coffee-day-container {
  background-color: #dec0a7;
  color: white;
  padding-top: 156px;
  padding-bottom: 50px;
  h1 {
    margin-bottom: 20px;
  }
}

.gift-cards-container {
  padding-top: 50px;
  padding-bottom: 50px;
  background-color: #9a7153;
  color: white;
  h1 {
    margin-bottom: 20px;
  }
}

.visit-store-container {
  padding-top: 50px;
  padding-bottom: 50px;
  h1 {
    margin-bottom: 20px;
  }
  img {
    margin-bottom: 20px;
  }
}

img {
  border-radius: 3% / 5%;
  max-width: 800px;
}

.gift-card {
  max-width: 450px;
  max-height: 300px;
  margin-bottom: 40px;
}
</style>