<template>
  <v-container>
    <v-layout row wrap class="mb-2">
      <v-flex xs12 xs6 class="text-xs-center text-sm-right pl-3 pr-2">
        <v-btn large><router-link to="/meetups">Explore Meetups</router-link></v-btn>
      </v-flex>
      <v-flex xs12 xs6 class="text-xs-center text-sm-left pr-2">
        <v-btn large><router-link to="/meetup/new">Organize Meetups</router-link></v-btn>
      </v-flex>
    </v-layout>
    <!-- <br> -->
    <v-layout row wrap>
      <v-flex xs12>
        <v-carousel
          v-model="model"
          :show-arrows="showArrows"
          :hide-delimiters="hideDelimiters"
          :cycle="cycle"
          style="cursor: pointer;"
        >
          <v-carousel-item
            v-for="meetup in meetups"
            :key="meetup.id"
            :src="meetup.imageUrl"
            @click="onLoadMeetup(meetup.id)"
          >
            <div class="title">
              {{ meetup.title }}
            </div>
          </v-carousel-item>
        </v-carousel>
      </v-flex>
    </v-layout>
    <v-layout row wrap class="mt-2 mb-3">
      <v-flex xs12 xs6 class="text-xs-center text-sm-right pl-3 pr-2">
        <v-btn large><router-link to="/meetups">Search Meetups</router-link></v-btn>
      </v-flex>
      <v-flex xs12 xs6 class="text-xs-center text-sm-left pr-2">
        <v-btn large><router-link to="/meetup/new">Promote Meetups</router-link></v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  data () {
    return {
      meetups: [
        { imageUrl: 'https://images.pexels.com/photos/1557547/pexels-photo-1557547.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260', id: 1, title: 'Meetup in New York' },
        { imageUrl: 'https://images.pexels.com/photos/89432/pexels-photo-89432.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940', id: 2, title: 'Meetup in London' },
        { imageUrl: 'https://images.pexels.com/photos/2363/france-landmark-lights-night.jpg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260', id: 3, title: 'Meetup in Paris' },
        { imageUrl: 'https://images.pexels.com/photos/2193300/pexels-photo-2193300.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940', id: 4, title: 'Meetup in Sydney' },
        { imageUrl: 'https://images.pexels.com/photos/532263/pexels-photo-532263.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940', id: 5, title: 'Meetup in Rome' }
      ],
      colors: [
        'primary',
        'secondary',
        'yellow darken-2',
        'red',
        'orange',
      ],
      model: 0,
      showArrows: true,
      hideDelimiters: false,
      cycle: true,
    }
  },
  methods: {
    onLoadMeetup(id) {
      this.$router.push('/meetups/' + id)
    }
  }
}
</script>

<style scoped>
  .title {
    text-align: center;
    background-color: rgba(0,0,0,0.5);
    color: white;
    font-size: 2em;
  }
</style>
