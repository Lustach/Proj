<template>
  <v-app>
  <div>
        <v-layout>

        <v-toolbar color="primary">
            <v-btn text icon color="white">
              <v-icon>mdi-menu</v-icon><!-- logo -->
            </v-btn>

          <v-col cols="2" class="mt-2">
            <v-text-field
              placeholder="Search..."
              solo
            ></v-text-field>
          </v-col>
            <v-btn text rounded color="white">
              <span>Я ментор</span>
            </v-btn>
            <v-btn text rounded color="white">
              <span>Я ищу ментора</span>
            </v-btn>
          <v-spacer></v-spacer>

            <v-btn text rounded color="white">
              <router-link to="/login"><span>Sign in</span></router-link>
            </v-btn>
            <v-btn text rounded color="white">
              <span>Sign up</span>
            </v-btn>

        </v-toolbar>

        </v-layout>
        <v-flex>
        <v-layout row wrap>
          
        </v-layout>
      </v-flex>
      </div>
    
    <v-content>
      <!-- <Registration/> -->
      <router-view/>
      <!-- <Registration/> -->
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Registration from './components/Registration'
export default {
  name: 'App',

  components: {
    HelloWorld,
    Registration
  },

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
.v-text-field__details{
  display:none;
}
// .container{
//   display:none;
// }
</style>