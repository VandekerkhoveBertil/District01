<template>
  <div>
    <label class="c-checkbox">
      Hou mij op de hoogte wanneer er interessante acties zijn bij Q Team.
      <input
        v-model="info"
        id="wantEmails"
        type="checkbox"
      />
      <span class="checkmark"></span>
    </label>
  </div>
</template>

<script>
export default {
  name: "ActionsCheck",
  data() {
    return {
      info: ""
    };
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/screen";
@import "@/assets/style/components/checkbox";

div {
  display: flex;
  justify-content: flex-start;
  margin-top: 1em;
}
</style>