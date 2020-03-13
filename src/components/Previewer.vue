<template>
  <div class="main">
    <div class="box-inputs box-top">
      <input type="number" class="input-border i-left" v-model="borderTopLeft" @change="changeBorder()">
      <input type="number" class="input-border i-right" v-model="borderTopRight" @change="changeBorder()">
    </div>
    <div class="box"></div>
    <div class="box-inputs box-bottom">
      <input type="number" class="input-border i-left" v-model="borderBottomLeft" @change="changeBorder()">
      <input type="number" class="input-border i-right" v-model="borderBottomRight" @change="changeBorder()">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      borderTopLeft: 0,
      borderTopRight: 0,
      borderBottomLeft: 0,
      borderBottomRight: 0,
      borders: [],
    }
  },
  methods: {
    changeBorder() {
      this.borders = [this.borderTopLeft, this.borderTopRight, this.borderBottomLeft, this.borderBottomRight, ''];
      let strBorders = this.borders.join('px ');
      
      let box = document.getElementsByClassName('box')[0];
      console.log(box);
      box.style.borderRadius = strBorders;
    }
  },
}
</script>

<style>
.box {
  width: 400px;
  height: 200px;
  background-color: #aaa;
  margin: auto;
}

.box-inputs {
  width: 400px;
  margin: auto;
}

.box-top {
  margin-bottom: 5px;
}

.box-bottom {
  margin-top: 5px;
}

.i-right {
  float: right;
}

.input-border {
  width: 100px;
}
</style>