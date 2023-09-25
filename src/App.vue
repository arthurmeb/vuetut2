<template>

  <h1>{{ title }}</h1>
  <input type="text" ref="Username">
  <button @click="focus">Focus</button>
  <button @click="popupOpen">Open popup</button>
  <div v-if="popupActive">
    <Popup :message="message" :couler="couler" @closer="popupOpen" />
  </div>
</template>

<script>
import Popup from './components/Popup.vue'

export default {
  name: 'App',
  components: {Popup},
  data () {
    return {
      title: 'Vu:3 app UwU',
      message: "This is ground control to majoooor Tommm. Btw scheme =",
      couler: 'placeholder xD',
      popupActive: false
    }
  },
  methods: {
    focus() {
      this.$refs.Username.focus()
    },
    popupOpen() {
      this.popupActive = !this.popupActive
    }
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
