<template>
  <div class="hero">
    <div class="container">
      <h1>IP Adress Tracker</h1>
      <form @submit.prevent="onSubmit">
        <input
          type="text"
          name=""
          placeholder="Search for any IP address ex: 168.10.1.29"
          id=""
          v-model="ip"
        />
        <button type="submit">
          <img src="../../assets/icon-arrow.svg" alt="" srcset="" />
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import { ValidateIPaddress } from "./../../validations/ip";
export default {
  name: "Hero",
  data() {
    return {
      ip: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.ip.length === 0) {
        alert("Insira um endereco ip!");
        return;
      }

      if (!ValidateIPaddress(this.ip)) {
        alert("O endereço de IP fornecido não é valido!");
        return;
      }

      this.$emit("getIPInfoData", this.ip);
    },
  },
};
</script>
<style scoped src="./styles.css"></style>
