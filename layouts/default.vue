<template>
  <v-app dark>
    <v-navigation-drawer
      :mini-variant.sync="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      fixed
      app
    >
      <v-list>
        <v-list-tile
          router
          :to="item.to"
          :key="i"
          v-for="(item, i) in items"
          exact
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed app :clipped-left="clipped">
      <v-toolbar-side-icon @click="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon @click="liveChatDialog = true"><v-icon>chat</v-icon></v-btn>
      <v-menu bottom left>
            <v-btn slot="activator" icon dark>
              <v-icon>more_vert</v-icon>
            </v-btn>
            <v-list>
              <v-list-tile  @click="logout">
                <v-list-tile-title>Logout</v-list-tile-title>
              </v-list-tile>
            </v-list>
          </v-menu>
      <v-avatar
              size="36px"
            >
              <img
                src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                alt=""
              >
            </v-avatar>
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
      fixed
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>

    <v-dialog v-model="liveChatDialog" max-width="500px">
        <v-card>
          <v-card-text>
            <live-chat></live-chat>
          </v-card-text>
          <v-card-actions>
            <v-btn @click.stop="liveChatDialog=false">Close</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    
  </v-app>
</template>

<script>
  import LiveChat from '~/components/chat/LiveChat'

  export default {
    components: {
      LiveChat
    },
    data () {
      return {
        liveChatDialog: false,
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'apps', title: 'Dashboard', to: '/dashboard' },
          { icon: 'add', title: 'New Request', to: '/requests/new' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'SmartFlow'
      }
    },
    methods: {
      logout: function () {
        this.$router.push('/')
      }
    }
  }
</script>
