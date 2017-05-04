<template>
  <div class="index">
    <ct-sidebar :class="show ? 'shown' : ''"/>
    <main :class="show ? 'shown' : ''">
      <v-toolbar class="grey darken-2">
        <v-toolbar-side-icon @click.native.stop="show = !show"/>
        <v-toolbar-title class="text-xs-left">Clustack</v-toolbar-title>
        <v-spacer/>
        <v-btn icon>
          <v-icon>account_circle</v-icon>
        </v-btn>
        <span class="white--text">admin</span>
        <v-btn icon>
          <v-icon>more_vert</v-icon>
        </v-btn>
      </v-toolbar>
    </main>
  </div>
</template>

<script>
import ctSidebar from './Sidebar'
export default {
  name: 'HomePage',
  data () {
    return {
      show: true
    }
  },
  components: {ctSidebar}
}
</script>

<style scoped sass>
.index {
  position: relative;
  height: 100%;
}
main {
  transition: all linear .3s;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  padding-left: 40px;
}
main.shown {
  padding-left: 100px;
}
.ct-sidebar {
  position: absolute;
  left: 0;
  top: 0;
  transition: all linear .3s;
  z-index: 20;
}
</style>
