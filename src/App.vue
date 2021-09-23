<template>
    <FolderView name="$" :folders="folders" :files="files" />
</template>

<script>
import FolderView from "./components/FolderView.vue";
import data from "./data/list";

export default {
  name: "App",
  components: {
    FolderView,
  },
  data: () => data,
};
</script>

<style lang="scss">
:root {
  --body-color: #383838;
  --folder__item-height: 120px;
  --item-background-color: #FFFFFF
}
body {
  height: 100%;
  background-color: var(--body-color);
}
#app {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
  padding: 25px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
