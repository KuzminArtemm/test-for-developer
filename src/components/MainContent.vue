<template>
  <div class="main-wrapper">
    <div v-if="items.title">
      <p class="main-title">
        {{ items.title }}
      </p>
      <div v-if="radio === 'radio-1'">
        <p class="main-body">Public</p>
        <div class="main-items" :key="el" v-for="el of items.body['Public']">
          {{ el }}
        </div>
      </div>
      <div v-else-if="radio === 'radio-2'">
        <p class="main-body">Private</p>
        <div class="main-items" :key="el" v-for="el of items.body['Private']">
          {{ el }}
        </div>
      </div>
      <div v-else-if="radio === 'radio-3'">
        <p class="main-body">Public && Private</p>
        <div class="main-items" :key="el" v-for="el of items.body['Public']">
          {{ el }}
        </div>
        <div class="main-items" :key="el" v-for="el of items.body['Private']">
          {{ el }}
        </div>
      </div>
      <div class="main-items" v-else>list is empty</div>
    </div>
    <h3 class="main-empty" v-else>list is empty</h3>
  </div>
</template>

<script>
export default {
  name: "main-content",
  props: {
    items: {
      type: Object,
      required: true,
    },
    radio: "",
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.main-wrapper {
  overflow: auto;
  width: 678px;
  height: 570px;
  background: #363a42;
  box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49),
    inset 3px 3px 5px rgba(8, 7, 13, 0.25);
  border-radius: 12px;
  margin: 22px;
}
.main-title {
  margin-left: 16px;
  margin-top: 12px;
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 18px;
  color: #ffffff;
}
.main-empty {
  margin-left: 16px;
  margin-top: 12px;
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 18px;
  color: #ffffff;
}
.main-body {
  display: flex;
  align-items: center;
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 15px;
  padding-left: 18px;
  margin-top: 12px;
  color: #ffffff;
  background-color: #2e3138;
  width: 660px;
  height: 30px;
}
.main-items {
  display: flex;
  align-items: center;
  box-sizing: border-box;
  width: 646px;
  height: 40px;
  left: 16px;
  top: 72px;
  background: #363a42;
  border-bottom: 1px solid #2e3138;
  width: 646px;
  height: 49px;
  margin-left: 16px;
  margin-right: 16px;
  color: #ffffff;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
}
</style>
