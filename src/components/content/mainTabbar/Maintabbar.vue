<template>
    <tabbar>
     <tabbarltem path="/home">
        <img slot="item-icon"  src="@/assets/img/tabbar/home.svg" alt=""/>
        <img  slot="item-icon-active" src="@/assets/img/tabbar/home_active.svg"/>
        <div slot="item-text">首页</div>
      </tabbarltem>
      <tabbarltem path="/category">
        <img  slot="item-icon" src="@/assets/img/tabbar/category.svg" alt=""/>
        <img  slot="item-icon-active" src="@/assets/img/tabbar/category_active.svg"/>
        <div slot="item-text">分类</div>
      </tabbarltem>
      <tabbarltem path="/cart">
        <img  slot="item-icon" src="@/assets/img/tabbar/shopcart.svg" alt=""/>
        <img  slot="item-icon-active" src="@/assets/img/tabbar/shopcart_active.svg"/>
        <div slot="item-text">购物车</div>
      </tabbarltem>
      <tabbarltem path="/profle">
        <img  slot="item-icon" src="@/assets/img/tabbar/profile.svg" alt=""/>
        <img  slot="item-icon-active" src="@/assets/img/tabbar/profile_active.svg"/>
        <div slot="item-text">我的</div>
      </tabbarltem>
    </tabbar>
</template>

<script>
  import Tabbar from '../../common/tabbar/Tabbar.vue'
  import Tabbarltem from '../../common/tabbar/Tabbarltem.vue'


  export default{
    name:'Maintabbar',
    components: {
      Tabbar,
      Tabbarltem
    }
  }
</script>

<style>
</style>
