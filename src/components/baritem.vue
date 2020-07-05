<template >
      <div class="tab-bar-item">
            <div v-if="!active" @click="goview">
                <slot name="icon" ></slot>
            </div>
             <div v-else>
                 <slot name="icon-active"></slot>
             </div>
             <div :style="judge()">
                 <slot name="text"></slot>
             </div>
        </div>
</template>
<script>
export default {
  name: 'vueitem',
  props:{
      path:String,
      color:{
          type: String,
          default: 'red'
      }
  },
  data(){
      return {
        //   active:false
      }
  }
  ,methods: {
        goview(){
        //   console.log("你在电价...")
        this.$router.replace(this.path)
        },
        judge(){
          return this.active?{color:this.color}:{}
      }
  }
  ,computed: {
      active(){
            return this.$route.path.indexOf(this.path)!= -1;
      }
      
  }
}
</script>
<style  scoped>
   .tab-bar-item{
        margin: 0 auto;
        height: 49px;
    }
    .tab-bar-item img{
        width: 30px;
        height: 30px;
    }
    .tab-bar-item span{
        margin: 0 auto;
        justify-content: center;
        display: flex;
    }
    .textcolor{
        color: red;
    }
</style>
