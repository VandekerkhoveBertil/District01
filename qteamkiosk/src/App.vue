<template>
  <div class="c-app">
    <img class="c-logo" src="/img/logo.png" alt="Qteam logo" />
    <h1 class="c-title">
      <span>VUL UW</span> GEGEVENS AAN
    </h1>
    <Form />
    <img class="c-image" src="/img/working_man.jpg" alt="Picture of a working man" />
  </div>
</template>

<script>
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    Form
  },

  created() {}
};
</script>

<style lang="scss">
@import "@/assets/style/screen";
</style>
