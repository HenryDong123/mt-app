<template>
  <div class="m-menu">
    <dl class="nav" @mouseleave="mouseleave">
      <dt>全部分类</dt>
      <dd @mouseenter="enter" v-for="(item, idx) in menu" :key="idx">
        <i :class="item.type"></i>{{ item.name }}<span class="arrow"></span>
      </dd>
    </dl>
    <div class="detail" v-if="kind" @mouseenter="sover" @mouseleave="sout">
      <template v-for="(item, idx) in curdetail.child">
        <h4 :key="idx">{{ item.title }}</h4>
        <span v-for="v in item.child" :key="v">{{ v }}</span>
      </template>
    </div>
  </div>
</template>

<script>
    export default {
        name: "Emenu",
      data(){
          return {
            kind: '',
            menu:[{
              type: 'food',
              name: '美食',
              child: [{
                title: '美食',
                child:['代金券','甜点饮品','火锅','自助餐','小吃快餐']
              }]
            },{
              type: 'takeout',
              name: '外卖',
              child: [{
                title: '外卖',
                child:['美团外卖']
              }]
            },{
              type: 'hotel',
              name: '酒店',
              child:[{
                title: '酒店星级',
                child: ['积极型','舒适/三星','高档','豪华']
              }]
            }]
          }
      },
      computed:{
          curdetail(){
            return this.menu.filter((item) => item.type === this.kind)[0]
          }
      },
      methods:{
          mouseleave(){
            this._timer = setTimeout(() => {
              this.kind = ''
            },150)
          },
        enter(e){
            this.kind = e.target.querySelector('i').className
        },
        sover(){
            clearTimeout(this._timer)
        },
        sout(){
            this.kind = ''
        }
      }
    }
</script>

<style scoped>

</style>
