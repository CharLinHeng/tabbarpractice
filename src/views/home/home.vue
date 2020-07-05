<template>
    <div>
        这里是首页..
        <ul>
          <li v-for="(item,index) in data">{{item + ','+index}}</li>
        </ul>
    </div>
</template>
<script>
export default {
  name: '',
  data(){
    return {
      data:[1,2,3,4,5,6,7,8,9]
    }
  }
}
</script>
<style  scoped>

</style>
