// index.vue 路径：src/pages
<template>
  <div>
    <div class="pageTitle">猫眼电影</div>
    <ul class="topNav">
      <li :class="[showHot==1?'active':'']" @click="showHot=1">正在热映</li>
      <li :class="[showHot==0?'active':'']" @click="showHot=0">即将上映</li>
    </ul>
    <div class="main">
      <hoting v-show="showHot==1"></hoting>
      <comming v-show="showHot==0"></comming>
    </div>

  </div>
</template>

<script>
import hoting from '@/components/hoting'
import comming from '@/components/comming'

export default {
  name: "index",
  components: {
    hoting,comming
  },
  data() {
    return {
      showHot:1
    }
  }
};
</script>

<style scoped>
/** 其他样式代码已注释，demo有完整代码 **/
.active{
  color: rgb(229, 72, 71);
  border-bottom: 2px solid rgb(229, 72, 71);
}
</style>
