<template>
  <main>
    <hero-component
      :title="'Stop burning accounts!'"
      :description="'Learn how to keep track of your passwords in a safe and simple manner'"
      :action="'Lock them up!'"
    ></hero-component>
    <stalk-section
      :title="`There is always someone with eyes on your data`"
    ></stalk-section>
    <features-section></features-section>
  </main>
</template>

<script>
import HeroComponent from '../components/sections/HeroComponent.vue';
import StalkSection from '../components/sections/StalkSection.vue';
import FeaturesSection from '../components/sections/FeaturesSection.vue';

export default {
  components: {
    HeroComponent,
    StalkSection,
    FeaturesSection
  },
  setup() {
  },
}
</script>
