<template>
  <div class="ct-sidebar blue darken-3 white--text">
    <div class="ct-sidebar-title">
      <span>Clustack</span>
    </div>
    <div v-for="item, i in items" :key="i" ripple class="ct-sidebar-item">
      <v-icon medium>{{item.icon}}</v-icon>
      <span class="ct-sidebar-item-text">{{item.text}}</span>
    </div>
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

<style scope>
.ct-sidebar {
  width: 40px;
  height: 100%;
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
  height: 64px;
  line-height: 64px;
  font-weight: bold;
  font-size: 1.2rem;
  vertical-align: middle;
  background: #3588e0;
}
.ct-sidebar-item {
  padding-top: 0.5rem;
  width: 100%;
  height: 40px;
  border-bottom: 1px solid #3284db;
  transition: all linear .2s;
  cursor: pointer;
}
.ct-sidebar.shown .ct-sidebar-item {
  padding-top: 1rem;
  height: 80px;
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
