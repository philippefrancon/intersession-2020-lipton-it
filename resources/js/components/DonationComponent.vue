<template>
  <div>
    <h1 class="layout__title">Faites un don</h1>
    <p
      class="layout__description"
    >Vous pouvez soutenir le projet et l’équipe de développeurs en faisant un don (Visa, Mastercard and American Express)*. </p>
    <button v-if="toggle === false" @click="toggle=true" value="donate" type="button" class="form__submit">
      Donnez
    </button>
    <DonationFormComponent v-if="toggle" />
    <!-- <button v-on:click="(event) => this.$emit('childToParent', event)" value='explication' type="button" class="header__item">explication</button> -->
    <p class="text-danger">* Seuls les dons en euros (€) sont acceptés.</p>
  </div>
</template>

<script>
import DonationFormComponent from "./DonationFormComponent";
export default {
  components: {
    DonationFormComponent,
  },
  data() {
    return {
      toggle: false,
    };
  },
  mounted() {
    localStorage.page = 'donation'
  },
};
</script>


<style scoped>
div {
  display: flex;
  flex-direction: column;
}

button {
  align-self: right;
  font-size: 1em;
  padding: 5px 35px;
}

button:focus {
  outline: none;
}

.text-danger {
  text-align: end;
}
</style>
