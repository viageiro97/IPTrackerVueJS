<template>
  <div class="ip-info">
    <IPDetails :ipInfoData="ipInfoData" :loading="loading" />
    <Map :center="center" :zoom="7" />
  </div>
</template>

<script>
import IPDetails from "./IPDetails/IPDetails";
import Map from "./IPLocationMap/Map";

export default {
  name: "IPInfo",
  props: {
    loading: Boolean,
    ipInfoData: {
      type: Object,
      require: true,
    },
  },
  components: {
    IPDetails,
    Map,
  },
  computed: {
    center: function () {
      return [this.ipInfoData.latitude || 0, this.ipInfoData.longitude || 0];
    },
  },
};
</script>

<style scoped>
.ip-info {
  position: relative;
  flex: 1;
}
</style>
