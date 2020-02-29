<template>
  <div class="child">
    <input ref="input">
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

import { Focusable, Printable } from '../interfaces'

@Component({
  name: 'Child'
})
export default class ChildComponent extends Vue implements Focusable, Printable {
  $refs!: {
    input: HTMLInputElement;
  }

  blur () {
    // Parent doesn't know about this method
    this.$refs.input.blur()
  }

  focus () {
    this.$refs.input.focus()
  }

  print (text: string) {
    console.group('Text passed by parent')
    console.log(text)
    console.groupEnd()
  }
}
</script>
