<template>
<v-card>
        <v-toolbar color="teal" dark>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title class="text-xs-center">Live Help</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>
        <v-card-title>
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/men/31.jpg">
            </v-list-tile-avatar>
            Hello How Can I help?
        </v-card-title>
        
        <v-card-text light> 
            <v-text-field
                name="input-7-1"
                label="Chat here"
                multi-line
                ></v-text-field>
        </v-card-text>
 
        <v-list subheader>
          <v-subheader>Recent chat</v-subheader>
          <v-list-tile v-for="item in items" :key="item.title" avatar @click="">
            <v-list-tile-avatar>
              <img :src="item.avatar">
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title v-html="item.title"></v-list-tile-title>
            </v-list-tile-content>
            <v-list-tile-action>
              <v-icon :color="item.active ? 'teal' : 'grey'">chat_bubble</v-icon>
            </v-list-tile-action>
          </v-list-tile>
        </v-list>
        <v-divider></v-divider>
        <v-list subheader>
          <v-subheader>Previous chats</v-subheader>
          <v-list-tile v-for="item in items2" :key="item.title" avatar @click="">
            <v-list-tile-avatar>
              <img :src="item.avatar">
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title v-html="item.title"></v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-card>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          { active: true, title: 'Jason Oner', avatar: 'https://randomuser.me/api/portraits/men/31.jpg' },
          { active: true, title: 'Ranee Carlson', avatar: 'https://randomuser.me/api/portraits/women/71.jpg' },
          { title: 'Cindy Baker', avatar: 'https://randomuser.me/api/portraits/women/51.jpg' },
          { title: 'Ali Connors', avatar: 'https://randomuser.me/api/portraits/women/81.jpg' }
        ],
        items2: [
          { title: 'Travis Howard', avatar: 'https://randomuser.me/api/portraits/men/91.jpg' }
        ]
      }
    }
  }
</script>