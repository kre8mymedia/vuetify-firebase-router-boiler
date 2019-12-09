<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex xs12>
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        ></v-img>
      </v-flex>

      <v-flex mb-4>
        
      </v-flex>

      <v-flex mb-5 xs12>
        <h3>This is mb-5 xs12</h3>
      </v-flex>

      <v-flex xs12 mb-5 >
        <h2 class="headline font-weight-bold mb-3">Settings Page</h2>
      </v-flex>

      <v-flex xs12 mb-5>
        <h2 class="headline font-weight-bold mb-3">Ecosystem</h2>
      </v-flex>
      
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'settings',
  data: () => ({
    
  }),
};
</script>
