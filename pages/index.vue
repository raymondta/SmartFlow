<template>
  <v-container>
    <v-layout column justify-center align-center>
        <v-flex xs12 sm8 md6>
        <v-container>
          <v-card flat>
            <v-card-title primary-title>
                <img src="/logo.png"/>
            </v-card-title>
            <v-form>
            <v-text-field prepend-icon="person" name="Username" label="Username"></v-text-field>
            <v-text-field prepend-icon="lock" name="Password" label="Password" type="password"></v-text-field>
            <v-card-actions>
              <v-btn primary large block @click="login">Login</v-btn>
            </v-card-actions>
            </v-form>
          </v-card>
        </v-container>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  layout: 'noNav',
  methods: {
    login: function () {
      this.$router.push('/dashboard')
    }
  }
}
</script>