<template>
  <div>
    <div>个人中心</div>
    <div @click="addnr()">添加</div>
  </div>
</template>
<script>
export default {
  name: 'User',
  methods: {
    addnr () {
      this.$router.push('/add')
    }
  }
}
</script>
<style scoped>

</style>
