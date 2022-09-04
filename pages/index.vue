<template>
  <div>
    <MainIntro/>
    <v-divider />
    <Projects />
    <v-divider />
    <TechStack />
    <v-divider />
    <ContactMe />
    <v-divider />
  </div>
</template>

<script>
import MainIntro from '~/pages/MainIntro'
import Projects from '~/pages/MyProjects'
import TechStack from '~/pages/TechStack'
import ContactMe from '~/pages/ContactMe'

export default {
  name: 'IndexPage',
  components: {
    ContactMe,
    TechStack,
    Projects,
    MainIntro
  }
}
</script>
