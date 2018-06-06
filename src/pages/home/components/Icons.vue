<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page,index) in pages" :key="index">
        <div
          class="icon"
          v-for="item in page"
          :key="item.id"
        >
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-content">{{ item.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script type="text/javascript">
export default {
    name: 'HomeIcons',
    data () {
      return {
        iconList: [{
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        }, {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
          desc: '游乐场'
        }, {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
          desc: '水上花园'
        }, {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
          desc: '城市观光'
        }, {
          id: '005',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          desc: '一日游'
        }, {
          id: '006',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          desc: '动植物园'
        }, {
          id: '007',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
          desc: '海滨海岛'
        }, {
          id: '008',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
          desc: '东部华侨城'
        }, {
          id: '009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
          desc: 'hey'
        }]
      }
    },
    computed: {
      pages () {
        const pages = []
        this.iconList.forEach((item,index) => {
          const page = Math.floor(index/8)
          if(!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varible.styl'
  .icons >>> .swiper-container
    overflow: hidden
    height: 0
    padding-bottom: 50%
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-content
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      text-align: center
      color: #212121
      ellipsis()
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis

</style>
