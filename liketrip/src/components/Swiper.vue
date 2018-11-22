<template>
<div class="Swiper-wraper">
    <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="(item, index) in SwipeList" :key="index">
            <img class="banner-img" :src="item.imgUrl" alt="">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
</div>
</template>

<script>
export default {
  name: 'carrousel',
  data () {
    return {
      swiperOption: {
        loop: true,
        pagination: '.swiper-pagination'
      },
      SwipeList: [
        {
          id: 1,
          imgUrl: 'https://dimg04.c-ctrip.com/images/700m0y000000m60y3000A_750_150_25.jpg'
        },
        {
          id: 2,
          imgUrl: 'https://dimg04.c-ctrip.com/images/70010y000000lzzqjDFC1_750_150_25.jpg'
        },
        {
          id: 3,
          imgUrl: 'https://dimg04.c-ctrip.com/images/70050y000000lv9wx9D8C_750_150_25.jpg'
        },
        {
          id: 4,
          imgUrl: 'https://dimg04.c-ctrip.com/images/700k0x000000ll8fgB6E5_750_150_25.jpg'
        }
      ]
    }
  },
  computed: {},
  mounted () {}
}
</script>
<style lang="stylus">
 .swiper-pagination-bullet-active {
    opacity: 1;
    background: #fff
}
.Swiper-wraper
  overflow:hidden
  width:100%
  height:0
  padding-bottom:31.3%
 .banner-img {
    width: 100%
    height 100%
}
</style>
