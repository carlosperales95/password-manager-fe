<template>
  <main>
    <hero-component
      :title="'Welcome to my page!'"
      :description="'This is a little description about what you xan find and sth else'"
      :action="'Start journey'"
    ></hero-component>
  </main>
</template>

<script>
import HeroComponent from '../components/layout/HeroComponent.vue';
export default {
  components: {
    HeroComponent
  },
  setup() {
  },
}
</script>
