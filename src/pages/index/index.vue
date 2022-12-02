<template>
  <view class="index">


    <view v-if="state.banners.length>0" class="top-slider">
      <nut-swiper class="top-slider-block" :init-page="0" :pagination-visible="true" pagination-color="#426543"
                  auto-play="3000">
        <nut-swiper-item v-for="item in state.banners" :key="item.cover">
          <image class='img-cover' mode="aspectFill" :src="item.cover"/>
        </nut-swiper-item>
      </nut-swiper>
    </view>

  </view>
</template>

<script setup>
import {reactive, } from 'vue';

const state = reactive({
  banners: []
});

setTimeout(() => {
  const data = [{
    "id": 5,
    "cover": "https://cdn.anlulu.com/hero/img/banner0.jpg",
  }, {
    "id": 4,
    "cover": "https://cdn.anlulu.com/hero/img/banner20223.png",
  }, {
    "id": 2,
    "cover": "https://cdn.anlulu.com/hero/img/banner2.jpg",
  }, {
    "id": 3,
    "cover": "https://cdn.anlulu.com/hero/img/banner0.jpg",
  }, {
    "id": 1,
    "cover": "https://cdn.anlulu.com/hero/img/banner1.jpg",
  }];
  state.banners.push(...data);
}, 1000);
</script>

<style lang="scss">
.index {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: orangered;
  padding: 12px;
}

.top-slider {
  background: var(--dream-primary-color);

  .top-slider-block {
    border-radius: 4px;
    overflow: hidden;
    line-height: 40vw;
    height: 40vw;
  }

  .swiper-pagination {
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: flex-end;
  }

  .swiper-item {
    line-height: 40vw;
    height: 40vw;
  }

  taro-image-core.img-cover, .img-cover {
    border-radius: 4px;
    overflow: hidden;
    display: block;
    width: 100%;
    height: 100%;
    //object-fit: cover;
    //object-position:50% 50%;
  }
}

</style>
