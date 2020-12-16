<template>
  <div id="home">
      <navbar class="home-navbar"><div slot="center">购物街</div></navbar>
      <homeswiper :banners="banners"/>
      <recommend-view :recommends="recommends"/>
      <feature-view/>
      <tabcontrol class="tab-control" :titles="['流行','新款','精选']"/>

     <ul>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
        <li>列表</li>
      </ul>
  </div>
</template>

<script>
  import Homeswiper from './childcomps/Homeswiper'
  import RecommendView from './childcomps/RecommendView'
  import FeatureView from './childcomps/FeatureView'

  import Navbar from 'components/common/navbar/Navbar'
  import Tabcontrol from 'components/content/tabcontrol/Tabcontrol'

  import {getHomeMultidata, getHomeGoods} from "network/home";




  export default{
    name:'Home',
    components:{
      Homeswiper,
      RecommendView,
      FeatureView,
      Navbar,
      Tabcontrol
    },
    data() {
      return{
          banners: [],
          recommends: [],
          goods:{
            'pop': {page:0, list: []},
            'new': {page:0, list: []},
            'sell': {page:0, list: []},
          }
      }
    },
    //created发送网络请求
    created() {
        //1.请求多个数据
        this.getHomeMultidata()
        //2.请求商品数据
        this.getHomeGoods('pop')
        this.getHomeGoods('new')
        this.getHomeGoods('sell')
        },
    methods:{
      getHomeMultidata() {
        getHomeMultidata().then(res => {
          //this.result =res;
          this.banners = res.data.banner.list;
          this.recommends =res.data.recommend.list;
        })
      },
      getHomeGoods(type) {
        const page =this.goods[type].page +1
        getHomeGoods(type, page).then(res => {
             this.goods[type].list.push(...res.data.list)
             this.goods[type].page += 1
          })
      }
    }
  }
</script>

<style scoped>
  #home{
    padding-top: 43px;
  }
  .home-navbar{
    background-color: var(--color-tint);
    color: #fff;
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    z-index: 9;
  }

  .tab-control{
    position: sticky;
    top: 44px;
  }
</style>
