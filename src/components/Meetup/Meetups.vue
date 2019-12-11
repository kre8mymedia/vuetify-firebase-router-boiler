<template>
  <v-container dark>
    <v-row no-gutters>
      <v-col
        v-for="meetup in meetups"
        :key="meetup.id"
        cols="12"
        sm="4"
      >
        
        <v-card
          class="mr-2 mb-3"
          max-width="400"
        >
          <v-img
            class="white--text align-end"
            height="200px"
            :src="meetup.imageUrl"
          >
          </v-img>
          
          <v-card-title>{{meetup.title}}</v-card-title>

          <v-card-subtitle class="pb-0">{{meetup.place}}</v-card-subtitle>

          <v-card-text class="text--primary">
            <div>{{meetup.addressStart}}</div>

            <div>{{meetup.addressEnd}}</div>
          </v-card-text>

          <v-card-actions
            class="d-flex flex-row-reverse"
          >
            <v-btn
              color="orange"
              text
            >
              Share
            </v-btn>

            <v-btn
              color="orange"
              text
            >
              Explore
            </v-btn>
          </v-card-actions>
        </v-card>

      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      meetups: [
        { 
          id: 1, 
          imageUrl: 'https://images.pexels.com/photos/1557547/pexels-photo-1557547.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260', 
          title: 'Meetup in New York', 
          place: 'McDonalds',
          addressStart: '123 New York Ave',
          addressEnd: 'New York, NY 32830'
        },
        { 
          id: 2,
          imageUrl: 'https://images.pexels.com/photos/89432/pexels-photo-89432.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',  
          title: 'Meetup in London',
          place: 'Big Ben Tower next to the palace',
          addressStart: '737 London Blvd',
          addressEnd: 'London, UK 32830'
        },
        { 
          id: 3, 
          imageUrl: 'https://images.pexels.com/photos/2363/france-landmark-lights-night.jpg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260', 
          title: 'Meetup in Paris',
          place: 'The Eiffel Tower with your girl',
          addressStart: '3923 Paris Rd',
          addressEnd: 'Paris, France 32830'
        },
        { 
          id: 4,
          imageUrl: 'https://images.pexels.com/photos/2193300/pexels-photo-2193300.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940', 
          title: 'Meetup in Sydney',
          place: 'Throwin Shrimp on the Barby with the Mates',
          addressStart: '320 Koala Rd',
          addressEnd: 'Barby, Outback 32933'
        },
        { 
          id: 5,
          imageUrl: 'https://images.pexels.com/photos/532263/pexels-photo-532263.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',
          title: 'Meetup in Rome',
          place: 'Amakin pizzas with some mafiosos',
          addressStart: '133 Pizza St',
          addressEnd: 'Rome, Italy 32039'
        }
      ],
    }
  }
}
</script>

<style scoped>
  .title {
    background-color: rgba(0,0,0,0.5);
    color: white;
    font-size: 2em;
  }
</style>