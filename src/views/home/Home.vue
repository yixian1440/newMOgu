<template>
    <div id="home">
   <nav-bar  class="hom-nav"><div slot="center">购物街</div></nav-bar>
    <HomeSwiper :banners="banners"/>
    <HomeRecommendView :recommends="recommends"/>
    </div>
</template>


<script>
import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from './childComps/HomeSwiper'
import {getHomeMultidata} from 'network/home'
import HomeRecommendView from './childComps/HomeRecommendView'

export default{
    name:'Home',
    components:{
        NavBar,
        HomeSwiper,HomeRecommendView
    },
    data() {
        return {
            banners:[],
            recommends:[]
        }
    },

    //创建生命周期函数，一旦创建完毕就发送网络请求
    created(){
        //1.请求多个数据
        getHomeMultidata().then(res=>{
            console.log(res);
            //request本质上返回了一个promise函数，异步操作，不可以在这里去打印验证是否保存了res
            this.banners = res.data.banner.list
            this.recommends = res.data.recommend.list
        })
    }
}    
</script>
<style scoped>
.hom-nav{
background-color:#ff8198;
color: #fff;
}
</style>