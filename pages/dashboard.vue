<template>
  <v-container grid-list-md text-xs-center>
    <v-layout row wrap>
     <v-flex xs6>
        <todo-list></todo-list>
        <br><br>
        <my-approvals></my-approvals>
     </v-flex>
     <v-flex xs6>
      <my-requests></my-requests>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import TodoList from '~/components/todo/TodoList'
import MyApprovals from '~/components/todo/MyApprovals'
import MyRequests from '~/components/requests/MyRequests'

export default {
  components: {
    TodoList,
    MyRequests,
    MyApprovals
  }
}
</script>