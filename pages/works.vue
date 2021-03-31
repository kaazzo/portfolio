<template>
  <v-container fuild>
    <v-row>
      <v-col v-for="(work, i) in works" :key="i" cols="12" md="4">
        <v-card outlined>
          <v-card-title>
            <v-avatar>
              <img :src="`/${work.title}.png`" />
            </v-avatar>
            <a class="ml-3" @click="goto(work.url)">
              {{ work.title }}
              <v-icon small>mdi-checkbox-multiple-blank-outline</v-icon>
            </a>
          </v-card-title>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      works: [
        {
          title: 'github',
          url: 'https://github.com/kaazzo/'
        },
        {
          title: 'scrapbox',
          url: 'https://scrapbox.io/kaazzo/'
        },
        {
          title: 'qiita',
          url: 'https://qiita.com/kaazzo'
        }
      ]
    }
  },
  methods: {
    goto: url => {
      window.open(url, '_blank')
    }
  }
}
</script>
