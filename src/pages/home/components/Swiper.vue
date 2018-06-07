<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="swiperShow">
	    <swiper-slide v-for="item of swiper" :key="item.id">
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
  props: {
    swiper: Array
  },
  data () {
    return {
      swiperOption: {
      	pagination: '.swiper-pagination',
      	loop: true
      },
    }
  },
  computed: {
    swiperShow () {
      return this.swiper.length
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
  	height:0
  	padding-bottom: 31.25%
  	background: #eee
	  .swiper-img
	    width: 100%
</style>
