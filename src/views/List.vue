<template>
  <div>
    <ul>
      <li v-for="(item,index) in xlist" :key="index">
        {{item.title}}---{{item.cont}}
      </li>
    </ul>
  </div>
</template>
<script>
import store from '@/store'
export default {
  name: 'List',
  store,
  computed: {
    xlist () {
      return (store.state.lists)
    }
  },
  data () {
    return {
      lllist: []
    }
  }
}
</script>

<style scoped>

</style>
