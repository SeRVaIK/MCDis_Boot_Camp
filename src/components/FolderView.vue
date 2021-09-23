<template>
  <div class="wrapper">
    <p class="folder">{{ name }}</p>
  </div>
  <template v-for="folder in folders">
    <FolderView
      :name="folder.name"
      :folders="folder.folders"
      :files="folder.files"
    />
  </template>
  <div class="folder__list">
    <template v-for="file in files">
      <FileView :name="file.name" />
    </template>
  </div>
</template>

<script>
import FileView from "./FileView";
export default {
  name: "FolderView",
  components: { FileView },
  props: {
    name: String,
    folders: Array,
    files: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.wrapper {
  width: 100%;
  background-color: lightblue;
  border-radius: 15px;
  transition: width, border-radius 0.4s ease-in-out;
}
.wrapper {
  margin-bottom: 15px;
}
.wrapper:active {
  border-radius: 25px;
}
.folder {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  color: orangered;
}
.folder__list {
  width: 100%;
  min-height: calc((var(--folder__item-height) * 2.5) - 10px);
  display: flex;
  align-content: space-between;
  justify-content: space-between;
  flex-wrap: wrap;
  padding: 5px;
  margin-bottom: 15px;
}
@media (max-width: 769px) {
  .folder__list {
    display: inline-block;
  }
}
.wrapper:last-of-type {
  background-color: #FFF;
}
</style>
