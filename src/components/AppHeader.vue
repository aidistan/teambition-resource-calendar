<template lang="pug">
.app-header.row
  nav.navbar.navbar-default
    ul.nav.navbar-nav
      li(v-for="(displayName, name) in menuItems", :class="{ active: $route.name === name }")
        router-link(:to="{ name: name, query: $route.query }") {{ displayName }}
      li(:class="{ active: $route.name === 'config' }")
        router-link(:to="{ name: 'config', query: $route.query }")
          span.icon.icon-cog
      li(:class="{ active: $route.name === 'help' }")
        router-link(:to="{ name: 'help', query: $route.query }")
          span.icon.icon-circle-question
</template>

<script>
export default {
  data () {
    return {
      menuItems: {
        resources: '资源日历',
        members: '人员日历',
        conflicts: '冲突检测',
        statistics: '利用统计'
      }
    }
  }
}
</script>

<style lang="scss">
.app-header {
  .navbar {
    min-height: 40px;
  }

  ul.navbar-nav {
    margin: 0;
    float: none;
    text-align: center;

    & > li {
      float: none;
      display: inline-block;
    }
  }
}
</style>
