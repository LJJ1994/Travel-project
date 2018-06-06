<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
	    <swiper-slide v-for="item of swiperList" :key="item.id">
	      <img 
	      class="swiper-img"
	      :src="item.imgUrl"
	      >
	    </swiper-slide>
	    <div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
	</div>
</template>

<script type="text/javascript">
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
      	pagination: '.swiper-pagination',
      	loop: true
      },
      swiperList: [{
      	id: '001',
      	imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/3b/ef86879aa50e3002.jpg_750x200_2a108508.jpg'
      },{
      	id: '002',
      	imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg'
      },{
      	id: '003',
      	imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/77/f63bd04dd5319602.jpg_750x200_6ba8e0ca.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper
  	overflow: hidden
  	width: 100%
  	height:0
  	padding-bottom: 31.25%
  	background: #eee
	  .swiper-img
	    width: 100%
</style>
