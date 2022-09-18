<template>
  <v-row align="center" justify="center" class="mt-16 mb-16">
    <v-col class="avatarContainer" md="3">
      <div style="width: 16rem">
        <v-img :src="require('../assets/avatar.jpeg')" class="avatar" transition="fade-transition" lazy-src="">
          <template #placeholder>
            <v-row
              align="center"
              class="fill-height ma-0"
              justify="center"
            >
              <v-progress-circular
                color="grey lighten-5"
                indeterminate
              />
            </v-row>
          </template>
        </v-img>
      </div>
    </v-col>
    <v-col md="6" class="ml-16">
      <div>
        <h1 class="subheading mb-3 font-body">
          Hello ! I'm Danushka Herath
        </h1>
      </div>
      <div>
        <h2 class="heading font-body">
          Software Engineer & <br>
          Front-end Developer
        </h2>
      </div>
      <div class="description font-body mt-2">
        I design and develop responsive, optimized and efficient websites. Currently available for freelance opportunities.
      </div>
      <div class="actions">
        <v-row>
          <v-col lg="6" sm="12" class="buttonCol">
            <v-btn outlined rounded class="text-none" height="50px">
              Get in touch
            </v-btn>
          </v-col>
          <v-col lg="6" sm="12" class="buttonCol">
            <v-btn outlined rounded class="text-none" height="50px">
              My resume
            </v-btn>
          </v-col>
        </v-row>
      </div>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'MainIntro'
}
</script>

<style scoped>
.heading {
  font-size: 3rem;
  font-weight: 700;
  color: #c7ff84;
  line-height: 1.25;
}
.subheading {
  font-size: 1.65rem;
  font-weight: 700;
  color: #e5fec7;
  margin-bottom: 1rem;
}
.description {
  color: #f7fafc;
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
}
.font-body {
  font-family: Overpass,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
}
.v-btn {
  border: solid #e5fec7;
  font-size: 1.35rem;
}

.v-btn:hover {
  background-color: #c7ff84;
  color: #1A202C;
  transition: 0.5s
}

::v-deep .v-btn__content {
  padding: 0.5rem 1.5rem;
}

.avatar {
  border-radius: 30px;
  transition: 0.4s transform;
}

.avatar:hover {
  transform: scale(1.2) translateX(10px);
}

.avatarContainer {
  display: flex;justify-content: flex-end;
}

@media (max-width: 768px) {
  .avatarContainer {
    justify-content: center
  }
  .subheading {
    text-align: center !important;
  }
  .ml-16 {
    margin-left: 3px !important;
  }
  .heading {
    text-align: center !important;
  }
  .description {
    text-align: center !important;
  }
  .buttonCol {
    text-align: center !important;
  }
}
</style>
