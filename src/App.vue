<template lang="pug">
  <div id="app">
    <Select :options="icecreams"></Select>
  </div>
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
          name: 'Кока-кола',
          id: 1
        },
        {
          name: 'Апельсиновый сок',
          id: 2
        },
        {
          name: 'Водичка',
          id: 3
        }
      ],
      food: {
        option1: 'Чипсоны',
        option2: 'Борщ',
        option3: 'Доширак',
        option4: 'Оливье',
        option5: 'Холодец'
      },
      icecreams: ['ванильное мороженое', 'шоколадное мороженое', 'сливочное мороженое']
    }
  }
}
</script>

<style lang="stylus">
  @import "assets/styles/main.styl"
</style>
