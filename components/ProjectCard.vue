<template>
  <v-sheet class="pa-10" color="transparent" height="550px">
    <v-img
      class="project-img"
      :src="project.image"
      style="border-radius: 20px"
      height="220px"
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
    <div class="card-title mt-5 font-header">
      {{ project?.title }}
      <v-icon v-if="project?.link" color="#c7ff84" @click="openLink(project?.link)">
        mdi-open-in-new
      </v-icon>
      <v-icon v-if="project?.github" color="#c7ff84" @click="openLink(project?.github)">
        mdi-github
      </v-icon>
    </div>
    <div class="card-sub-title">
      {{ project?.subTitle }}
    </div>
    <div class="tags">
      <v-chip
        v-for="tag of project?.tags"
        :key="tag"
        class="ma-2"
        label
        color="#2d3748"
      >
        {{ tag }}
      </v-chip>
    </div>
  </v-sheet>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    project: {
      type: Object,
      required: true
    }
  },
  methods: {
    openLink (link) {
      window.open(link, '_blank')
    }
  }
}
</script>

<style scoped>
.card-title {
  color: #c7ff84;
  font-size: 1.65rem;
  font-weight: 700;
}
.card-sub-title {
  margin-bottom: 1.5rem;
  font-size: 1.25rem;
  line-height: 1.5;
}
.project-img {
  transition: 0.4s transform;
}
.project-img:hover {
  transform: scale(1.2) translateX(10px);
}
</style>
