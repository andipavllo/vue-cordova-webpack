<template>
  <v-ons-page>
    <v-ons-toolbar class="home-toolbar">
      <div class="left">
        <v-ons-toolbar-button @click="$emit('toggleMenu')">
          <v-ons-icon icon="ion-navicon, material:md-menu"></v-ons-icon>
        </v-ons-toolbar-button>
      </div>
      <div class="center">\{{ msg }}</div>
    </v-ons-toolbar>

    <div class="header">
      <img src="../assets/logo.png">
    </div>

    <v-ons-list-title>Vue.js Essential Links</v-ons-list-title>
    <v-ons-list>
      <v-ons-list-item v-for="item in essentialLinks" @click="goTo(item.link)" :key="item.link">
        <div class="left"><v-ons-icon fixed-width :icon="item.icon"></v-ons-icon></div>
        <div class="center">\{{ item.label }}</div>
        <div class="right"><v-ons-icon icon="fa-external-link"></v-ons-icon></div>
      </v-ons-list-item>
    </v-ons-list>

    <v-ons-list-title>Vue.js Ecosystem</v-ons-list-title>
    <v-ons-row>
      <v-ons-col>
        <v-ons-card @click="goTo('http://router.vuejs.org/')">vue-router</v-ons-card>
      </v-ons-col>
      <v-ons-col>
        <v-ons-card @click="goTo('http://vuex.vuejs.org/')">vuex</v-ons-card>
      </v-ons-col>
    </v-ons-row>
    <v-ons-row>
      <v-ons-col>
        <v-ons-card @click="goTo('http://vue-loader.vuejs.org/')">vue-loader</v-ons-card>
      </v-ons-col>
      <v-ons-col>
        <v-ons-card @click="goTo('https://github.com/vuejs/awesome-vue')">awesome-vue</v-ons-card>
      </v-ons-col>
    </v-ons-row>

  </v-ons-page>
</template>

<script>
export default {
  name: 'home',
  data{{#unless_eq lintConfig "airbnb"}} {{/unless_eq}}() {
    return {
      msg: 'Welcome',
      essentialLinks: [
        {
          label: 'Core Docs',
          link: 'https://vuejs.org',
          icon: 'fa-book'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Gitter Chat',
          link: 'https://gitter.im/vuejs/vue',
          icon: 'fa-commenting'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Forum',
          link: 'https://forum.vuejs.org',
          icon: 'ion-chatboxes'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Twitter',
          link: 'https://twitter.com/vuejs',
          icon: 'fa-twitter'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        },
        {
          label: 'Docs for this template',
          link: 'http://vuejs-templates.github.io/webpack/',
          icon: 'fa-file-text'{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
        }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
      ]{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
    }{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
  },
  methods: {
    goTo{{#unless_eq lintConfig "airbnb"}} {{/unless_eq}}(url) {
      window.open(url, '_blank'){{#if_eq lintConfig "airbnb"}};{{/if_eq}}
    }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
  }{{#if_eq lintConfig "airbnb"}},{{/if_eq}}
}{{#if_eq lintConfig "airbnb"}};{{/if_eq}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  text-align: center;
}

img {
  max-width: 300px;
}

ons-list-title:not(:first-of-type) {
  margin-top: 30px;
}

ons-card {
  text-align: center;
}

ons-list-item, ons-card {
  cursor: pointer;
}
</style>
