<template>
  <b-container>
    <b-row align-h="around" align-v="center">
      <h1>{{ imageAlt }}</h1>
      <b-img :src="imageSrc" fluid thumbnail></b-img>
    </b-row>
    <template v-if="nutritionInfo !== null">
      <b-row>
        <p><strong>Nutrition Information</strong></p>
      </b-row>
      <b-row class="row-border-bottom thick-hr">
        <p>{{ nutritionInfo.serving.servingSize.name }} {{ nutritionInfo.serving.servingSize.amount}} {{ nutritionInfo.serving.servingSize.unit }}</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.calories.calories.name }} {{ nutritionInfo.calories.calories.amount }}</strong>
        </p>
        <p>{{ nutritionInfo.calories.caloriesFromFat.name }} {{ nutritionInfo.calories.caloriesFromFat.amount }}</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="end">
        <p>% Daily Value *</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.fat.totalFat.name }}</strong>
          {{ nutritionInfo.fat.totalFat.amount }} {{ nutritionInfo.fat.totalFat.unit }}
        </p>
        <p>{{ nutritionInfo.fat.totalFat.percent }}%</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p class="ml-4">{{ nutritionInfo.fat.saturatedFat.name }} {{ nutritionInfo.fat.saturatedFat.amount }} {{ nutritionInfo.fat.saturatedFat.unit }}</p>
        <p>{{ nutritionInfo.fat.saturatedFat.percent }}%</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p class="ml-4">{{ nutritionInfo.fat.transFat.name }} {{ nutritionInfo.fat.transFat.amount }} {{ nutritionInfo.fat.transFat.unit }}</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.cholesterol.cholesterol.name }}</strong>
          {{ nutritionInfo.cholesterol.cholesterol.amount }} {{ nutritionInfo.cholesterol.cholesterol.unit }}
        </p>
        <p>{{ nutritionInfo.cholesterol.cholesterol.percent }}%</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.sodium.sodium.name }}</strong>
          {{ nutritionInfo.sodium.sodium.amount }} {{ nutritionInfo.sodium.sodium.unit }}
        </p>
        <p>{{ nutritionInfo.sodium.sodium.percent }}%</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.carbohydrates.totalCarbohydrates.name }}</strong>
          {{ nutritionInfo.carbohydrates.totalCarbohydrates.amount }} {{nutritionInfo.carbohydrates.totalCarbohydrates.unit}}
        </p>
        <p>{{ nutritionInfo.carbohydrates.totalCarbohydrates.percent }}%</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p class="ml-4">{{ nutritionInfo.carbohydrates.fiber.name }} {{ nutritionInfo.carbohydrates.fiber.amount }} {{nutritionInfo.carbohydrates.fiber.unit}}</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p class="ml-4">{{ nutritionInfo.carbohydrates.sugar.name }} {{ nutritionInfo.carbohydrates.sugar.amount }} {{nutritionInfo.carbohydrates.sugar.unit}}</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.protein.protein.name }}</strong>
          {{ nutritionInfo.protein.protein.amount}} {{ nutritionInfo.protein.protein.unit }}
        </p>
        <p>{{ nutritionInfo.protein.protein.percent }}%</p>
      </b-row>
      <b-row class="row-border-bottom" align-h="between">
        <p>
          <strong>{{ nutritionInfo.caffeine.caffeine.name }}</strong>
          {{ nutritionInfo.caffeine.caffeine.amount }} {{ nutritionInfo.caffeine.caffeine.unit }}
        </p>
      </b-row>
    </template>
  </b-container>
</template>

<script>
export default {
  name: "NutritionFactsComponent",
  props: {
    imageSrc: String,
    imageAlt: String,
  },
  data() {
    return {
      nutritionInfo: null,
    };
  },
  mounted() {
    this.nutritionInfo = {};
    this.nutritionInfo = Object.assign({}, this.nutritionInfo, {
      serving: {
        servingSize: {
          name: "Serving Size",
          amount: 16,
          unit: "fl oz",
        },
      },
      calories: {
        calories: {
          name: "Calories",
          amount: 240,
        },
        caloriesFromFat: {
          name: "Calories From Fat",
          amount: 40,
        },
      },
      fat: {
        totalFat: {
          name: "Total Fat",
          amount: 4.5,
          unit: "g",
          percent: 6,
        },
        saturatedFat: {
          name: "Saturated Fat",
          amount: 2,
          unit: "g",
          percent: 10,
        },
        transFat: {
          name: "Trans Fat",
          amount: 0,
          unit: "g",
        },
      },
      cholesterol: {
        cholesterol: {
          name: "Cholesterol",
          amount: 20,
          unit: "mg",
          percent: 7,
        },
      },
      sodium: {
        sodium: {
          name: "Sodium",
          amount: 115,
          unit: "mg",
          percent: 5,
        },
      },
      carbohydrates: {
        totalCarbohydrates: {
          name: "Total Carbohydrates",
          amount: 45,
          unit: "g",
          percent: 16,
        },
        fiber: {
          name: "Dietary Fiber",
          amount: 0,
          unit: "g",
        },
        sugar: {
          name: "Sugars",
          amount: 42,
          unit: "g",
        },
      },
      protein: {
        protein: {
          name: "Protein",
          amount: 8,
          unit: "g",
          percent: 16,
        },
      },
      caffeine: {
        caffeine: {
          name: "Caffeine",
          amount: 95,
          unit: "mg",
        },
      },
    });
  },
};
</script>

<style scoped lang="scss">
img {
  max-width: 200px;
  max-height: 200px;
}

p {
  margin-bottom: 0;
}

.row-border-bottom {
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  &.thick-hr {
    border-bottom: 5px solid rgba(0, 0, 0, 0.1);
  }
  padding-top: 0.5em;
  padding-bottom: 0.5em;
}
</style>