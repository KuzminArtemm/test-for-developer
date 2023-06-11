<template>
  <div class="footer-wrapper">
    <div class="footer-item cell">
      Cellnet<img src="../assets/img/svg/indicator_online.svg" alt="cellnet" />
    </div>
    <div class="footer-item main">
      Mainnet<img src="../assets/img/svg/indicator_online.svg" alt="mainnet" />
    </div>
    <div class="footer-item some">
      Somenet<img src="../assets/img/svg/indicator_online.svg" alt="somenet" />
    </div>
    <div class="footer-item test">
      Testnet<img src="../assets/img/svg/indicator_online.svg" alt="testnet" />
    </div>
  </div>
</template>

<script>
export default {
  name: "footer-vue",
};
</script>

<style lang="scss" scoped>
.footer-wrapper {
  display: flex;
  width: 1280px;
  height: 42px;
  background: #2e3138;
  box-shadow: 5px -5px 10px rgba(8, 7, 13, 0.42), inset 1px 1px 0px #524d64;
}
.footer-item {
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #2e3138;
  text-align: center;
  width: 295px;
  height: 41px;
  padding: 5px;
  color: #ffffff;
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 15px;
  box-shadow: inset 0px 1px 0px #524d64;
}
.cell {
  margin-left: 50px;
}
.test {
  margin-right: 50px;
}
img {
  margin-left: 8px;
}
</style>
