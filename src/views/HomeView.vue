<template>
  <main>
    <hero-component
      :title="'Stop burning accounts!'"
      :description="'Learn how to keep track of your passwords in a safe and simple manner'"
      :action="'Lock them up!'"
    ></hero-component>
    <problem-section></problem-section>
    <text-component
      backgroundColor="#00796b"
      textColor="#ffffff"
      sectionTitle="Section 1 Title"
      sectionContent="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla vitae elit libero, a pharetra augue."
    ></text-component>
    <stalk-section
      :title="`There is always someone with eyes on your data`"
    ></stalk-section>
    <text-component
      backgroundColor="#ff6f61"
      textColor="#ffffff"
      sectionTitle="Section 2 Title"
      sectionContent="Pellentesque nec turpis in ipsum cursus ullamcorper. Integer lacinia auctor condimentum."
    ></text-component>
    <features-section></features-section>
  </main>
</template>

<script>
import HeroComponent from '../components/sections/HeroComponent.vue';
import StalkSection from '../components/sections/StalkSection.vue';
import FeaturesSection from '../components/sections/FeaturesSection.vue';
import TextComponent from '../components/base/TextComponent.vue';
import ProblemSection from '../components/sections/ProblemSection.vue';

export default {
  components: {
    HeroComponent,
    StalkSection,
    FeaturesSection,
    TextComponent,
    ProblemSection
  },
  setup() {
  },
}
</script>
