<template>
	<div class="search" ref="wrapper">
		<div>
			<div class="area">
				<div class="title border-topbottom">当前城市</div>
				<div class="button-list">
					<div class="button-wrapper">
						<div class="button">{{this.$store.state.city}}</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="title border-topbottom">热门城市</div>
				<div class="button-list">
					<div
					 class="button-wrapper"
					 v-for="item in hotCities"
					 :key="item.id"
					 @click="handleChangeCity(item.name)">
						<div class="button">{{ item.name }}</div>
					</div>
				</div>
			</div>
			<div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
				<div class="title border-topbottom">{{ key }}</div>
				<div
				 class="item-list" 
				 v-for="innerItem in item"
				 :key="innerItem.id"
				 @click="handleChangeCity(innerItem.name)">
					<div class="item border-bottom">{{ innerItem.name }}</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
	name: 'List',
	props: {
		hotCities: Array,
		cities: Object,
		letter: String
	},
	methods: {
		handleChangeCity (city) {
			this.$store.commit('changeCity',city)
			this.$router.push('./')
		}
	},
	mounted () {
		this.scroll = new BScroll(this.$refs.wrapper)
	},
	watch: {
		letter () {
			if (this.letter) {
				const element = this.$refs[this.letter][0]
				this.scroll.scrollToElement(element)
			}
		}
	}
}
</script>

<style lang="stylus" scoped>
	.border-topbottom
		&:before
			border-color: #7d7373
		&:after
			border-color: #7d7373
	.border-bottom
		&:before
			border-color: #ccc
	.search
		position: absolute
		overflow: hidden
		top: 1.45rem
		left: 0
		right: 0
		bottom: 0
		.title
			line-height: .54rem
			background: #f1ecec
			padding-left: .2rem
			color: #777
			font-size: .26rem
		.button-list
			overflow: hidden
			padding: .1rem
			padding: .01rem .6rem .01rem .01rem
			.button-wrapper
				float: left
				width:33.3%
				.button
					text-align: center
					margin: .1rem
					border: .01rem solid #ccc
					padding: .1rem 0
					border-radius: .06rem
		.item-list
			.item
				line-height: .74rem
				padding-left: .2rem
</style>