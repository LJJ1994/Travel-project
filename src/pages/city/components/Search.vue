<template>
	<div>
		<div class="search">
			<input v-model="keyword" class="search-input" type="text" placeholder="请输入城市名/拼音">
		</div>
		<div class="search-content" ref="search" v-show="keyword">
			<ul>
				<li
				 class="search-item border-bottom" 
				 v-for="item of list" 
				 :key="item.id"
				 @click="handleChangeCity(item.name)">{{ item.name }}</li>
				<li class="search-item border-bottom" v-show="hasList">没有匹配到数据</li>
			</ul>
		</div>
	</div>
</template>

<script type="text/javascript">
import Bscroll from 'better-scroll'
export default {
	name: 'Search',
	props: {
		cities: Object
	},
	data () {
		return {
			keyword: '',
			list: [],
			timer: null
		}
	},
	methods: {
		handleChangeCity (city) {
			this.$store.commit('changeCity',city)
			this.$router.push('./')
		}
	},
	computed: {
		hasList(){
			return !this.list.length
		} 
	},
	watch: {
		keyword () {
			if(this.timer){
				clearTimeout(this.timer)
			}
			if(!this.keyword){
				this.list = []
				return
			}
			this.timer = setTimeout(() => {
				const result = []
				for(let i in this.cities){
					this.cities[i].forEach((value)=>{
						if(value.spell.indexOf(this.keyword) > -1 ||
							value.name.indexOf(this.keyword) > -1){
							result.push(value)
						}
					})
				}
				this.list = result
			},100)
		}
	},
	mounted () {
		this.scroll = new Bscroll(this.$refs.search)
	}
}
</script>

<style lang="stylus" scoped>
	.search
		border-sizing: border-box
		height: .66rem
		background: #804e9a
		padding: 0 .05rem
		.search-input
			width: 100%
			height: .62rem
			line-height: .62rem
			border-radius: .06rem
			text-align: center
	.search-content
		z-index: 1
		position: absolute
		overflow: hidden
		top: 1.52rem
		left: 0
		right: 0
		bottom: 0
		background: #f7f4f4
		.search-item
			line-height: .62rem
			padding-left: .2rem
			color: #666
</style>