<template>
  <div class="right-wrapper">
    <p class="filter">Filter</p>
    <div class="radio-wrapper">
      <input
        id="radio-1"
        placeholder="Public certificate"
        name="radio"
        class="radio"
        type="radio"
        @change="changeOption"
      />
      <label for="radio-1">Public certificate</label>
      <br />
      <input
        id="radio-2"
        @change="changeOption"
        name="radio"
        class="radio"
        type="radio"
      />
      <label for="radio-2">Private certificate</label>
      <br />
      <input
        id="radio-3"
        @change="changeOption"
        name="radio"
        class="radio"
        type="radio"
      />
      <label for="radio-3">Both</label>
    </div>
    <p class="actions">Actions</p>
    <div class="buttons-wrapper">
      <button
        @click="isActive = 1"
        class="btn item-1"
        :class="{ active: isActive == 1, notactive: isActive !== 1 }"
      >
        Create certificate
      </button>
      <button
        @click="isActive = 2"
        class="btn item-2"
        :class="{ active: isActive == 2, notactive: isActive !== 2 }"
      >
        Import certificate
      </button>
      <button
        @click="isActive = 3"
        class="btn item-3"
        :class="{ active: isActive == 3, notactive: isActive !== 3 }"
      >
        Export private certificate to public
      </button>
      <button
        @click="isActive = 4"
        class="btn item-4"
        :class="{ active: isActive == 4, notactive: isActive !== 4 }"
      >
        Export certificate to mempool
      </button>
      <button
        @click="isActive = 5"
        class="btn item-5"
        :class="{ active: isActive == 5, notactive: isActive !== 5 }"
      >
        Delete certificate
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "aside-right",
  data() {
    return {
      isActive: "",
    };
  },
  props: {
    items: {
      type: Object,
      required: true,
    },
  },
  methods: {
    handleActive(e) {
      if (e.target) this.isActive = !this.isActive;
    },
    changeOption(event) {
      console.log(event.isTrusted);
      this.$emit("update:modelValue", event.target.id);
    },
  },
};
</script>

<style lang="scss" scoped>
.right-wrapper {
  width: 351px;
  height: 570px;
  margin-top: 24px;
  margin-bottom: 24px;
}
.filter {
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 18px;
  color: #ffffff;
}
.radio-wrapper {
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 20px;
  color: #ffffff;
}
input[type="radio"]:after {
  width: 4px;
  height: 4px;
  border-radius: 15px;
  top: -2px;
  left: -1px;
  position: relative;
  background-color: #717580;
  content: "";
  display: inline-block;
  visibility: visible;
  border: 5px solid #2d3037;
  box-shadow: 2px 2px 5px rgba(8, 7, 13, 0.42),
    inset 1px 1px 3px rgba(77, 85, 99, 0.52);
}

input[type="radio"]:checked:after {
  width: 4px;
  height: 4px;
  border-radius: 15px;
  top: -2px;
  left: -1px;
  position: relative;
  background: #363a42;
  content: "";
  display: inline-block;
  visibility: visible;
  border: 5px solid #7930de;
  box-shadow: 2px 2px 5px rgba(8, 7, 13, 0.42),
    inset 1px 1px 3px rgba(77, 85, 99, 0.52);
}
.radio {
  margin-top: 25px;
  margin-right: 15px;
}
.actions {
  font-family: "Quicksand";
  font-style: normal;
  font-weight: 700;
  font-size: 14px;
  line-height: 18px;
  color: #ffffff;
  margin-top: 30px;
  margin-bottom: 24px;
}
.buttons-wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
}
.btn {
  color: #ffffff;
  width: 318px;
  height: 36px;
  padding: 0px 40px;

  /* buttonsShadow' */

  box-shadow: 2px 2px 7px rgba(11, 10, 13, 0.44), inset 1px 1px 4px #f1e7ff;
  border-radius: 30px;
  margin-bottom: 20px;
}
.active {
  background: linear-gradient(230.15deg, #9580ff 0%, #a361ff 92.48%);
}
.notactive {
  background: #b0aeb9;
}
</style>
