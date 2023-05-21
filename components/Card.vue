<template>
  <div class="card">
    <header class="header"><h3>{{ project.name }}</h3></header>
    <div class="picture-container">
      <picture class="grayscale-background" :style="`background-image:url(${project.covers.max_808});`" :title="project.name">
    <!-- <source
        :srcset="`${project.covers['115']} 115w, ${project.covers['808']} 808w,  ${project.covers.original} 1200w`">
    <img :src="project.covers.max_808" :alt="project.name"> -->
    </picture>
    </div>
    <p class="p"><a :href="project.url" class="pure-button" target="_blank">READ MORE</a></p>
  </div>
</template>

<script>
export default {
  props: {
    project: {
      type: Object,
      required: true
    }
  }
};
</script>