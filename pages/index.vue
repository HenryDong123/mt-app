<template>
  <div class="page-index">
    <el-row>
      <el-col :span="5">
        <emenu/>
      </el-col>
      <el-col :span="19">
        <life/>
      </el-col>
    </el-row>
    <el-row >
      <el-col :span="24">
        <artistic/>
      </el-col>
    </el-row>
  </div>
</template>
<script>
  import Emenu from '@/components/index/menu'
  import Life from '@/components/index/life.vue'
  import Artistic from '@/components/index/artistic.vue'
  export default {
    data(){
      return {
        title: '美团网-北京美食_酒店_旅游_团购_电影_吃喝玩乐'
      }
    },
    components: {
      Emenu,
      Life,
      Artistic
    },
    head () {
      return {
        title: this.title,
        meta: [
          { hid: 'description', name: 'description', content:
              '美团网精选北京美食餐厅,酒店预订,电影票,旅游景点,外卖订餐,北京团购信息,您可查询商家评价店铺信息。北京生活,下载美团官方APP ,吃喝玩乐1折起。' },
          {
            hid: 'keywords', name: 'keywords', content: '美食,酒店,团购'
          }
        ]
      }
    }
  };
</script>
<style lang="scss">
  @import "@/assets/css/index/index.scss";
</style>
