<template>
  <ul>
    <learning-resource
      v-for="res in storedResources"
      :key="res.id"
      :title="res.title"
      :description="res.description"
      :link="res.link"
    >
    </learning-resource>
  </ul>
</template>

<script>
import LearningResource from "./components/LearningResource.vue";

export default {
  name: "App",
  components: {
    LearningResource,
  },
  data() {
    return {
      storedResources: [
        {
          id: "official-guid",
          title: "Official Guide",
          description: "The official Vue.js documentation",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          description: "Learn to Google....",
          link: "https://www.google.com",
        },
      ],
    };
  },
};
</script>

<style></style>
