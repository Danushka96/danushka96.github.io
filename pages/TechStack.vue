<template>
  <div class="mt-16 px-16 mb-16">
    <div class="section-title text-uppercase text-center font-header">
      My Tech Stack
    </div>
    <div class="stack mt-16">
      <v-row justify="space-between" align="center">
        <v-col
          v-for="stack of stacks"
          :key="stack.name"
          sm="6"
          md="3"
          class="justify-center align-center"
        >
          <v-tooltip bottom>
            <template v-slot:activator="{ on, attrs }">
              <v-card
                v-bind="attrs"
                v-on="on"
                class="pa-5 text-center stack-img"
                color="white"
                width="8rem"
                height="8rem"
              >
                <v-card-text>
                <v-img
                  :src="stack.img"
                  width="5rem"
                />
                </v-card-text>
              </v-card>
            </template>
            <span>{{ stack.name }}</span>
          </v-tooltip>
        </v-col>
      </v-row>
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
</style>
