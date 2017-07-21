<template>
  <v-container>
    <v-layout row-wrap class="mb-2">
      <v-flex xs12 sm6 class="text-xs-center text-sm-right">
        <v-btn large router to="/meetups" class="info">Explore meetups</v-btn>
      </v-flex>
      <v-flex xs12 sm6 class="text-xs-center text-sm-left">
        <v-btn large router to="/meetup/new" class="info">Create meetup</v-btn>
      </v-flex>      
    </v-layout>
    <v-layout row wrap>
      <v-flex xs12>
        <v-carousel>
    <v-carousel-item 
    v-for="(meetup,i) in meetups" 
    :src="meetup.imageUrl" 
    :key="meetup.id">
      <div class="title">
        {{meetup.title}}
      </div>
    </v-carousel-item>
  </v-carousel>
      </v-flex>
    </v-layout>

    <v-layout row wrap class="mt-2">
      <v-flex xs12 class="text-xs-center">
        <p>
          Join our awesome meetup!
        </p>
      </v-flex>
    </v-layout>

  </v-container>
</template>

<script>
export default {
  data () {
    return {
      meetups: [
        { imageUrl: 'https://media-cdn.tripadvisor.com/media/photo-s/0e/9a/e3/1d/freedom-tower.jpg', id: 'dsdd', title: 'Meet up in New York' },
        { imageUrl: 'https://en.parisinfo.com/var/otcp/sites/images/node_43/node_51/node_233/visuel-carrousel-dossier-ou-sortir-le-soir-a-paris-740x380-c-dr/16967596-1-fre-FR/Visuel-carrousel-dossier-Ou-sortir-le-soir-a-Paris-740x380-C-DR.jpg', id: 'abc', title: 'Meet up in Paris' }
      ]
    }
  }
}
</script>

<style scoped>
  .title {
    position: absolute;
    bottom: 50px;
    background-color: rgba(0,0,0,0.5);
    color: white;
    font-size: 2em;
    padding: 20px;    
  }
</style>
