<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(item, index) of list" :key="index">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      list: [
        {
          imgUrl: 'https://source.qunarzz.com/site/images/wns/20190705_qunar_dujia_homepage_top_banner_1.jpg'
        }, {
          imgUrl: 'https://source.qunarzz.com/site/images/wns/2019704_dujia_homepage_top_banner_6.jpg'
        }
      ]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.25%
    .swiper-img
      width: 100%
</style>
