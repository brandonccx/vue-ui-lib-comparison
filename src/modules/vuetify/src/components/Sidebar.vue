<template>
  <div class="ct-sidebar blue darken-3 white--text">
    <div class="ct-sidebar-title">
      <span>Clustack</span>
    </div>
    <v-btn v-for="item, i in items" :key="i"
      dark flat class="ct-sidebar-item">
      <v-icon medium>{{item.icon}}</v-icon>
      <span class="ct-sidebar-item-text">{{item.text}}</span>
    </v-btn>
  </div>
</template>

<script>
  export default {
    name: 'Sidebar',
    data () {
      return {
        items: [{
          icon: 'cloud',
          text: '资源'
        }, {
          icon: 'av_timer',
          text: '监控'
        }, {
          icon: 'trending_up',
          text: '报表'
        }]
      }
    }
  }
</script>

<style>
.ct-sidebar {
  width: 40px;
  height: 100%;
  overflow-x: hidden;
}
.ct-sidebar.shown {
  width: 100px;
}
.ct-sidebar.shown .ct-sidebar-item-text,
.ct-sidebar.shown .ct-sidebar-title > span {
  display: inline;
}
.ct-sidebar .ct-sidebar-item-text,
.ct-sidebar .ct-sidebar-title > span {
  display: none;
}
.ct-sidebar-title {
  height: 40px;
  line-height: 64px;
  font-weight: bold;
  font-size: 1.2rem;
  vertical-align: middle;
  background: #3588e0;
  transition: all linear .3s;
}
.ct-sidebar-item.btn {
  width: 100%;
  height: 40px;
  transition: all linear .2s;
  cursor: pointer;
  margin: 0;
  min-width: 0;
  padding: 0.5rem 0 0;
}

.ct-sidebar-item > .btn__content {
  flex-direction: column;
}

.ct-sidebar.shown .ct-sidebar-item {
  height: 64px;
}
.ct-sidebar.shown .ct-sidebar-title {
  height: 64px;
}
.ct-sidebar-item:hover {
  background: #0f5491;
}
.ct-sidebar-item .icon {
  font-size: 1.6rem;
  height: 2.6rem;
  display: block;
  margin: 0 auto;
}
.ct-sidebar.shown .icon {
  font-size: 2rem;
  display: block;
  margin: 0 auto;
}
</style>
