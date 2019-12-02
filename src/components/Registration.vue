<template>
    <div>
        <v-flex>
        <v-flex row justify-center pa-5>
            <span class="display-2">Create your account</span>
        </v-flex>
        <v-flex>
            <v-card
    class="mx-auto"
    max-width="644"
    elevation="5"
  >
  <v-progress-linear rounded striped :value="progressValue" height="9"></v-progress-linear>
    <v-card-text>
      <div></div>
      <p class="display-1 text--primary">
        <!-- be•nev•o•lent -->
        <v-col cols="12">
            <v-text-field
                label="Password"

                outlined
            ></v-text-field>
          </v-col>
      </p>
      <p>
        <v-col cols="12">
            <v-text-field
                label="Username"
                outlined
                
            ></v-text-field>
          </v-col>
          </p>
          <p>
        <v-col cols="12">
            <v-text-field
                label="E-mail"
                outlined
                
            ></v-text-field>
          </v-col>
          </p>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Learn More
      </v-btn>
    </v-card-actions>
  </v-card>
        </v-flex>
        </v-flex>
    </div>
</template>
<script>
export default {
    data:()=>({
        progressValue: 0
    }),
    methods:{
        
    }
}
</script>