<template>
  <div>
    <MainIntro/>
    <v-divider />
    <Projects/>
  </div>
</template>

<script>
import MainIntro from '~/pages/MainIntro'
import Projects from '~/pages/MyProjects'

export default {
  name: 'IndexPage',
  components: {
    Projects,
    MainIntro
  }
}
</script>
