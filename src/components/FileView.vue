<template>
  <div class="file folder__item">{{ name }}</div>
</template>

<script>
export default {
  name: "FileView",
  props: {
    name: String,
  },
};
</script>

<style scoped lang="scss">
.folder__item {
  flex: 0 1 49%;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: var(--folder__item-height);
  min-width: 200px;
  color: green;
  background-color: var(--item-background-color);
  border-radius: 25px;
  position: relative;
}
@media (max-width: 769px) {
  .folder__item:not(:last-child) {
    margin-bottom: 10px;
  }
}
.folder__item::before {
  content: "";
  position: absolute;
  left: 0;
  width: 100%;
  height: 100%;
  background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 320'%3E%3Cpath fill='%230099ff' fill-opacity='1' d='M0,224L30,240C60,256,120,288,180,282.7C240,277,300,235,360,218.7C420,203,480,213,540,229.3C600,245,660,267,720,240C780,213,840,139,900,133.3C960,128,1020,192,1080,192C1140,192,1200,128,1260,112C1320,96,1380,128,1410,144L1440,160L1440,320L1410,320C1380,320,1320,320,1260,320C1200,320,1140,320,1080,320C1020,320,960,320,900,320C840,320,780,320,720,320C660,320,600,320,540,320C480,320,420,320,360,320C300,320,240,320,180,320C120,320,60,320,30,320L0,320Z'%3E%3C/path%3E%3C/svg%3E")
    0 0/100% auto no-repeat;
  border-radius: 25px;
  opacity: 0.6;
  background-position-y: 100px;
  transition: color, background 0.5s ease-in-out;
}
.folder__item:hover::before {
  background-position-y: -5px;
  
}
.folder__item:hover {
  color: orangered;  
  background-color: var(--item-background-color);
  box-shadow: 0 0 15px turquoise;
}
@media (max-width: 1200px) {
  .folder__item:hover::before {
    background-position-y: 20px;
  }
}
@media (max-width: 426px) {
  .folder__item:hover::before {
    background-position-y: 40px;
  }
}
@media (max-width: 376px) {
  .folder__item:hover::before {
    background-position-y: 65px;
  }
}
</style>
