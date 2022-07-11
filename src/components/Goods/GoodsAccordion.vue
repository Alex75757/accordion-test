<template>
  <div v-for="c of contents" :key="c.title">
    <div class="title" @click="c.expanded = !c.expanded">
      <div>
        <b>{{ c.title }}</b>
      </div>
      <div>
        <span v-if="c.expanded">
        <img src="./img/up.png" alt="up">
        </span>
        <span v-else>
           <img src="./img/down.png" alt="down">
          </span>
      </div>
    </div>
    <div class="description" v-if="c.expanded">
      <!-- {{ c.description }} -->
      <!-- {{c.title}} -->
       <AccordionDescription :goodsKey='c.title'/>
    </div>
  </div>
</template>
<script>
import  AccordionDescription from './AccordionDescription'
const contents = Array(5)
  .fill()
  .map((_, i) => {
    return {
      title: `title ${i}`,
      description: `description ${i}`,
      expanded: false,
    };

  });
  contents[0].title = "Товары для дома";
  contents[1].title = "Автомобили";
  contents[2].title = "Аксессуары";
 
export default {
  name: "GoodsAccordion",
  components:{
    AccordionDescription
  },
  data() {
    return {
      contents,
    };
  },
};
</script>
<style scoped>
.title {
  cursor: pointer;
  display: flex;
  justify-content: start;
  margin: 10px;
 
}
.title span{
   margin-left: 10px;
}

.description {
 margin: 10px;
  border-bottom: 1px solid rgba(25, 27, 65, 1);
}
</style>