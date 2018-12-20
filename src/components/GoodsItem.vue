<template>
  <div class="GoodsItemWrapper">
    <div class="GoodsSupplier" ><span style="font-size: 12px;margin-top: 8px;color: #6B6967" v-show="false">本商品由王大发农产品专供</span></div>
    <div class="GoodsCover" >
      <img    class="CoverImg" :src="ItemData.ProductImage" >
      <div class="GoodsMask" v-show="false"></div>
    </div>
    <div class="GoodsName ratina-bd bd-b">
      <span>{{ItemData.ProductName}} {{ItemData.Specifications}}</span>
      <div style="display: flex;width: 100%">
        <div style="flex: 2">
          <span style="font-size: 12px;color: #6B6967;margin-top: 3px;margin-bottom: 8px" v-show="false">{{ItemData.StandardUnit}} </span>
        </div>
        <div style="flex: 8;display: flex;justify-content: flex-end;">
          <div style="font-size: 12px;color: #6B6967;margin-top: 3px;margin-bottom: 8px"> <label v-show="ItemData.SalesAmount !== 0">已售<label style="color:#FD6803;">{{ItemData.SalesAmount}}</label>份</label><label v-show="ItemData.SalesAmount !== 0 && ItemData.InventoryAmount !== 0">/</label><label v-show="ItemData.InventoryAmount !== 0">限量{{ItemData.InventoryAmount}}份</label></div>
        </div>
      </div>
    </div>
    <div class="GoodsSaleTime">
      <div class="SaleTimeBegin">
        <span style="font-size: 12px;color: #6B6967">预售时间：<label style="color:#FD6803;">{{ItemData.SaleTime}}</label></span>
      </div>
      <div class="SaleTimeEnd" style="display: flex;justify-content: flex-end">
        <span v-show="ItemData.LimitNum > 0" style="font-size: 12px;color: #6B6967 ">每人限购{{ItemData.LimitNum}}份</span>
      </div>
    </div>
    <div class="GoodsSaleTime">
      <div class="SaleTimeBegin">
        <span style="font-size: 12px;color: #6B6967;">提货时间：<label style="color:#FD6803;">{{ItemData.GetTime}}</label></span>
      </div>
      <div class="SaleTimeEnd">
      </div>
    </div>
    <div class="GoodsPrice ratina-bd bd-b">
      <div class="Prcie">
        <span ><label style="color:#FD6803;">¥{{ItemData.Price}}</label><label style="margin-left: 15px;color: #6B6967;text-decoration:line-through">¥{{ItemData.OriginalPrice}}</label></span>
      </div>
      <div class="AddCart">
        <div style="display: flex;align-items: center;margin-right: 8px" v-show="!ItemData.Isvalid"><label style="font-size: 12px;color: #6B6967">数量：<label style="color:#FD6803;">{{ItemData.Count}}</label></label></div>
        <van-button type="danger" size="small" plain >添加到购物车
        </van-button>
      </div>

    </div>
  </div>
</template>

<script>
  import '../common/stylus/1px.css'
  export default {
    props: {
      ItemData: {},
      Index: 0
    },
    data () {
      return {
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .GoodsItemWrapper
    width :100%
    height :100%
    .GoodsSupplier
      display :flex
      justify-content :center
    .GoodsCover
      margin-top :14px
      margin-left :14px
      margin-right :14px
      position:relative
      .CoverImg
        object-fit: cover
        width: 100%
        height: 180px
    .GoodsMask
      position: absolute
      z-index: 3
      top: 0px
      left: 0px
      width: 100%
      height: 11.3rem
      background: url("http://cmall.longyu365.cn/m/static/img/indexmask.png")
      background-size: 22rem 11.3rem
    .GoodsName
      margin-left :14px
      margin-right :14px
      margin-top :8px
      display :flex
      flex-direction: column
    .GoodsSaleTime
      display :flex
      margin-left :14px
      margin-right :14px
      .SaleTimeBegin
        flex :1
        display :flex
        margin-top :6px
        align-items : center
      .SaleTimeEnd
        flex :1
        display :flex
        margin-top: 6px
        align-items : center
    .GoodsPrice
      margin-left :14px
      margin-right :14px
      display :flex
      padding-bottom :6px
      .Prcie
        flex :1
        margin-top :6px
        display : flex
        align-items :center
      .AddCart
        flex :1
        display :flex
        justify-content : flex-end
        margin-top :6px
    .GoodsShare
      display :flex
      margin-left :14px
      margin-right :14px
      justify-content :flex-start
      margin-top :5px
</style>
