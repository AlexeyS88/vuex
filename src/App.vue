<template>
  <the-navbar></the-navbar>
  <div class="container with-nav">
    <div class="card">
      <h1>{{uppercaseTitle}}</h1>
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
  // computed: mapGetters(['count/counter', 'count/doubleCounter', 'uppercaseTitle']),
  computed: {
    ...mapGetters(['uppercaseTitle']),
    ...mapGetters('count',['counter', 'doubleCounter']),
  },
  methods: {
    ...mapMutations({add: 'count/increment'}),
    ...mapActions('count',['incrementAsync']),
    // incrementAsync() {
    //   this.$store.dispatch('incrementAsync', {
    //     value: 10,
    //     delay: 1000
    //   })
    // }
  },
}
</script>