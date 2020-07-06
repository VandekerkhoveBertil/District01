<template>
  <form @submit="checkForm" class="c-form">
    <div>
      <RadioGroup ref="Geslacht" />
      <div class="u-double">
        <InputField placeholder="Voornaam" type="text" ref="Voornaam" />
        <InputField placeholder="Naam" type="text" ref="Naam" />
      </div>
      <InputField placeholder="Nummerplaat" type="text" ref="Nummerplaat" />
      <InputField placeholder="Email" type="email" ref="Email" />
      <InputField placeholder="Straat" type="text" ref="Straat" />
      <div class="u-double">
        <InputField placeholder="Nummer" type="number" ref="Nummer" />
        <InputField placeholder="Bus" type="text" required="false" ref="Bus" />
      </div>
      <div class="u-double">
        <InputField placeholder="Stad" type="text" ref="Stad" />
        <InputField placeholder="Postcode" type="number" ref="Postcode" />
      </div>
      <InputField placeholder="Telefoon" type="tel" ref="Telefoon" />
      <ActionsCheck ref="ActionsCheck" />
    </div>

    <button type="submit">Bevestigen</button>
  </form>
</template>

<script>
import RadioGroup from "./RadioGroup.vue";
import InputField from "./InputField.vue";
import ActionsCheck from "./ActionsCheck.vue";

export default {
  name: "Form",
  components: {
    RadioGroup,
    InputField,
    ActionsCheck
  },
  methods: {
    checkForm: function(e) {
      e.preventDefault();

      let jsonText = "{";
      jsonText += '"Aanspreektitel" : "' + this.$refs.Geslacht.info + '",';
      jsonText += '"Voornaam" : "' + this.$refs.Voornaam.info + '",';
      jsonText += '"Naam" : "' + this.$refs.Naam.info + '",';
      jsonText += '"Nummerplaat" : "' + this.$refs.Nummerplaat.info + '",';
      jsonText += '"Email" : "' + this.$refs.Email.info + '",';
      jsonText += '"Straat" : "' + this.$refs.Straat.info + '",';
      jsonText += '"Nummer" : "' + this.$refs.Nummer.info + '",';
      jsonText += '"Bus" : "' + this.$refs.Bus.info + '",';
      jsonText += '"Stad" : "' + this.$refs.Stad.info + '",';
      jsonText += '"Postcode" : "' + this.$refs.Postcode.info + '",';
      jsonText += '"Telefoon" : "' + this.$refs.Telefoon.info + '",';
      jsonText += '"Acties" : "' + this.$refs.ActionsCheck.info + '"';
      jsonText += "}";
      console.log(jsonText);
    }
  }
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/screen";
@import "@/assets/style/components/radio";

.c-form {
  width: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
}

.u-double {
  display: flex;
}

button {
  margin-top: 2em;
  padding: 0.8em;
  width: 180px;

  font-size: 0.8em;

  border: none;
  border-radius: 4px;
  background-color: $global-primary;
  color: $global-white;
}

@media only screen and (min-width: 440px) {
  button {
    width: 320px;
  }
}
</style>