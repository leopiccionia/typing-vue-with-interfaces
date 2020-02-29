<template>
  <div id="app">
    <Parent/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

import Parent from './components/Parent.vue'

@Component({
  name: 'App',
  components: {
    Parent
  }
})
export default class App extends Vue {}
</script>
