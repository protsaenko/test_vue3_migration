<template>
  <div id="app">
    <Heading msg="Compat App" />
    <ul>
      <li v-for="item in items" v-bind:key="item">{{ item }}</li>
    </ul>
      <v-btn v-on:click="pop">Pop</v-btn>
  </div>
</template>

<script>
import Heading from './components/Heading.vue'

export default {
  name: 'App',
  components: {
    Heading
  },
  data() {
    return {
      items: [1,2,3,4,5]
    }
  },
  watch: {
    items: {
      handler(val, oldVal) {
        console.log(oldVal + ' --> ' + val)
      }
    }
  },
  methods: {
    pop() {
      this.items.pop()
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Arial, Helvetica, sans-serif;
  padding: 1em;
  max-width: 240px;
  margin: 0 auto;
  background-color:#eee;
  text-align: center;
}

ul {
  padding-left: 0;
  list-style: none;
}

button {
  background-color: red;
  padding: 5px 15px;
  border: none;
  color:white;
  font-size: 16pt;
}
</style>