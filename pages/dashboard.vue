<template>
  <v-container grid-list-md text-xs-center>
    <v-layout row wrap>
     <v-flex xs6>
        <todo-list></todo-list>
     </v-flex>
     <v-flex xs6>
      <v-card dark color="secondary">
        <v-toolbar color="pink">
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title class="white--text">My Tasks</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>search</v-icon>
          </v-btn>
        </v-toolbar>
        <v-card-text class="px-0">6</v-card-text>
      </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import TodoList from '~/components/todo/TodoList'

export default {
  components: {
    TodoList
  }
}
</script>