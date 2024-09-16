<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="selectedTab === 'stored-resources' ? null : 'flat'"
      >Stored Resources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resource')"
      :mode="selectedTab === 'sadd-resource' ? null : 'flat'"
      >Add Resources</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from "../StoredResources.vue";
import AddResource from "../AddResource.vue";
export default {
  data() {
    return {
      selectedTab: "stored-resources",
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
  components: {
    StoredResources,
    AddResource,
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
  },
  mounted() {},
};
</script>
