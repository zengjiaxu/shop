<template>
   <div class="m-header">
     <el-row>
       <el-col>
         <topbar/>
       </el-col>
     </el-row>
     <el-row>
       <el-col>
         <searchbar/>
       </el-col>
     </el-row>     
   </div>
</template>

<script type="text/ecmascript-6">
import topbar from './topbar.vue'
import searchbar from './searchbar.vue'
export default {
  components:{
    topbar,
    searchbar
  }
}
</script>

<style lang="scss">
@import '@/assets/css/public/header/index.scss';
</style>
