<template>
  <div class="studentComponent col-3">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">{{student.name}}</h5>
        <h6 class="card-subtitle mb-2 text-muted">{{student.house}}</h6>
        <button @click="awardPoints">Achievement unlocked</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "studentComponent",
    props: ["student"],
    data() {
      return {}
    },
    computed: {},
    methods: {
      awardPoints() {
        this.$store.dispatch('awardPoints', this.student.house)
      }
    },
    components: {}
  }
</script>