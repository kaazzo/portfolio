<template>
  <v-container fluid>
    <v-parallax src="/background.jpg">
      <v-container fill-height>
        <v-row align="center" justify="center">
          <v-col class="text-center" cols="12">
            <h1 class="display-1 font-weight-thin mb-4">
              kaazzo's portfolio
            </h1>
            <h4 class="subheading">
              Welcome to my portfolio
            </h4>
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-btn outlined dark block to="/about">About Me</v-btn>
          </v-col>
          <v-col>
            <v-btn outlined dark block to="/skills">Skills</v-btn>
          </v-col>
          <v-col>
            <v-btn outlined dark block to="/works">Works</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-parallax>
  </v-container>
</template>

<script>
export default {}
</script>

<style scoped>
.container {
  max-width: 100%;
  width: 100%;
  padding: 0px;
}
.v-parallax {
  position: static;
}
</style>
