<template lang="pug">
.custom-select(:tabindex='tabindex', @blur='open = false')
  input.select(type='text', v-model='search', :class='{open: open}', @click='open = !open; itemSelected()', :placeholder='`${selected}`')
  .items(:class='{selectHide: !open}')
    .item(v-for='(option, index) in filteredList', :key='index', @click="selected = option; open = false; $emit('input', option)") {{ option }}
</template>

<script>
export default {
  name: 'Select',
  props: {
    tabindex: {
      type: Number,
      required: false,
      default: 0
    },
    desert: {
      type: Array,
      required: true
    },
    drinks: {
      type: Array,
      required: true
    },
    food: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      search: '',
      selected: 'Выберите продукт',
      open: false
    }
  },
  computed: {
    mixedArray () {
      return [...this.desert,
        ...this.drinks.flatMap(el => el.name),
        ...Object.values(this.food)]
    },
    filteredList () {
      return this.mixedArray.filter(el => {
        return el.match(this.search)
      })
    }
  },
  mounted () {
    this.$emit('input', this.selected)
  },
  methods: {
    async itemSelected () {
      this.search = this.selected
      this.selected = ''
    }
  }
}
</script>
