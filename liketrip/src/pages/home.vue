<template>
    <div>
        <Header></Header>
        <Swiper :list="swiperList"></Swiper>
        <Menun :list="iconList"></Menun>
         <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
   </div>
</template>
<script>
import Header from '@/components/Header'
import Swiper from '@/components/Swiper'
import Menun from '@/components/Menun'
import HomeRecommend from '@/components/Recommend'
import HomeWeekend from '@/components/Weekend'
import axios from 'axios'
export default {
  components: {
    Header,
    Swiper,
    Menun,
    HomeRecommend,
    HomeWeekend

  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  // computed: {
  //   ...mapState(['city'])
  // },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>
<style>

</style>
