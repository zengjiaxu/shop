<template>
   <div class="search-panel" style="height:200px">
     <el-row class="m-header-searchbar">
       <el-col
       :span="3"
       class="left">
         <img src="https://s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png" alt="">
       </el-col>
       <el-col
       :span="15"
       class="center">
       <div class="wrapper">
         <el-input
         placeholder="搜索商家或地点"
         @focus="focus" @blur="blur" v-model="search">
         </el-input>
         <button class="el-button el-button--primary"><i class="el-icon-search"></i></button>
         <dl class="hotPlace" v-show="isHotplace"><!-- 用户没输入并且聚焦的时候显示 -->
           <dt>热门搜索</dt>
           <dd v-for="(val,idx) of hotPlace" :key="idx">{{val}}</dd>
         </dl>
         <dl class="searchList" v-show="isSearchList"><!-- 用户输入的时候显示 -->
           <dd v-for="(val,idx) of searchList" :key="idx">{{val}}</dd>
         </dl>
         
       </div>
       <p class="suggset">
         <a href="javascript:;">故宫博物院</a>
         <a href="javascript:;">天安门</a>
         <a href="javascript:;">长城</a>
         <a href="javascript:;">故宫博物院</a>
       </p>
       <ul class="nav">
         <li>
           <nuxt-link 
           to="/" 
           class="takeout">美团外卖</nuxt-link>
         </li>
         <li>
          <nuxt-link 
           to="/" 
           class="movie">猫眼电影</nuxt-link>
         </li>
         <li>
          <nuxt-link 
          to="/" 
          class="movie">美团酒店</nuxt-link>
         </li>
         <li>
          <nuxt-link 
           to="/" 
           class="apartment">民宿/公寓</nuxt-link>           
         </li>
         <li>
          <nuxt-link 
           to="/" 
           class="business">商家入驻</nuxt-link>   
         </li>
       </ul>
       </el-col>
       <el-col 
       :span="6"
       class="right">
       <ul class="security">
         <li><i class="refund"/><p class="txt">随时退</p></li>
         <li><i class="single"/><p class="txt">不满意免单</p></li>
         <li><i class="overdue"/><p class="txt">过期退</p></li>
       </ul>
       </el-col>
     </el-row>
   </div>
</template>

<script type="text/ecmascript-6">
export default {
  data(){
    return {
      isFocus:false,
      search:'',
      hotPlace:['火锅','火锅','火锅','火锅','火锅'],
      searchList:['搜索','火锅','搜索','搜索','搜索']
    }
  },
  computed:{
    isHotplace(){
      return this.isFocus&&!this.search
    },
    isSearchList(){
      return this.isFocus&&this.search
    }
  },
  methods:{
    focus(){
      this.isFocus=true
    },
    blur(){
      setTimeout(()=>{this.isFocus=false},100)
    }

  }
}
</script>

<style lang="scss">
</style>
