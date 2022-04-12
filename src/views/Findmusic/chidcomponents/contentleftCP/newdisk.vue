<template>
  <div id="newdisk">
    <sub-nav-bar>
      <div slot="left" class="left">
        <i class="el-icon-s-help red"></i>
        <p>新碟上架</p>
      </div>

      <div slot="right" class="right">
        <p>更多</p>
        <img src="@/assets/img/to right.svg" alt="" />
      </div>
    </sub-nav-bar>

    <div class="swiper">
      <swiper1>
        <swiper-slide v-for="item in newplaylist" :key="item.id">
          <img :src="item.blurPicUrl" alt="" />
        </swiper-slide>
      </swiper1>
    </div>
  </div>
</template>

<script>
import subNavBar from "@/components/common/subNavBar.vue";
import swiper1 from "@/components/common/swiper.vue";
import { swiperSlide } from "vue-awesome-swiper";
export default {
  name: "newdisk",
  components: {
    subNavBar,
    swiper1,
  },
  created() {
    this.getnewdiskList();
  },

  data() {
    return {
      newplaylist: [],
    };
  },

  methods: {
    async getnewdiskList() {
      const { data: res } = await this.$http.get("/album/newest");
      this.newplaylist = res.albums;
      console.log(this.newplaylist);
    },
  },
};
</script>
<style scoped>
.left {
  display: flex;
  align-items: center;
}
.left i {
  position: relative;
  top: 1px;
  margin-right: 10px;
}

.left p {
  font-size: 20px;
}

.red {
  position: relative;
  top: 3px;
  color: #b1281e;
}

.center {
  position: relative;
  justify-content: center;
}

.right {
  align-items: center;
  display: flex;
}

.right p {
  font-size: 10px;
}

.right p:hover {
  cursor: pointer;
  text-decoration: underline;
}

.right img {
  width: 20px;
}

.swiper {
  padding: 20px 10px;
  height: 300px;
}

img {
  width: 100%;
}
</style>