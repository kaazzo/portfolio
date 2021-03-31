<template>
  <v-container fuild>
    <v-row>
      <v-col v-for="(skill, i) in skills" :key="i" cols="12" md="4">
        <v-card outlined>
          <v-card-title class="headline" v-text="skill.title"> </v-card-title>
          <v-card-text>
            {{ skill.description }}
            <div class="text-center mt-12">
              <v-rating
                v-model="skill.rating"
                color="yellow darken-3"
                background-color="grey darken-1"
                half-increments
                readonly
              >
              </v-rating>
            </div>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        {
          title: 'Java',
          description: 'Spring Framework(Spring Boot), Struts2, JUnit',
          rating: 4.5
        },
        {
          title: 'Javascript',
          description: 'Vue.js, Vuetify, Express.js, Jest',
          rating: 4
        },
        {
          title: 'Python',
          description: 'pandas, oepnpyxl, eel',
          rating: 1.5
        },
        {
          title: 'Git',
          description: 'Github, Gitlab',
          rating: 4.5
        },
        {
          title: 'Docker',
          description: 'docker-compose',
          rating: 3
        },
        {
          title: 'Blue Prism',
          description: 'Blue Prism Cloud',
          rating: 1
        }
      ]
    }
  }
}
</script>
