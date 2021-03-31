<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" fixed temporary app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to">
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-tabs>
        <v-tab
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          v-text="item.title"
        >
        </v-tab>
      </v-tabs>
      <v-switch v-model="$vuetify.theme.dark">
        <template v-slot:label>
          <v-icon>mdi-weather-night </v-icon>
        </template>
      </v-switch>
    </v-app-bar>
    <v-main>
      <v-toolbar
        v-if="$route.path != '/'"
        prominent
        light
        flat
        src="/background.jpg"
      >
        <v-toolbar-title align="center" justify="center">{{
          $route.path.replace('/', '').toUpperCase()
        }}</v-toolbar-title>
      </v-toolbar>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }} kaazzo</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'HOME',
          to: '/'
        },
        {
          icon: 'mdi-clipboard-account',
          title: 'ABOUT',
          to: '/about'
        },
        {
          icon: 'mdi-pencil',
          title: 'SKILLS',
          to: '/skills'
        },
        {
          icon: 'mdi-file-multiple',
          title: 'WORKS',
          to: '/works'
        }
      ],
      title: "kaazzo's portfolio"
    }
  }
  // watch: {
  //   darkMode: () => {
  //     this.$vuetify.theme.dark = darkMode
  //   }
  // }
}
</script>

<style lang="scss" scoped>
$xs: 600;
$sm: 960;
$md: 1264;
$lg: 1904;

$sp-max: calc($xs - 1) px;
$tb-min: $xs + px;
$tb-max: calc($sm - 1) px;
$pc-min: $sm + px;

/* PC */
@mixin display_pc {
  @media (min-width: $pc-min) {
    @content;
  }
}

/* タブレット */
@mixin display_tab {
  @media (min-width: $tb-min) and (max-width: $tb-max) {
    @content;
  }
}

/* スマホ */
@mixin display_sp {
  @media (max-width: $sp-max) {
    @content;
  }
}

.v-app-bar__nav-icon {
  @include display_pc {
    display: none !important;
  }
}

.v-tabs {
  display: none;

  @include display_pc {
    display: block !important;
  }
}

.v-toolbar__title {
  overflow: visible !important;
  margin-right: 50px !important;
}
</style>
