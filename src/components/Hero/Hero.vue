<template>
  <div class="hero">
    <div class="container">
      <h1>IP Adress Tracker</h1>
      <form @submit.prevent="onSubmit">
        <input
          type="text"
          name=""
          placeholder="Search for any IP address"
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
export default {
  name: "Hero",
  data() {
    return {
      ip: "",
    };
  },
  methods: {
    onSubmit() {
      console.log("submetendo");
      if (!this.ip) {
        alert("Insira um endereco ip!");
        return;
      }
    },
  },
};
</script>
<style scoped src="./styles.css"></style>
