<template>
  <div>
    <home-header></home-header>
    <home-swiper :swiper="SwiperList"></home-swiper>
    <home-icons :list="IconsList"></home-icons>
    <home-recommend :list="RecommendList"></home-recommend>
    <home-weekend :list="WeekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      SwiperList: [],
      IconsList: [],
      RecommendList: [],
      WeekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.SwiperList = data.swiperList
        this.IconsList = data.iconList
        this.RecommendList = data.recommendList
        this.WeekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
