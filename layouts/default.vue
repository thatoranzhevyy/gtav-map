<template>
  <div class="flex h-screen w-screen">
    <splitpanes class="no-splitter" :dbl-click-splitter="false" horizontal>
      <Pane class="flex flex-1 hide-scrollbar !overflow-auto">
        <main class="flex flex-1 w-full">
          <Nuxt class="flex overflow-y-auto flex-1"/>
        </main>
      </Pane>
<!--      <pane style="height: auto">-->
<!--        <AppFooter/>-->
<!--      </pane>-->
    </splitpanes>
  </div>
</template>
<script>
import {Splitpanes, Pane} from 'splitpanes'
import 'splitpanes/dist/splitpanes.css'

export default {
  components: {
    Splitpanes,
    Pane
  }
}
</script>
<style>
.no-splitter {
  /*@apply pointer-events-none;*/
}
</style>
