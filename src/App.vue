<template>
  <div class="app">
    <Hero />
    <IPInfo :ipInfoData="ipInfoData" :loading="loading" />
  </div>
</template>

<script>
import Hero from "./components/Hero/Hero";
import IPInfo from "./components/IPInfo/IPInfo";

export default {
  name: "App",
  components: { Hero, IPInfo },
  data() {
    return {
      ip: "",
      loading: true,
      ipInfoData: {},
    };
  },
  methods: {
    async getIPInfoData() {
      try {
        this.loading = true;
        const response = await fetch(`https://ipapi.co/${this.ip}/json/`);
        const data = await response.json();
        this.ipInfoData = data;
        this.loading = false;
      } catch (e) {
        this.loading = false;
        console.log(e);
      }
    },
  },

  created() {
    this.getIPInfoData();
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  display: flex;
  flex-direction: column;
  font-family: "Rubik", sans-serif;
  color: white;
}

input,
button {
  font-family: "Rubik", sans-serif;
}

h1 {
  font-weight: 500;
}

.app {
  display: flex;
  flex-direction: column;
  height: 100vh;
  background: #1e1e1e;
}

.container {
  max-width: 1120px;
  padding: 0 20px;
  margin: 0 auto;
}
</style>
