<template>
      <v-card>
        <v-toolbar color="pink" dark>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title>My Requests</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
          
        </v-toolbar>
        <v-list three-line>
          <template v-for="(item, index) in items">
            <v-list-tile
              :key="item.title"
              avatar
              ripple
              @click="toggle(index)"
            >
              <v-list-tile-content>
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                <v-list-tile-sub-title class="text--primary">{{ item.headline }}</v-list-tile-sub-title>
                <v-list-tile-sub-title>
                    <v-stepper value="1">
                        <v-stepper-header>
                        <v-stepper-step step="1">Submitted</v-stepper-step>
                        <v-divider></v-divider>
                        <v-stepper-step step="2">Prepared</v-stepper-step>
                        <v-divider></v-divider>
                        <v-stepper-step step="3">Delivered</v-stepper-step>
                        </v-stepper-header>
                    </v-stepper>
                </v-list-tile-sub-title>
              </v-list-tile-content>
              <v-list-tile-action>
                <v-list-tile-action-text>{{ item.action }}</v-list-tile-action-text>
                <v-icon
                  @click="snackbarRemind = true"
                  v-if="selected.indexOf(index) < 0"
                  color="grey lighten-1"
                >notification_important</v-icon>
                <v-icon
                  v-else
                  color="yellow darken-2"
                >notification_important</v-icon>
              </v-list-tile-action>
              
            </v-list-tile>
            <v-divider v-if="index + 1 < items.length" :key="index"></v-divider>
          </template>
        </v-list>
        <v-snackbar
          v-model="snackbarRemind"
        ><v-icon>notification_important</v-icon> A reminder has been sent to the approvers!</v-snackbar >
      </v-card>
</template>

<script>
  export default {
    data () {
      return {
        snackbarRemind: false,
        selected: [2],
        items: [
          { action: '15 min', headline: 'Engineering Package', title: 'Ali Connors', subtitle: "I'll be in your neighborhood doing errands this weekend. Do you want to hang out?" },
          { action: '2 hr', headline: 'Finance Package', title: 'me, Scrott, Jennifer', subtitle: "Wish I could come, but I'm out of town this weekend." },
          { action: '6 hr', headline: '24 inch Screen', title: 'Sandra Adams', subtitle: 'Do you have Paris recommendations? Have you ever been?' },
          { action: '12 hr', headline: 'IT Package', title: 'Trevor Hansen', subtitle: 'Have any ideas about what we should get Heidi for her birthday?' },
          { action: '18hr', headline: 'HR Package', title: 'Britta Holt', subtitle: 'We should eat this: Grate, Squash, Corn, and tomatillo Tacos.' }
        ]
      }
    },

    methods: {
      toggle (index) {
        const i = this.selected.indexOf(index)

        if (i > -1) {
          this.selected.splice(i, 1)
        } else {
          this.selected.push(index)
        }
      }
    }
  }
</script>