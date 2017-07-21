<template>
  <v-app>
   <v-navigation-drawer temporary v-model="sideNav">
    <v-list>
      <v-list-tile v-for="menIt in menuItems" :key="menIt.title" router :to="menIt.link">
        <v-list-tile-action>
          <v-icon>{{menIt.icon}}</v-icon>
        </v-list-tile-action>
        <v-list-tile-content>{{menIt.title}}</v-list-tile-content>
      </v-list-tile>
    </v-list>
    </v-navigation-drawer>
    <v-toolbar dark class="primary">
      <v-toolbar-side-icon @click.native.stop="sideNav = !sideNav"
        class="hidden-sm-and-up"
      ></v-toolbar-side-icon>
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">DevMeetup</router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat 
        v-for="menIt in menuItems" 
        :key="menIt.title"
        router
        :to="menIt.link"
        >
          <v-icon left dark>{{menIt.icon}}</v-icon>
            {{menIt.title}}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <main>
     <router-view></router-view>
    </main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        sideNav: false,
        menuItems: [
          { icon: 'supervisor_account', title: 'View Meetups', link: '/meetups'},
          { icon: 'room', title: 'Organize meetup', link: '/meetup/new'},
          { icon: 'person', title: 'Profile', link: '/profile'},
          { icon: 'face', title: 'Sign Up', link: '/signup'},
          { icon: 'lock_open', title: 'Sign In', link: '/signin'},
        ]
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
