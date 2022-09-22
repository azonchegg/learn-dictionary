<template>
  <v-app dark>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
    >
      <v-btn
        v-for="item in menuItems"
        :to="item.code"
      >
        <v-toolbar-title v-text="item.title" />
      </v-btn>

      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      menuItems: [
        {
          title: 'Learn words',
          code: '/'
        },
        {
          title: 'Your dictionary',
          code: 'dictionary'
        }
      ]
    }
  },
  methods: {
    go(code) {
      console.log(code)

      if (code === '') this.$router.replace('')
      this.$router.push(code)
    }
  },
}
</script>
