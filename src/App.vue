<template>
  <div id="app">
    <UsersList :users="users" :modes="modes"/>
  </div>
</template>

<script>
import UsersList from './components/UsersList.vue'

export default {
  name: 'App',
  components: {
    UsersList
  },
  data () {
    return (
      {
        users: [
          {name: "AIT-SSI Mouslim", picture: "https://upload.wikimedia.org/wikipedia/commons/a/a0/Pierre-Person.jpg", userId: 1, modeId: 1},
          {name: "AIT-SSI Salman", picture: "https://upload.wikimedia.org/wikipedia/commons/a/a0/Pierre-Person.jpg", userId: 2, modeId: 1},
          {name: "AIT-SSI Amine", picture: "https://upload.wikimedia.org/wikipedia/commons/a/a0/Pierre-Person.jpg", userId: 3, modeId: 1}
        ],
        modes: [
          {modeId: 1, value: "Présent", cssClass: "present"},
          {modeId: 2, value: "Absent", cssClass: "absent"},
        ]
      }
    )
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
