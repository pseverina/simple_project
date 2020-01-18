<template lang="pug">
  .container
    input.select(list='order', onmouseover='focus(); old = value', onmousedown="value = ''", onmouseup='value = old', placeholder='Выберите продукт')
    datalist#order(v-model='chosen_item')
      option(v-for='drink in drinks', :key='drink.id', :value='drink.name') {{ drink.name }}
      optgroup(label='Еда')
        option(v-for='option in food', :key='option') {{ option }}
      optgroup(label='Десерт')
        option(v-for='icecream in icecreams', :key='icecream') {{ icecream }}
      option(value=' ', readonly='') Вино
</template>

<script>
export default {
  name: 'Select',
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
      icecreams: ['Ванильное мороженое', 'Шоколадное мороженое', 'Сливочное мороженое']
    }
  }
}
</script>
