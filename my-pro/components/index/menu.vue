<template>
   <div class="m-menu">
     <dl class="nav">
       <dt>全部分类</dt>
       <dd v-for="(item,index) of menu" :key="index" @mouseenter="mouseenter" @mouseleave="mouseleave">
         <i :class="item.type"/>{{item.name}}<span class="arrow"/>    
       </dd>
     </dl>
     <div class="detail" v-if="kind" @mouseenter="enter" @mouseleave="leave">
      <template  v-for="(item,idx) of currentDetail.child">
        <h4 :key="idx">{{item.title}}</h4>
        <span v-for="val of item.child" :key="val">{{val}}</span>        
      </template>
     </div>
   </div>
</template>

<script type="text/ecmascript-6">
export default {
  data(){
    return{
      kind:"",
      menu:[
        {
          type:"food",
          name:"美食",
          child:[
            {
              title:"美食",
              child:["火锅","冰淇淋","巧克力"]
            }
            ]
        },
        {
          type:"hotel",
          name:"酒店",
           child:[
            {
              title:"酒店/住宿",
              child:["榛果民宿","公寓","宾馆"]
            }
            ]
        }
      ]
    }
  },
  computed:{
    currentDetail(){
      return this.menu.filter(item => item.type===this.kind)[0]
    }
  },
  methods:{
    mouseenter(e){
      clearTimeout(this.timer)
      this.kind=e.target.querySelector('i').className;
      
    },
    mouseleave(){
      this.timer=setTimeout(()=>{
      this.kind=''
      },150)
    },
    enter(){
      clearTimeout(this.timer)
    },
    leave(){
      this.kind=''
    }
  }
}
</script>

<style lang="scss">
</style>
