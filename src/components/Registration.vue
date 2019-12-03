<template>
  <div>
    <v-flex>
      <v-flex row justify-center pa-5>
        <span class="display-2">Create your account</span>
      </v-flex>
      <v-flex>
        <v-card class="mx-auto" max-width="644" elevation="10">
          <v-progress-linear
            rounded
            striped
            :value="progressValue"
            height="9"
          ></v-progress-linear>
          <v-card-text class="mt-10">
            <v-form>
            <p class="display-1 text--primary">
              <!-- be•nev•o•lent -->
              <v-col cols="12">
                <v-text-field
                  :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
                  :rules="[rules.required, rules.min]"
                  :type="show2 ? 'text' : 'password'"
                  name="input-10-2"
                  label="Password"
                  hint="At least 8 characters"
                  value=""
                  class="input-group--focused"
                  @click:append="show2 = !show2"
                ></v-text-field>
              </v-col>
            </p>
            <p>
              <v-col cols="12">
                <v-text-field
                  label="Username"
                  :rules="[rules.counter, rules.required]"
                  v-model="username"
                  counter
                  maxlength="20"
                >
                </v-text-field>
              </v-col>
            </p>
            <p>
              <v-col cols="12">
                <v-text-field
                  label="E-mail"
                  v-model="email"
                  :rules="[rules.required, rules.email]"
                ></v-text-field>
              </v-col>
            </p>
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-hover>
              <v-btn
                text
                color="deep-purple accent-4"
                slot-scope="{ hover }"
                :class="`elevation-${hover ? 12 : 0}`"
                @click="pagination--, (progressValue -= 25)"
              >
                <v-icon>mdi-arrow-left-bold</v-icon>Back
              </v-btn>
            </v-hover>
            <v-spacer></v-spacer>
            <v-hover>
              <v-btn
                slot-scope="{ hover }"
                :class="`elevation-${hover ? 12 : 0}`"
                text
                color="deep-purple accent-4"
                @click="pagination++, (progressValue += 25)"
              >
                Next<v-icon>mdi-arrow-right-bold</v-icon>
              </v-btn>
            </v-hover>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-flex>
  </div>
</template>
<script>
export default {
  data: () => ({
    progressValue: 0,
    pagination: 0,
    email: "",
    username: "",
    password: "",
    show2: false,
    rules: {
      required: value => !!value || "Required.",
      counter: value => value.length <= 20 || "Max 20 characters",
      min: v => v.length >= 8 || "Min 8 characters",
      email: value => {
        const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return pattern.test(value) || "Invalid e-mail.";
      },
      password: value => value.length <= 5 || "Pass"
      // username: value =>{
      //   value
      // }
    }
  }),
  methods: {}
};
</script>
