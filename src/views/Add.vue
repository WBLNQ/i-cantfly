<template>
    <div>
        <p>标题</p>
        <input type="text" v-model="title">
        <p>内容</p>
        <input type="text" v-model="cont">
        <div class="btn" @click="add()">添加</div>
    </div>
</template>
<script>
import store from '@/store'
export default {
  name: 'Add',
  store,
  data () {
    return {
      title: '',
      cont: ''
    }
  },
  methods: {
    add () {
      store.commit('addItem', {
        title: this.title,
        cont: this.cont
      })
      this.title = ''
      this.cont = ''
      this.$router.push('/home/list')
    }
  }
}
</script>
<style scoped>

</style>
