<template>
  <body>
    <div class="buttons">
      <button class="btn btn-danger" @click="allAbsent()">Tout est absent</button>
      <span class="flex-spacer"></span>
      <button class="btn btn-success" @click="allPresent()">Tout est présent</button>
    </div>
    <b-list-group class="list-group" v-for="user in users" :key="user.userId">
      <b-list-group-item class="d-flex align-items-center">
        <b-avatar variant="info" :src="user.picture" class="mr-3" size="6rem"></b-avatar>
        <div class="username-mode">
          <h4>{{user.name}}</h4>
          <h4 v-bind:class="getCssClass(user)">{{getModeValue(user)}}</h4>
        </div>
        <button @click="toggle(user)" class="btn btn-success">Switcher</button>
      </b-list-group-item>
    </b-list-group>
  </body>  
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    users: Array,
    modes: Array
  },
  methods: {
    toggle(user) {
      user.modeId = 2 - (user.modeId + 1)%this.modes.length;
    },
    getCssClass(user) {
      console.log("getcssclass")
      for(let mode of this.modes) {
        console.log(user.modeId)
        console.log(mode.modeId)
        console.log(mode.modeId===mode.modeId)
        if (user.modeId === mode.modeId) {
          console.log(mode.cssClass)
          return mode.cssClass;
        }
      }
    },
    getModeValue(user) {
      console.log("getmodevalue")
      for(let mode of this.modes) {
        console.log(user.modeId)
        console.log(mode.modeId)
        console.log(mode.modeId===mode.modeId)
        if (user.modeId === mode.modeId) {
          console.log(mode.value)
          return mode.value;
        }
      }
    },
    allPresent() {
      for(let user of this.users) {
        user.modeId = 1;
      }
    },
    allAbsent() {
      for(let user of this.users) {
        user.modeId = 2;
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.buttons {
  display: flex;
  margin: 20px
}
.list-group {
  width: 100%;
}
.card {
  width: 100%;
  height: 15%;
}
.username-mode {
  margin-right: auto;
  margin-left: 2%;
  text-align: start;
}
.present {
  color: green;
}
.absent {
  color: red;
}
img {
  width: 15%;
  height: 15%;
  border-radius: 50%;
}
.btn {
  margin: 1px;
}
.flex-spacer {
  flex: 1 1 auto;
}
</style>
