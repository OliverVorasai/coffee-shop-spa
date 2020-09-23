<template>
  <b-container class="menu-container">
    <h1>Menu</h1>
    <b-row class="mx-auto">
      <h2>Drinks</h2>
    </b-row>
    <b-row class="mx-auto" v-for="obj in drinks" :key="obj.groupName">
      <b-col>
        <h3>{{ obj.groupName }}</h3>
        <b-row class="menu-items-alignment">
          <div v-for="(imageObj, index) in obj.images" :key="index">
            <img :src="imageObj.path" />
            <p>{{ imageObj.name }}</p>
          </div>
        </b-row>
      </b-col>
    </b-row>
    <b-row class="mx-auto">
      <h2>Food</h2>
    </b-row>
    <b-row class="mx-auto" v-for="obj in food" :key="obj.groupName">
      <b-col>
        <h3>{{ obj.groupName }}</h3>
        <b-row class="menu-items-alignment">
          <div v-for="(imageObj, index) in obj.images" :key="index">
            <img :src="imageObj.path" />
            <p>{{ imageObj.name }}</p>
          </div>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Menu",
  data() {
    return {
      drinks: [], // Array of Objects
      food: [], // Array of Objects
    };
  },
  mounted() {
    // require.context cannot take a variable as path, so must do manually here
    let coffeeContext = require.context("../assets/menu-items/drinks/coffee/", false, /\.svg$/);
    let iceCoffeeContext = require.context("../assets/menu-items/drinks/ice-coffee/", false, /\.svg$/);
    let frappeContext = require.context("../assets/menu-items/drinks/frappe/", false, /\.svg$/);
    let teaContext = require.context( "../assets/menu-items/drinks/tea/", false, /\.svg$/);
    let drinksOtherContext = require.context("../assets/menu-items/drinks/other/", false, /\.svg$/);
    let cakeContext = require.context("../assets/menu-items/food/cake/", false, /\.svg$/);
    let cookiesContext = require.context( "../assets/menu-items/food/cookies/", false, /\.svg$/);
    let pastriesContext = require.context("../assets/menu-items/food/pastries/", false, /\.svg$/);
    let foodOtherContext = require.context("../assets/menu-items/food/other/", false, /\.svg$/);
    
    // Note: Group name must be unique
    this.drinks.push(this.loadImages2(coffeeContext, "Coffee"));
    this.drinks.push(this.loadImages2(iceCoffeeContext, "Ice Coffee"));
    this.drinks.push(this.loadImages2(frappeContext, "Frappe"));
    this.drinks.push(this.loadImages2(teaContext, "Tea"));
    this.drinks.push(this.loadImages2(drinksOtherContext, "Other Drinks"));
    this.food.push(this.loadImages2(cakeContext,"Cake"));
    this.food.push(this.loadImages2(cookiesContext,"Cookies"));
    this.food.push(this.loadImages2(pastriesContext,"Pastries"));
    this.food.push(this.loadImages2(foodOtherContext,"Other Foods"));
  },
  methods: {
    loadImages(imageContext, store) {
      imageContext.keys().forEach((key) => {
        store.push({
          name: key.slice(2, -4),
          path: imageContext(key),
        });
      });
    },
    loadImages2(imageContext, groupName) {
      let obj = {};
      obj.groupName = groupName;
      obj.images = [];
      imageContext.keys().forEach((key) => {
        obj.images.push({
          name: key.slice(2, -4),
          path: imageContext(key),
        });
      });
      return obj;
    }
  },
};
</script>

<style scoped lang="scss">
@import '../../node_modules/bootstrap/scss/functions';
@import '../../node_modules/bootstrap/scss/variables';
@import '../../node_modules/bootstrap/scss/mixins/breakpoints';
.menu-container {
  margin-top: 156px;
}

.menu-items-alignment {
  @include media-breakpoint-down(md) {
    justify-content: space-between;
  }
  
  @include media-breakpoint-up(md) {
    justify-content: start;
    div {
      margin-right: 80px;
    }
  }
}

img {
  width: 160px;
  height: 160px;
}
</style>