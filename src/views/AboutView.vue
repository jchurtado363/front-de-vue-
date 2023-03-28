<template>
  <div class="about">
    <PosComponente/>
    <GetComponente/>
    

  </div>
</template>

<script>
import GetComponente from '@/components/GetComponente.vue'
import PosComponente from '@/components/PosComponente.vue'
export default {
  name: 'AboutView',
  components: {
    GetComponente,PosComponente
  }
}
</script>
<style scoped>

</style>
