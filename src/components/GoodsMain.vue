<template>
  <div class="goods-main">
    {{msg}}
    <GoodsHeader/>
    <div class="goods-blocks">
          <SideBar/>
          <GoodsContent/>
    </div>
   
  </div>  
</template>
<script>
import GoodsHeader from './Goods/GoodsHeader'
import SideBar from './Goods/SideBar'
import GoodsContent from './Goods/GoodsContent.vue'

export default {
  name: 'GoodsMain',
  components: {
   GoodsHeader,
   SideBar,
   GoodsContent
 
  }
}
</script>
<style lang="scss">

.goods-main {
    width: 1920px;
    height: 1191px;
    background: rgba(18, 20, 52, 0.9);
    backdrop-filter: blur(48px);
    font-family: 'Gotham Pro';
    font-style: normal;
    font-weight: 700;
    font-size: 18px;
    line-height: 25px;
    /* or 139% */

    letter-spacing: -0.04em;

    color: #FFFFFF;
}

.goods-blocks{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    
}
   
</style>
