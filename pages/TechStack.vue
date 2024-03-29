<template>
  <div class="mt-16 mb-16">
    <div class="section-title text-uppercase text-center font-header">
      My Tech Stack
    </div>
    <div class="stack mt-16">
      <v-row align="center" justify="center" class="stackContainer">
        <v-col
          v-for="stack of stacks"
          :key="stack.name"
          sm="6"
          md="3"
          class="d-flex justify-center"
        >
          <v-tooltip bottom>
            <template #activator="{ on, attrs }">
              <v-card
                v-bind="attrs"
                class="pa-5 text-center stack-img"
                color="white"
                width="8rem"
                height="8rem"
                v-on="on"
              >
                <v-card-text>
                  <v-img
                    :src="stack.img"
                    width="5rem"
                    lazy-src=""
                    transition="fade-transition"
                  >
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
                </v-card-text>
              </v-card>
            </template>
            <span>{{ stack.name }}</span>
          </v-tooltip>
        </v-col>
      </v-row>
      <v-row align="center" justify="center" style="margin-top: 8rem">
        <v-col>
          <div class="text-center">
            <v-icon size="8rem" color="rgb(229,254,199)">
              mdi-server
            </v-icon>
            <div class="card-title font-semi-bold font-header mt-5">
              Backend Design
            </div>
            <div class="card-sub-title">
              Design reactive Java backends with Spring framework
            </div>
          </div>
        </v-col>
        <v-col>
          <div class="text-center">
            <v-icon size="8rem" color="rgb(229,254,199)">
              mdi-webpack
            </v-icon>
            <div class="card-title font-semi-bold font-header mt-5">
              Frontend Develop
            </div>
            <div class="card-sub-title">
              Create the design of your websites and applications.
            </div>
          </div>
        </v-col>
        <v-col>
          <div class="text-center">
            <v-icon size="8rem" color="rgb(229,254,199)">
              mdi-ip-network
            </v-icon>
            <div class="card-title font-semi-bold font-header mt-5">
              Deployment
            </div>
            <div class="card-sub-title">
              Manage the deployment process with CI/CD pipelines
            </div>
          </div>
        </v-col>
      </v-row>
      <div class="description text-center" style="margin-top: 8rem">
        Passionate about back-end development and design, I am committed to carrying out the opportunities
        entrusted to me by building modern and effective solutions. Rigorous and demanding, I take care to respect
        the best practices and standards of the Web. Being also curious and open, I like to experiment with the latest
        trends through daily monitoring.
      </div>
      <div class="download-resume text-center">
        <v-btn outlined rounded class="text-none" height="50px">
          Download my resume
        </v-btn>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TechStack',
  data: () => ({
    a: '../assets/stacks/java.png',
    stacks: [
      {
        name: 'Java',
        img: require('../assets/stacks/java.png')
      },
      {
        name: 'React Native',
        img: require('../assets/stacks/react-native.png')
      },
      {
        name: 'Mongo',
        img: require('../assets/stacks/mongo.png')
      },
      {
        name: 'Spring Boot',
        img: require('../assets/stacks/spring-boot-logo.png')
      },
      {
        name: 'AWS',
        img: require('../assets/stacks/aws.png')
      },
      {
        name: 'Vue',
        img: require('../assets/stacks/vue.png')
      },
      {
        name: 'Docker',
        img: require('../assets/stacks/docker.webp')
      },
      {
        name: 'Github',
        img: require('../assets/stacks/github.png')
      }
    ]
  })
}
</script>

<style scoped>
.section-title {
  color: #c7ff84;
  font-size: 1.5rem;
  font-weight: 700;
}

.stack-img {
  transition: 0.4s transform;
}

.stack-img:hover {
  transform: scale(1.2) translateX(2px);
}

.card-title {
  color: #c7ff84;
  font-size: 1.875rem;
}

.card-sub-title {
  margin-top: 20px;
  font-size: 1.5rem;
  font-family: Overpass,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
  letter-spacing: .01em;
}

.description {
  font-size: 1.5rem;
  margin-bottom: 4rem;
  line-height: 1.625;
  font-family: Overpass,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
  letter-spacing: .01em;
  font-weight: 530;
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

.stackContainer {
  padding-left: 12rem; padding-right: 12rem
}

@media (max-width: 768px) {
  .stackContainer {
    padding-left: 0 !important;
    padding-right: 0 !important;
  }
}
</style>
