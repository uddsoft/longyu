<template>
    <div class="BuyListWrapper">
      <div class="GoodsList" >
        <scroll-view :scroll-y="true" :style="'height: '+windowHeight+'px'" @scrolltolower="scrolltolower">
        <van-search
          :value="SecValue"
          placeholder="请输入搜索关键词"
          use-action-slot
          bind:search="onSearch"
        >
          <view slot="action" @click="onSearch">搜索</view>
        </van-search>
        <ul>
          <li v-for="(item,index) in list" :key="index" style="background-color: white">
            <GoodsItem :ItemData="item" ></GoodsItem>
            <div style="width: 100%;height: 8px;background-color: rgb(242, 242, 242)"></div>
          </li>
        </ul>
        </scroll-view>
      </div>
      <van-tabbar :active="active" @change="onChange">
        <van-tabbar-item icon="shop">首页</van-tabbar-item>
        <van-tabbar-item icon="cart-o" info="5">购物车</van-tabbar-item>
        <van-tabbar-item icon="contact" info="20">我</van-tabbar-item>
      </van-tabbar>
    </div>

</template>

<script>
  import GoodsCard from '../../components/GoodsCard'
  import GoodsItem from '../../components/GoodsItem'
  export default {
    name: 'index.vue',
    data () {
      return {
        windowHeight: wx.getSystemInfoSync().windowHeight - 50,
        SecValue: '',
        active: 0,
        list: [
          {'ProductName': '红尖椒',
            'ProductImage': 'http://cmall.longyu365.cn/Uploads/imges/20181125/50e4cf20181125094425.jpg',
            'Specifications': '约1斤',
            'StandardUnit': '份',
            'SalesAmount': '100',
            'InventoryAmount': '110',
            'SaleTime': '12月19日',
            'LimitNum': '10',
            'GetTime': '12月20日',
            'OriginalPrice': 4,
            'Price': 0.01,
            'Count': 1
          },
          {'ProductName': '螺丝椒',
            'ProductImage': 'http://cmall.longyu365.cn/Uploads/imges/20181125/314f0320181125094200.jpg',
            'Specifications': '约1斤',
            'StandardUnit': '份',
            'SalesAmount': '100',
            'InventoryAmount': '110',
            'SaleTime': '12月19日',
            'LimitNum': '10',
            'GetTime': '12月20日',
            'OriginalPrice': 4,
            'Price': 0.01,
            'Count': 1
          },
          {'ProductName': '朝天椒',
            'ProductImage': 'http://cmall.longyu365.cn/Uploads/imges/20181125/75655120181125095002.jpg',
            'Specifications': '约1斤',
            'StandardUnit': '份',
            'SalesAmount': '100',
            'InventoryAmount': '110',
            'SaleTime': '12月19日',
            'LimitNum': '10',
            'GetTime': '12月20日',
            'OriginalPrice': 4,
            'Price': 0.01,
            'Count': 1
          }
        ]
      }
    },
    methods: {
      onSearch () {
        console.log('用户搜索')
      },
      onChange (event) {
        console.log(event)
        if (this.active === 1) {
          console.log('购物车')
        }
      },
      scrolltolower () {
        console.log('滚动条已到底部。请获取数据。')
      },
      scroll () {
        console.log('用户在滚动')
      }
    },
    components: {
      GoodsCard,
      GoodsItem
    },
    onPullDownRefresh () {
      // 下拉刷新
      console.log('下拉刷新')
    },
    onReachBottom () {
      // 上拉加载
      console.log('上拉加载')
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus"  scoped>
.BuyListWrapper
  position : fixed
  left :0
  top:0
  bottom :0
  width :100%
  height :100%
  background-color :rgb(242, 242, 242)
  .GoodsList
    position : absolute
    top: 0px
    bottom: 48px
    width : 100%
    overflow : hidden
</style>
