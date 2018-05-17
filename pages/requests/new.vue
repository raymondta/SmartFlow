<template>
  <v-container grid-list-md text-xs-center>
    <v-layout row wrap>
     <v-flex xs8>
        <bundle></bundle>
        <br>
        <custom></custom>
     </v-flex>
     <v-flex xs4>
      <todo-list></todo-list>
      <br><br>
      <cart></cart>
      </v-flex>
    </v-layout>
    
  </v-container>
</template>

<script>
import Bundle from '~/components/cart/Bundle'
import Custom from '~/components/cart/Custom'
import Cart from '~/components/cart/Cart'
import TodoList from '~/components/todo/TodoList'

export default {
  components: {
    Bundle,
    Custom,
    Cart,
    TodoList
  }
}
</script>