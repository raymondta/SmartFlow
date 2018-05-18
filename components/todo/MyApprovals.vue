<template>
    <v-card dark color="secondary">
          <v-toolbar color="pink">
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title class="white--text">My approvals</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon>
              <v-icon>search</v-icon>
            </v-btn>
            <v-btn icon @click="approveAll()">
            <v-icon>check_circle</v-icon>
            </v-btn>
          </v-toolbar>
          <v-list two-line>
            <template v-for="(item, index) in items">
              <v-subheader v-if="item.header" :key="item.header">{{ item.header }}</v-subheader>
              <v-divider v-else-if="item.divider" :inset="item.inset" :key="index"></v-divider>
              <v-list-tile v-else :key="item.title" avatar @click="">
                <v-list-tile-avatar>
                  <img :src="item.avatar">
                </v-list-tile-avatar>
                <v-list-tile-content >
                  <v-list-tile-title v-html="item.title"></v-list-tile-title>
                  <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
                </v-list-tile-content>
                <v-list-tile-action >
                <v-list-tile-action-text>{{ item.action }}</v-list-tile-action-text>
                <v-btn icon @click="approve(item)">

                <v-icon 
                >check_circle</v-icon>
                </v-btn>
              </v-list-tile-action>
              </v-list-tile>
            </template>
          </v-list>

          <v-snackbar
          v-model="snackbarApproved"
        ><v-icon>check_cicle</v-icon>{{snackbarText}}</v-snackbar>
        </v-card>
</template>

<style>
.list-leave-active {
  transition: all 0.5s;
  opacity: 0;
}
</style>

<script>
  export default {
    data () {
      return {
        snackbarApproved: false,
        snackbarText: '',
        items: [
          { action: '2days',
            avatar: 'https://randomuser.me/api/portraits/women/71.jpg',
            title: 'New Employee',
            subtitle: "<span class='text--primary'>Ali Connors</span> &mdash; Needs an Engineering bundle" },
          { action: '4 hours',
            avatar: 'https://randomuser.me/api/portraits/men/11.jpg',
            title: 'Summer SOW',
            subtitle: "<span class='text--primary'>Bob - Needs SOW bundle" },
          { action: '15 minutes',
            avatar: 'https://randomuser.me/api/portraits/women/61.jpg',
            title: 'Existing exployee',
            subtitle: "<span class='text--primary'>Sandra Adams</span> &mdash; Needs access to a new SAP Transaction" }
        ]
      }
    },
    methods: {
      approve: function (item) {
        console.log(item.title)
        this.items = this.items.filter(e => e.title !== item.title)
        this.snackbarText = 'The request has been approved!'
        this.snackbarApproved = true
      },
      approveAll: function () {
        this.snackbarText = 'All requests have been approved!'
        this.items = []
      }
    }
  }
</script>