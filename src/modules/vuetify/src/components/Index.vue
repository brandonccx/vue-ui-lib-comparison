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
      <v-breadcrumbs icons divider="chevron_right">
        <v-breadcrumbs-item
          v-for="(item, i) in breadcrumb" :key="i"
          :disabled="i === breadcrumb.length - 1"
        >
          {{item}}
        </v-breadcrumbs-item>
      </v-breadcrumbs>
      <ct-table></ct-table>
    </main>
  </div>
</template>

<script>
import ctSidebar from './Sidebar'
import ctTable from './Table'
export default {
  name: 'HomePage',
  data () {
    return {
      show: true,
      breadcrumb: ['资源', '云主机']
    }
  },
  components: {ctSidebar, ctTable}
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
  height: 100%;
  z-index: 10;
  padding-left: 40px;
  flex-direction: column;
}
main.shown {
  padding-left: 100px;
}
main > .row {
  width: 100%;
}
main > nav {
  height: 40px;
  transition: all linear .3s;
}
main.shown > nav {
  height: 64px;
}
.breadcrumbs {
  justify-content: flex-start;
}
.ct-sidebar {
  position: absolute;
  left: 0;
  top: 0;
  transition: all linear .3s;
  z-index: 20;
}
</style>
