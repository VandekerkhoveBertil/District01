<template>
  <div class="c-radio-group">
    <label class="c-radio">
      Dhr.
      <input v-model="info" v-bind:value="'Dhr.'" type="radio" checked="checked" name="radio" />
      <span class="checkmark"></span>
    </label>
    <label class="c-radio">
      Mevr.
      <input v-model="info" v-bind:value="'Mevr.'" type="radio" name="radio" />
      <span class="checkmark"></span>
    </label>
  </div>
</template>

<script>
export default {
  name: "RadioGroup",
  data() {
    return {
      info: "Dhr."
    };
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/screen";
@import "@/assets/style/components/radio";
</style>