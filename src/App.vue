<template lang="pug">
#app
  Select(:desert='icecreams', :drinks='drinks', :food='food')
</template>

<script>
import Select from './components/Select'

export default {
  name: 'App',
  components: {
    Select
  },
  data () {
    return {
      chosen_item: '',
      drinks: [
        {
          name: 'кока-кола',
          id: 1
        },
        {
          name: 'апельсиновый сок',
          id: 2
        },
        {
          name: 'водичка',
          id: 3
        }
      ],
      food: {
        option1: 'чипсоны',
        option2: 'борщ',
        option3: 'доширак',
        option4: 'оливье',
        option5: 'холодец'
      },
      icecreams: ['ванильное мороженое', 'шоколадное мороженое', 'сливочное мороженое']
    }
  }
}
</script>

<style lang="stylus">
  @import "assets/styles/main.styl"
</style>
