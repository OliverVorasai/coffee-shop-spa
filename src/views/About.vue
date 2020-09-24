<template>
  <b-container class="about-container">
    <div class="about">
      <h1>About Coffee Shop SPA</h1>
      <hr />
      <h2>What is this?</h2>
      <p>This is an example coffee shop website utilizing Vue.js to provide a faster and more consistent web browsing experience.</p>
      <hr />
      <h2>Contact Me</h2>
      <p>Made by Oliver Vorasai. My website can be found at <a href="https://olivervorasai.com" target="_blank">https://olivervorasai.com</a></p>
      <p>You can contact me through email at <a href="mailto:olivervorasai@gmail.com">olivervorasai@gmail.com</a></p>
    </div>
  </b-container>
</template>

<script>
export default {
  name: "About",
};
</script>

<style scoped>
.about-container {
  margin-top: 156px;
  min-height: calc(100vh - 156px - 100px);
}
</style>