<template>
    <div class="content">
       
        <!-- <Statistic/> -->
        <Filters/>
        <GoodsAccordion/>
    </div>
</template>
<script>
import GoodsAccordion from './GoodsAccordion'
import Filters from './GoodsFilters'


export default {
  name: 'GoodsMain',
  components: {
   GoodsAccordion,
   Filters
 
  }
}
</script>
<style lang="scss" scoped>
.content{
  width: 100%;
  border: 1px solid white;
}
</style>