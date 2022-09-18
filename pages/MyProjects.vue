<template>
  <v-row class="mt-16 px-16">
    <v-col v-for="project of projects" :key="project.title" md="6">
      <ProjectCard :project="project" />
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'MyProjects',
  data: () => ({
    projects: [
      {
        title: 'KLASS.LK',
        subTitle: 'Web application for online institute management and Learning management system (SAAS)',
        image: 'https://klass.lk/wp-content/uploads/2022/04/Klass-About.webp',
        link: 'https://klass.lk',
        github: 'https://github.com/klass-lk',
        tags: [
          'SAAS',
          'Vue.js',
          'Spring boot',
          'Mongo DB',
          'Java'
        ]
      },
      {
        title: 'Mutual Transfer',
        subTitle: 'Mobile app for government mutual transfers built with React Native and published on the Play Store (iOS).',
        image: 'https://play-lh.googleusercontent.com/pU0zftnXvvEOMoOK-7Qp1IJ4Qa90fX5oxS-XJ_tj5tsDb7DvpOQQot9NqGKcRC5b4g4D=w832-h470-rw',
        link: 'https://play.google.com/store/apps/details?id=com.mutualtransfers',
        github: '',
        tags: [
          'Branding',
          'React Native',
          'Mobile',
          'Spring boot',
          'Mongo DB'
        ]
      },
      {
        title: 'FOSS ALGO',
        subTitle: 'Manage community driven algorithm collection with hacktoberfest contest.',
        image: 'https://res.cloudinary.com/practicaldev/image/fetch/s--cwRVKpcp--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/ayhj7n2ku7i1wes6nmcm.jpg',
        link: 'https://github.com/FOSS-UCSC/FOSSALGO',
        github: 'https://github.com/FOSS-UCSC/FOSSALGO',
        tags: [
          'Open Source',
          'Algo',
          'Crowd source',
          'Hacktoberfest'
        ]
      }
    ]
  })
}
</script>

<style scoped>
@media (max-width: 768px) {
  .px-16 {
    padding-left: 0 !important;
    padding-right: 0 !important;
  }
}
</style>
