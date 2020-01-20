<template lang="pug">
  <div class="custom-select" @blur="open = false">
    <input type="text" v-model="search" class="select" :class="{open: open}" @click="open = !open" :placeholder="`${selected}`"/>
    <div class="items" :class="{selectHide: !open}">
      <div class="item" v-for="(option, index) in filteredList" :key="index" @click="selected=option; open=false; $emit('input', option)">{{ option }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Select',
  props: {
    options: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      search: '',
      selected: this.options.length > 0 ? this.options[0] : null,
      open: false
    }
  },
  computed: {
    filteredList () {
      return this.options.filter(el => {
        return el.match(this.search)
      })
    }
  },
  mounted () {
    this.$emit('input', this.selected)
  }
}
</script>
