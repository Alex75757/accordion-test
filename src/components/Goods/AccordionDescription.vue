<template>
 <div v-for="item of items" :key="item.name">
 
   <div class="goods-accordion" v-if="item.category == goodsKey"> 
  
      <div class="goods-accordion__left" >
          <img class=" goods-accordion__left-img" :src="require(`../Goods/img/${item.icon.toLowerCase()}.png`)" :alt="goods"> 
          <div class=" goods-accordion__left-info">
            <div class=" goods-accordion__left-info-start">
               <div class="goods__caption">
                  {{item.name}}
                </div>
                <div class="union">
                    <img class="" src="./img/union.svg" alt="union">
                </div>
           
            </div>
           
            <div class="goods__quantity">
             <div class="goods__quantity--in" v-if="item.quantity > 0" >{{item.quantity}} / {{item.fromamount}}
               <div  v-for="it of Math.round(item.quantity*6/item.fromamount)" :key="it"> 
                   <img src="./img/dot.svg" alt="dots">
               </div>
               <div  v-for="it2 of Math.round(( item.fromamount)/item.quantity)" :key="it2"> 
                   <img src="./img/dot-empty.svg" alt="empty-dots">
               </div>
             </div>
              <div class="goods__quantity--out" v-else>{{item.quantity}}/ {{item.fromamount}}
               <div class="quantity-dots--out">
                  <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <circle opacity="0.35" cx="4" cy="4" r="4" fill="#FF4848"/>
                  </svg>
               </div>
               <div class="quantity-nomore">Нет на складе
               </div>
              </div>
            </div>
          </div> 
      </div>
      <div class="goods-accordion__right" >
        <div class="price__single">
          <div class="price__single-caption">
            Для потребителя:
          </div>
          <div class="price__single-text">
            {{item.oneprice}}
            <img src="./img/change.png" alt="change price">
          </div>
        </div>
      
        <div class="price__many">
          <div class="price__many-caption">
            Для потребителя:
          </div>
          <div class="price__many-text">
            {{item.manyprice}}
            <img src="./img/change.png" alt="change price">
          </div>
        </div>
      </div>
   </div>
 </div>
</template>
<script>

export default {
  name: " AccordionDescription",
  components:{
   
  },
  props:{
    goodsKey: String
  },
  data() {
    return {
      items: [
        {icon:"icon1", category: "Товары для дома", name:"Телевизор LED LG 65QNED966PA", quantity:"19", fromamount: "30", oneprice: "$2399", manyprice: "$2199"},
        {icon:"icon2", category: "Автомобили",  name:"Телевизор LED LG 65QNED966PA ",  quantity:"8", fromamount: "30", oneprice: "$2399", manyprice: "$2399"},
        {icon:"icon3",  category: "Аксессуары",  name:"Телевизор LED LG 65QNED966PA ", quantity:"0", fromamount: "30", oneprice: "$2399", manyprice: "$2399"},
      ]
    };
  },
  computed:{
    countDots(){
     
      return Math.round(parseInt(this.quantity)*6/parseInt(this.fromamount));
     
      
    }
  }

};
</script>
<style lang="scss" scoped>
.goods-accordion{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 0 20px;
 
;
}
.goods-accordion__left{
 display: flex;
  flex-direction: row;
  justify-content: start;
  margin: 10px 0;
}

.goods-accordion__left-img{
object-fit: contain;
// height: 86px;
// width: 113px;
border-radius: 10px;
}

.goods-accordion__left-info{
  display: flex;
  flex-direction: column;
  justify-content:baseline;
   margin-left: 10px;
   margin-top: 10px;
}
 .goods-accordion__left-info-start{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  position: relative;
  margin-bottom: 8px;
 }

.goods__caption{
 
// width: 284px;
// height: 15px;

    font-family: 'Gotham Pro';
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 15px;

    /* White */

    color: #FFFFFF;
   
}

.union{
  // position: absolute;
  // left: 48.34%;
  // right: 47.78%;
  // top: 66.13%;
  // bottom: 33.87%;
  // border: 1.23387px solid #000000;
   border: none;
   margin-top: -3px;
   margin-left: 10px;
}
.goods__quantity{
//  display: flex;
//  flex-direction: row;
//  justify-content: start;

  font-family: 'Gotham Pro';
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 19px;

  /* White */

  
}
.goods__quantity--in{
 display: flex;
 flex-direction: row;
 justify-content: space-between; 
 color: #FFFFFF;
}

.goods__quantity--out{
 display: flex;
 flex-direction: row;
 justify-content: space-between;
 color: #FF4848; 
}

.quantity-dots--out{
  // width: 8px;
  // height: 8px;
  // background-image: url(./img/dot.svg);
  // background-repeat: none;
  // color: #FF4848;
}

.quantity-nomore{
  width: 103px;
// height: 13px;

font-family: 'Gotham Pro';
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 17px;

/* White */

color: #FFFFFF;
background-color: #FF4848;
border-radius: 10px;
}

.goods-accordion__right{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 10px;
 
}
.price__single, .price__many{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  margin-left: 20px;
  position: relative;
  // border-right: 1px solid blue;
  
}



.price__single::after {
  content: '';
  position: absolute;
  top: 15%;
  bottom:15%;
  right: -15%;
 
  width: 1px;
  background:rgba(41, 47, 82, 1);
  // transform: rotate(90deg);

}

.price__single-caption, .price__many-caption{
  font-family: 'Gotham Pro';
font-style: normal;
font-weight: 400;
font-size: 13px;
line-height: 12px;

/* Gray */

color: #8285B4;

}

.price__single-text, .price__many-text{
  font-family: 'Gotham Pro';
font-style: normal;
font-weight: 400;
font-size: 20px;
line-height: 19px;

/* White */

color: #FFFFFF;

}

</style>
