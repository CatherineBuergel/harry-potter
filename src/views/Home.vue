<template>
  <div class="home container">
    <div class="row">
      <div class="col">
        <h1>Witchcraft and Wizardry</h1>
      </div>
    </div>

    <houses></houses>

    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <div class="row">
      <students v-for="student in students" :student="student" :key="student._id"></students>
    </div>
  </div>
</template>

<script>
  // @ is an alias to /src
  import students from "@/components/StudentComponent.vue"
  import houses from "@/components/HousesComponent.vue"
  export default {
    name: 'home',
    mounted() {
      this.$store.dispatch('getStudents')
    },
    computed: {
      students() {
        return this.$store.state.students.filter(character => character.role == "student")
      }
    },
    components: {
      students,
      houses
    }
  }
</script>