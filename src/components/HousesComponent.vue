<template>
  <div class="housesComponent row">
    <div class="col-3" v-for="(value, key) in houses">
      <h1>{{key}}</h1>
      <h5>{{value}}</h5>
    </div>
  </div>
</template>

<script>
  export default {
    name: "housesComponent",
    props: [],
    data() {
      return {}
    },
    computed: {
      houses() {
        return this.$store.state.houses
      }
    },
    methods: {},
    components: {}
  }
</script>