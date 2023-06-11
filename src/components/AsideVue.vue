<template>
  <div class="wrapper">
    <div class="img-wrapper">
<img
      class="logo"
      src="../assets/img/svg/logoo.svg"
      alt="logo"
    />
    <img class="litter" src="../assets/img/svg/path1429.svg" alt="">
    </div>
    
    <div class="menu" :key="element" v-for="element in elements">
      <button
        @click="
          isActive = `${element.id}`;
          createElement();
        "
        :class="{
          active: isActive == `${element.id}`,
          notactive: isActive !== `${element.id}`,
        }"
        class="menu__item"
      >
        <img
          class="img"
          :src="require(`../assets/img/svg/${element.icon}`)"
          alt=""
        />{{ element.title }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "aside-vue",
  data() {
    return {
      isActive: "",
      result: Object,
      elements: [
        {
          id: 1,
          title: "wallet",
          active: false,
          icon: "navigation_icons.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 2,
          title: "DEX",
          active: false,
          icon: "arrows.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 3,
          title: "TX explorer",
          active: false,
          icon: "watch.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 4,
          title: "Certificates",
          active: false,
          icon: "certificate.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 5,
          title: "Tokens",
          active: false,
          icon: "tokens.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 6,
          title: "VPN client",
          active: false,
          icon: "desktop.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 7,
          title: "VPN service",
          active: false,
          icon: "sun.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 8,
          title: "Console",
          active: false,
          icon: "console.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 9,
          title: "Logs",
          active: false,
          icon: "logs.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 10,
          title: "Settings",
          active: false,
          icon: "settings.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
        {
          id: 11,
          title: "dApps",
          active: false,
          icon: "dapps.svg",
          body: {
            Public: [
              "core-t0",
              "core-t1",
              "core-t2",
              "test.test1",
              "test.test2",
              "test.test3",
              "test.test4",
              "test.test5",
              "test.test6",
              "test.test7",
            ],
            Private: ["private1"],
          },
        },
      ],
    };
  },
  methods: {
    createElement() {
      this.elements.forEach((el) => {
        if (el.id === +this.isActive) {
          this.result = el;
        }
      });
      console.log(this.result);
      this.$emit("create", this.result);
    },
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  width: 180px;
  height: 673px;
  background: #2d3037;
  border-radius: 0px 0px 16px 0px;
  left: 0%;
  right: 0%;
  top: 0%;
  bottom: 0%;
  box-shadow: 5px 5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524d64;
  margin: 0px 2px 3px 0px;
}
.logo {
  width: 58px;
  height: 57px;
  margin-left: 10px;
  margin-top: 20px;
 }
.litter {
  width: 77px;
  height: 57px;
  margin-left: 0px;
}
.menu__item {
  border: none;
  padding: 0px;
  background-color: #2d3037;
  font-style: normal;
  font-weight: 400;
  font-size: 13px;
  line-height: 16px;
  color: #ffff;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  width: 170px;
  height: 52px;
  margin-left: 0px;
  padding-left: 20px;
}
.img {
  margin-right: 10px;
}
.active {
  background: #2e3138;
  /* MainBlockShadow1 */

  box-shadow: 1px 1px 0px rgba(107, 102, 126, 0.49),
    inset 3px 3px 5px rgba(8, 7, 13, 0.25);
  border-radius: 0px 16px 16px 0px;
}
.notactive {
  background: #2e3138;
}
</style>
