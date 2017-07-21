<template>
  <v-app>
   <v-navigation-drawer v-model="sideNav">
    <v-list>
      <v-list-tile v-for="menIt in menuItems" :key="menIt.title">
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
      <v-toolbar-title>DevMeetup</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn flat v-for="menIt in menuItems" :key="menIt.title">
          <v-icon left dark>{{menIt.icon}}</v-icon>
            {{menIt.title}}
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
    <main>
     
    </main>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        sideNav: false,
        menuItems: [
          { icon: 'supervisor_account', title: 'View Meetups' },
          { icon: 'room', title: 'Organize meetup' },
          { icon: 'person', title: 'Profile' },
          { icon: 'face', title: 'Sign Up' },
          { icon: 'lock_open', title: 'Sign In' }
        ]
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
