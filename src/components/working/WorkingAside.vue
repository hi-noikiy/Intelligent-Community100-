<template>
  <Aside :active="activeIndex" :title="title" :lists="lists"></Aside>
</template>

<script>
  import Aside from '../Aside'
    export default {
        name: "ContainerAside",
      data(){
          return {
            activeIndex:'/working/plan/my',
            title:'工作平台',
            lists:[
              {
                index:'/working/advertise',
                name:'宣传管理',
                childs:[
                  {
                    index:'/working/advertise/essay',
                    name:'文章管理'
                  },
                  {
                    index:'/working/essay/column',
                    name:'文章栏目管理'
                  },
                  {
                    index:'/working/essay/carousel',
                    name:'轮播图管理'
                  },
                ]
              },
              {
                index:'/working/logmanage',
                name:'日志管理',
                childs:[
                  {
                    index:'/working/logmanage/log',
                    name:'工作日志'
                  },
                  {
                    index:'/working/logmanage/audit',
                    name:'日志审核'
                  }
                ]
              },
              {
                index:'/working/plan',
                name:'工作计划',
                childs:[
                  {
                    index:'/working/plan/my',
                    name:'我的工作计划'
                  },
                  {
                    index:'/working/plan/undo',
                    name:'我安排的工作'
                  },
                  {
                    index:'/working/plan/dept',
                    name:'部门工作计划'
                  },
                ]
              },
              {
                index:'/working/notice',
                name:'公告管理',
              },
            ]
          }
      },
      components:{
          Aside
      },
      mounted(){
        //解决页面刷新的时候路由不高亮显示的问题
        this.activeIndex=this.$route.matched[1].path;
      }
    }
</script>
<style scoped>
</style>
