<template>
  <div class="c-input">
    <input
      v-model="info"
      @input="checkField"
      :id="`${placeholder}`"
      :type="`${type}`"
      :placeholder="`${placeholder}`"
      :required="required ? false : true"
    />
    <label :for="`${placeholder}`">
      <i v-if="valid" class="fas fa-check"></i>
      <i v-else-if="required" class="fas fa-check"></i>
      <i v-else class="fas fa-times"></i>
    </label>
  </div>
</template>

<script>
export default {
  name: "InputField",
  data() {
    return {
      info: "",
      valid: false,
      reg: /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/
    };
  },
  props: {
    placeholder: "",
    type: "",
    required: true
  },
  methods: {
    checkField() {
      if (this.type == "email") {
        if (this.reg.test(this.info)) this.valid = true;
        else this.valid = false;
      } else {
        if (this.info != "") this.valid = true;
        else this.valid = false;
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/screen";
@import "@/assets/style/components/input";
</style>