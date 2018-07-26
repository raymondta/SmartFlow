<template>
<div>

  <v-jumbotron>
    <v-container fill-height>
      <v-layout align-center>
        <v-flex>
          <h3 class="display-3">
              <v-avatar color="indigo">
                <v-icon dark>check_circle</v-icon>
                </v-avatar>
              Your request has been submitted!</h3>
          <span class="subheading">It should be delivered by [Date].</span>
          <v-divider class="my-3"></v-divider>
          <div v-if="feedbackSubmitted" class="title mb-3">Thanks for your feedback! <v-icon>thumb_up</v-icon></div>

          <div v-if="!feedbackSubmitted" class="title mb-3">Were you satisfied with the bundle?
              <no-ssr>
                <star-rating></star-rating>
                </no-ssr>
             <v-text-field
                name="input-7-1"
                label="How can we improve it?"
                ></v-text-field>  
                <v-btn @click="feedbackSubmitted = true" large color="primary" class="mx-0">Submit feedback</v-btn>&nbsp;
          </div>
            
          <v-btn large color="primary" class="mx-0" 
            @click="$router.push('/dashboard')">Back to dashboard</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
    
  </v-jumbotron>
  <my-requests></my-requests>
  
</div>
</template>

<script>
import MyRequests from '~/components/requests/MyRequests'
import StarRating from 'vue-star-rating'

export default {
  components: {
    MyRequests,
    StarRating
  },
  data () {
    return {
      feedbackSubmitted: false
    }
  }
}
</script>