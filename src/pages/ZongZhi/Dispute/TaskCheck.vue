<template>
  <el-container>
    <el-main>
      <FoundReportMain></FoundReportMain>
    </el-main>
  </el-container>

</template>

<script>
  import FoundReportMain from '../../../components/zongzhi/Dispute/TaskCheckMain'

  export default {
    props: {
      rightTitle: String
    },
    components: {
      FoundReportMain
    },
    data() {
      return {

      }
    },
    methods: {

    }
  }
</script>
<style>

</style>
<style scoped>

</style>
