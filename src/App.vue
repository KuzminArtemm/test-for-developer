<template>
  <div class="app">
    <aside-vue @create="createElement" class="app__aside"></aside-vue>
    <search-panel class="app__search"></search-panel>
    <main-content
      :radio="radio"
      :items="items"
      class="app__main"
    ></main-content>
    <aside-right
      @update:modelValue="changeOption"
      :items="items"
      class="app__right"
    ></aside-right>
    <footer-vue class="app__footer"></footer-vue>
  </div>
</template>

<script>
import AsideRight from "./components/AsideRight.vue";
import AsideVue from "./components/AsideVue.vue";
import FooterVue from "./components/FooterVue.vue";
import MainContent from "./components/MainContent.vue";
import SearchPanel from "./components/SearchPanel.vue";
export default {
  components: { AsideVue, SearchPanel, FooterVue, MainContent, AsideRight },
  data() {
    return {
      items: Object,
      radio: "",
    };
  },

  methods: {
    createElement(result) {
      this.items = result;
      console.log(this.items);
    },
    changeOption(event) {
      this.radio = event;
      console.log("events", this.radio);
    },
  },
};
</script>

<style lang="scss" scoped>
.app {
  width: 1280px;
  height: 712px;
  display: grid;
  grid-template-columns: auto auto auto;
  grid-auto-rows: auto auto auto;
  font-family: Quicksand;
  background: #3c3b3b;
  grid-template-areas:
    "aside search search"
    "aside main aside-right"
    "footer footer footer";
}
.app__aside {
  grid-area: aside;
}
.app__search {
  grid-area: search;
}
.app__footer {
  grid-area: footer;
}
.app__main {
  grid-area: main;
}
.app__right {
  grid-area: aside-right;
}
@media screen and (max-width: 720px) {
    .app {
    grid-template-columns: repeat(2, 1fr);
    grid-template-areas:
      "aside search"
      "aside-right main"
      "footer footer"
      
  }
}
</style>
