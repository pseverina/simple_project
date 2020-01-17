<template lang="pug">
  <div>
    <h1 class="title">Добрый день! Готовы сделать ваш заказ?</h1>
    <div class="container">
      <div class="column_left">
        <h2>Меню</h2>
        <div>Выберите напиток</div>
        <select v-model="chosen_drink">
          <option disabled value="">Напиток</option>
          <option v-for="drink in drinks" :key="drink.id" :value="drink">{{ drink.name }}</option>
        </select>
        <div>Может, вы хотите покушать?</div>
        <select v-model="chosen_food">
          <option disabled value="">Еда</option>
          <option v-for="option in food" :key="option">{{ option }}</option>
        </select>
        <div>Как насчет мороженки?</div>
        <select v-model="chosen_icecream">
          <option disabled value="">Десертик</option>
          <option v-for="icecream in icecream" :key="icecream">{{ icecream }}</option>
        </select>
      </div>
      <div class="column_right">
        <h2>Ваш заказ</h2>
        <p>{{ chosen_drink.name }}</p>
        <p>{{ chosen_food }}</p>
        <p>{{ chosen_icecream }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Select',
  data () {
    return {
      checked: false,
      title: 'Какой ваш любимый напиток?',
      chosen_drink: '',
      chosen_food: '',
      chosen_icecream: '',
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
      icecream: ['Ванильное мороженое', 'Шоколадное мороженое', 'Сливочное мороженое']
    }
  }
}
</script>
