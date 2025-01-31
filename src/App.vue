<template>
  <the-navbar></the-navbar>
  <div class="container with-nav">
    <div class="card">
      <h1>Про Vuex</h1>
      <h2>Счетчик {{ $store.state.counter}}</h2>
      <button class="btn primary" @click="increment">Добавить</button>
    </div>
  </div>
</template>

<script>
import TheNavbar from '@/components/TheNavbar.vue'
export default {
  components: {TheNavbar},
  // data() {
  //   return {
  //     counter: 0
  //   }
  // },
  methods: {
    increment() {
      this.$store.commit('increment')
    }
  }
}
</script>