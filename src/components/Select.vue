<template lang="pug">
  <div class="container">
    <input list="order" class="select" placeholder="Выберите продукт"/>
    <datalist id="order" v-model="chosen_item">
      <option disabled value=""></option>
      <option v-for="drink in drinks" :key="drink.id" :value="drink.name">{{ drink.name }}</option>
      <optgroup label="Еда">
        <option v-for="option in food" :key="option">{{ option }}</option>
      </optgroup>
      <optgroup label="Десерт">
        <option v-for="icecream in icecreams" :key="icecream">{{ icecream }}</option>
      </optgroup>
    </datalist>
  </div>
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
