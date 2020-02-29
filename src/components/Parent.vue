<template>
  <div class="parent">
    <Child ref="child"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

import Child from './Child.vue'
import { Focusable, Printable } from '../interfaces'

@Component({
  name: 'Parent',
  components: {
    Child
  }
})
export default class ParentComponent extends Vue {
  $refs!: {
    child: Vue & Focusable & Printable;
  }

  mounted () {
    this.$refs.child.focus()
    this.$refs.child.print('Hello from parent')
  }
}
</script>
