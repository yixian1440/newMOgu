<template > <!-- vue实例外创建 -->
     <swiper>
     <SwiperItem v-for="item in banners">
    <a :href="item.link">
    <img :src="item.image" alt=""></a>
     </SwiperItem>
     </swiper>
</template>
<!-- 调用   <mycom></mycom> -->
<script>
import {Swiper,SwiperItem} from 'components/common/swiper'
  export default {
      name:'HomeSwiper',
      props:{
          banners:{
              type:Array,
              default(){
                  return[]
              }
          }
      },
      components:{
          Swiper,
          SwiperItem
      },
  }
</script>
<style scoped>
    
</style>