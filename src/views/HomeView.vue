<template>
  <div class="home">
    <NavigationHeader />
    <HeroSection />
  </div>
</template>

<script>
import NavigationHeader from "@/components/NavigationHeader.vue";
import HeroSection from "@/components/HeroSection.vue";
export default {
  name: 'HomeView',
  components: {
    NavigationHeader,
    HeroSection
  }
}
</script>
