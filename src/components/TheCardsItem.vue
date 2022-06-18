<template>
  <div class="box">
    <div class="box-flex">
      <h1>{{ fullData.name }}</h1>
      <p>{{ fullData.cli }}</p>
      <!-- TODO: поле популяции должно быть инпутом, в который можно ввести целое неотрицательное число -->
      <p v-if="showInput" @click="hidenInput">{{ fullData.pop }}</p>
      <p v-else @click="newinfoDabl">{{ this.newPopInfo }}</p>
      <input
        v-on:keyup.enter="displayNone"
        v-show="!showInput && hiden"
        @click="addNewPop"
        v-model="newPopInfo"
        @focus="hiden = true"
        @blur="hiden = false"
      />
    </div>
  </div>
</template>
<script>
export default {
  name: "TheCardsItem",
  data() {
    return {
      newPopInfo: [],
      showInput: true,
      hiden: true,
      focused: true,
    };
  },
  methods: {
    hidenInput() {
      this.showInput = !this.showInput;
      this.hiden = true;
    },
    addNewPop() {
      this.newInfo = [];
    },
    displayNone() {
      this.hiden = !this.hiden;
    },
    newinfoDabl() {
      this.newPopInfo = [];
      this.hiden = !this.hiden;
    },
  },
  props: {
    fullData: {
      type: Object,
      default: null,
    },
  },
};
</script>
<style scoped>
.box {
  display: inline-flex;
  margin: 15px;
  border: 1px solid red;
  width: 200px;
  padding: 10px;
}

.box-flex {
  margin: 0 auto;
  justify-self: row;
}
</style>