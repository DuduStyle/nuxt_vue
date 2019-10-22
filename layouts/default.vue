<template>
  <div>
    <my-header />
    <nuxt />
  </div>
</template>
<script>
import MyHeader from '~/components/public/header/index.vue'

export default {
  components: {
    MyHeader
  }
}
</script>
