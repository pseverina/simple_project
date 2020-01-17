<template lang="pug">
  #app
    Select
</template>

<script>
import Select from './components/Select'

export default {
  name: 'App',
  components: {
    Select
  }
}
</script>

<style lang="stylus">
#app
  background-color black
  color white
  padding 30px
  text-align center

select
  width 130px

</style>
