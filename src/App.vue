<template>
  <the-navbar></the-navbar>
  <div class="container with-nav">
    <div class="card">
      <h1>Про Vuex</h1>
      <h2>Счетчик {{ counter}} ({{ doubleCounter }})</h2>
      <button class="btn primary" @click="add">Добавить</button>
      <button class="btn danger" @click="incrementAsync({value: 10,delay: 1000})">
        Добавить 10
      </button>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapMutations, mapActions } from 'vuex'
import TheNavbar from '@/components/TheNavbar.vue'
export default {
  components: {TheNavbar},
  computed: mapGetters(['counter', 'doubleCounter']),
  methods: {
    ...mapMutations({add: 'increment'}),
    ...mapActions(['incrementAsync']),
    // incrementAsync() {
    //   this.$store.dispatch('incrementAsync', {
    //     value: 10,
    //     delay: 1000
    //   })
    // }
  },
}
</script>