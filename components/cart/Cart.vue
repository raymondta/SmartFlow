<template>
    <v-card dark color="secondary">
          <v-toolbar color="pink">
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title class="white--text">My Cart <v-icon>cart</v-icon></v-toolbar-title>
            <v-spacer></v-spacer>
            
            <v-btn icon>
                <v-badge right>
                <span slot="badge">3</span>
              <v-icon>shopping_cart</v-icon>
            </v-badge>
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
          <v-btn
              absolute
              dark
              fab
              bottom
              right
              color="pink"
              @click="$router.push('/requests/submitted')"
            >
              <v-icon>check_circle</v-icon>
            </v-btn>
        </v-card>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          { avatar: 'https://cdn0.iconfinder.com/data/icons/logistic-5/32/11_box_package_parcel_logistic_delivery_unpack_open_shipping-512.png',
            title: 'New Employee Bundle',
            subtitle: "<span class='text--primary'>Ali Connors</span> &mdash; Engineering bundle" },
          { divider: true, inset: true },
          { avatar: 'https://cdn0.iconfinder.com/data/icons/logistic-5/32/11_box_package_parcel_logistic_delivery_unpack_open_shipping-512.png',
            title: 'Summer SOW Bundle',
            subtitle: "<span class='text--primary'>SOW bundle" },
          { divider: true, inset: true },
          { avatar: 'https://cdn0.iconfinder.com/data/icons/logistic-5/32/11_box_package_parcel_logistic_delivery_unpack_open_shipping-512.png',
            title: 'Existing exployee Bundle',
            subtitle: "<span class='text--primary'>Sandra Adams</span> &mdash; Access to a new SAP Transaction" }
        ]
      }
    }
  }
</script>