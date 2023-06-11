<template>
  <div class="search-wrapper">
    <div class="search-block">
      <input
        v-model="title"
        @input="title = $event.target.value"
        class="search__txt"
        placeholder="Search"
        type="search"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "search-panel",
  data() {
    return {
      title: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.search-block {
  width: 1097px;
  height: 60px;
  background: #2e3138;
  border-radius: 0px 0px 0px 16px;
  left: 0%;
  right: 0%;
  top: 0%;
  bottom: 0%;
  box-shadow: 5px 5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524d64;
}
.conteiner {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
}
input {
  background-color: #2e3138;
  background: transparent;
  margin: 10px 837px 15px 36px;
  height: 35px;
  border: none;
  border-bottom: 1px solid #393b41;
  width: 224px;
  position: relative;
}
input::placeholder {
  padding-bottom: 6px;
}
</style>
