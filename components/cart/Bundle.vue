<template>
  <v-layout>
    <v-flex>
      <v-card>
        
        <v-card-title primary-title>
          <div>
              <img  src="https://cdn0.iconfinder.com/data/icons/logistic-5/32/11_box_package_parcel_logistic_delivery_unpack_open_shipping-512.png" width="30%"> 
            <h3 class="headline mb-0">Standard Bundle</h3>
            <div>We think this bundle is the right one for you<br>Content: Laptop, Screen, MS Office, ...</div>
            <div>Approval Cycle: <b>Pre-approved</b></div>
            <div>ETA: 24 hours</div>
            <v-list-tile-sub-title>
                    <v-stepper value="0">
                        <v-stepper-header>
                        <v-stepper-step step="1">Submitted</v-stepper-step>
                        <v-divider></v-divider>
                        <v-stepper-step step="2">Prepared</v-stepper-step>
                        <v-divider></v-divider>
                        <v-stepper-step step="3">Delivered</v-stepper-step>
                        </v-stepper-header>
                    </v-stepper>
                </v-list-tile-sub-title>
          </div>
        </v-card-title>
        <v-card-actions>
          <v-btn flat color="orange">Add</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  export default {
    data () {
      return {
        card_text: 'STANDARD BUNDLE: Lorem ipsum dolor sit amet, brute iriure accusata ne mea. Eos suavitate referrentur ad, te duo agam libris qualisque, utroque quaestio accommodare no qui. Et percipit laboramus usu, no invidunt verterem nominati mel. Dolorem ancillae an mei, ut putant invenire splendide mel, ea nec propriae adipisci. Ignota salutandi accusamus in sed, et per malis fuisset, qui id ludus appareat.'
      }
    }
  }
</script>