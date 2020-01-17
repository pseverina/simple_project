<template lang="pug">
  <div>
    <h1>Меню</h1>
    <div>Выберите напиток</div>
    <select v-model="default_drink">
      <option disabled value="">Напиток</option>
      <option v-for="drink in drinks" :key="drink.id" :value="drink">{{ drink.name }}</option>
    </select>
    <div>Может, вы хотите покушать?</div>
    <select v-model="default_food">
      <option disabled value="">Еда</option>
      <option v-for="option in food" :key="option">{{ option }}</option>
    </select>
    <div>Как насчет мороженки?</div>
    <select v-model="default_icecream">
      <option disabled value="">Десертик</option>
      <option v-for="icecream in icecream" :key="icecream">{{ icecream }}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'Select',
  data () {
    return {
      checked: false,
      title: 'Какой ваш любимый напиток?',
      default_drink: '',
      default_food: '',
      default_icecream: '',
      drinks: [
        { name: 'Кока-кола', id: 1 },
        { name: 'Апельсиновый сок', id: 2 },
        { name: 'Водичка', id: 3 }
      ],
      food: {
        option1: 'Чипсоны',
        option2: 'Борщ',
        option3: 'Доширак',
        option4: 'Оливье',
        option5: 'Холодец'
      },
      icecream: ['Ванильное', 'Шоколадное', 'Сливочное']
    }
  }
}
</script>
