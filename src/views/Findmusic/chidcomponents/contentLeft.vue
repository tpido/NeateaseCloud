<template>
  <div id="contentLeft">
    <hot-recommend></hot-recommend>
    <recman-playlist></recman-playlist>
    <new-disk></new-disk>
  </div>
</template>

<script>
import hotRecommend from "./contentleftCP/hotrecommend.vue";
import newDisk from "./contentleftCP/newdisk.vue";
import recmanPlaylist from "./contentleftCP/recmanplaylist.vue";
export default {
  name: "",
  components: {
    hotRecommend,
    recmanPlaylist,
    newDisk,
  },
};
</script>
<style scoped>
#contentLeft {
  padding: 4px 15px;
  height: 1425px;
  width: 729px;
}
</style>