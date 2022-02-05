<template>
  <div class="container">
    <div v-if="loading" class="ip-details">
      <h1>Carregando dados...</h1>
    </div>
    <div v-else class="ip-details">
      <div>
        <span>Ip address</span>
        <p>{{ ipInfoData.ip }}</p>
      </div>
      <div>
        <span>Location</span>
        <p>{{ ipInfoData.region + ", " + ipInfoData.country_code }}</p>
      </div>
      <div>
        <span>Timezone</span>
        <p>{{ ipInfoData.timezone }}</p>
      </div>
      <div>
        <span>ISP</span>
        <p>{{ ipInfoData.org }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IPDetails",
  props: {
    loading: Boolean,
    ipInfoData: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped src="./styles.css"></style>
