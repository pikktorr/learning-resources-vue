<template>
  <TheHeader />
  <ResourceList :resourceList="resourceList" />
</template>

<script>
import ResourceList from './components/ResourceList.vue';
import TheHeader from './components/TheHeader.vue';
export default {
  data() {
    return {
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
    };
  },
  components: { ResourceList, TheHeader }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@300;400;700&family=Roboto+Slab:wght@700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Comfortaa', cursive;
}

h1 {
  font-weight: 700;
  text-transform: uppercase;
}

p,
a {
  font-weight: 300;
  font-size: small;
}

a {
  color: inherit;
  text-decoration: none;
}

a:visited {
  color: inherit
}
</style>