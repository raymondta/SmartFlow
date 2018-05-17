<template>
    <v-card dark color="secondary">
          <v-toolbar color="pink">
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title class="white--text">My approvals</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon>
              <v-icon>search</v-icon>
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
                <v-list-tile-content>
                  <v-list-tile-title v-html="item.title"></v-list-tile-title>
                  <v-list-tile-sub-title v-html="item.subtitle"></v-list-tile-sub-title>
                </v-list-tile-content>
              </v-list-tile>
            </template>
          </v-list>
        </v-card>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          { avatar: 'https://randomuser.me/api/portraits/women/71.jpg',
            title: 'New Employee',
            subtitle: "<span class='text--primary'>Ali Connors</span> &mdash; Needs an Engineering bundle" },
          { divider: true, inset: true },
          { avatar: 'https://randomuser.me/api/portraits/men/11.jpg',
            title: 'Summer SOW',
            subtitle: "<span class='text--primary'>Bob - Needs SOW bundle" },
          { divider: true, inset: true },
          { avatar: 'https://randomuser.me/api/portraits/women/61.jpg',
            title: 'Existing exployee',
            subtitle: "<span class='text--primary'>Sandra Adams</span> &mdash; Needs access to a new SAP Transaction" }
        ]
      }
    }
  }
</script>