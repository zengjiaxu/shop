<template>
   <div class="page-index">
     <el-row>
       <el-col :span="5">
         <emenu/>
       </el-col>
       <el-col :span="19">1</el-col>
     </el-row>
     <el-row :span="24">
       1
     </el-row>
   </div>
</template>

<script type="text/ecmascript-6">
import Emenu from '../components/index/menu.vue'
export default {
  components:{
    Emenu
  }
}
</script>
<style lang="scss">
@import "@/assets/css/index/index.scss";
</style>


