<template>
  <div class="resource-selector-container">
    <CustomButton @click="setSelectedTab('ResourceList')" :class="{ 'current-button': selectedListButton }">
      RESOURCES LIST</CustomButton>
    <CustomButton @click="setSelectedTab('AddNewResource')" :class="{ 'current-button': selectedAddNewButton }">ADD NEW
      +</CustomButton>
  </div>
  <KeepAlive>
    <component :is="selectedTab"></component>
  </KeepAlive>

</template>

<script>
import CustomButton from './UI/CustomButton.vue'
import ResourceList from './ResourceList.vue';
import AddNewResource from './AddNewResource.vue';

export default {
  provide() {
    return { resourceList: this.resourceList, addNewResourceToList: this.addNewResourceToList, deleteResource: this.deleteResource }
  },
  components: { CustomButton, ResourceList, AddNewResource },
  data() {
    return {
      selectedTab: 'ResourceList',
      resourceList: [
        {
          id: "vue-official-guide",
          title: "Vue Official Guide",
          description: "Vue is a JavaScript framework for building user interfaces. It builds on top of standard HTML, CSS and JavaScript, and provides a declarative and component-based programming model that helps you efficiently develop user interfaces, be it simple or complex.",
          link: "https://vuejs.org/guide/introduction.html"
        },
        {
          id: "react-official-guide",
          title: "React Official Guide",
          description: "React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.",
          link: "https://reactjs.org/docs/getting-started.html"
        },
        {
          id: "angular-official-guide",
          title: "Angular Official Guide",
          description: "Angular is an application design framework and development platform for creating efficient and sophisticated single-page apps.",
          link: "https://angular.io/guide/developer-guide-overview"
        },
      ]
    }
  },
  computed: {
    selectedListButton() {
      return this.selectedTab === 'ResourceList'
    },
    selectedAddNewButton() {
      return this.selectedTab === 'AddNewResource'
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addNewResourceToList(title, description, url) {
      const newResource = {
        id: title.toLowerCase().replaceAll(' ', '-'),
        title,
        description,
        link: url
      };

      this.resourceList.unshift(newResource);
      this.setSelectedTab('ResourceList');
    },
    deleteResource(id) {
      const selectedIndex = this.resourceList.findIndex(item => item.id === id);
      this.resourceList.splice(selectedIndex, 1);
    }
  }
}
</script>

<style scoped>
.resource-selector-container {
  display: flex;
  justify-content: space-around;
  margin-bottom: 2rem;
}

.current-button {
  background-color: cadetblue;
  color: white;
}
</style>