<template>
  <div>
    <h1>Contador</h1>
    <h2>{{value}}</h2>
    <button @click="setValue(-1)">Dec</button>
    <button @click="setValue(1)">Inc</button>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    startValue: {
      type: Number
    }
  },
  data() {
    return {
      value: this.startValue || 0
    }
  },
  methods: {
    setValue(delta: number) {
      this.value += delta
    },
  },
})

</script>

<style>

</style>