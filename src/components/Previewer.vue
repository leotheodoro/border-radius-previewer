<template>
  <div class="main">
    <div class="box box-inputs box-top">
      <input type="number" class="input-border i-left" v-model="borderTopLeft" @change="changeBorder()">
      <input type="number" class="input-border i-right" v-model="borderTopRight" @change="changeBorder()">
    </div>
    <div class="box box-element"></div>
    <div class="box box-inputs box-bottom">
      <input type="number" class="input-border i-left" v-model="borderBottomLeft" @change="changeBorder()">
      <input type="number" class="input-border i-right" v-model="borderBottomRight" @change="changeBorder()">
    </div>
    <div class="box box-textarea">
      <textarea v-model="selection" class="form-control" id="selection" readonly cols="30" rows="10" @click="copyToClipboard()"></textarea>
      <button class="btn btn-primary btn-block" @click="copyToClipboard()">Copiar para área de transferência</button>
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
      selection: '',
    }
  },
  methods: {
    changeBorder() {
      this.borders = [this.borderTopLeft, this.borderTopRight,this.borderBottomRight, this.borderBottomLeft,''];
      let strBorders = this.borders.join('px ');
      strBorders = strBorders.trim();
      
      let box = document.getElementsByClassName('box-element')[0];
      box.style.borderRadius = strBorders;
      this.selection = `border-radius: ${strBorders};`;
    },
    copyToClipboard() {
      let textarea = document.getElementById('selection');

      textarea.select();
      textarea.setSelectionRange(0, 99999); // Para aplicativos móveis

      document.execCommand('copy');
    }
  },
}
</script>

<style>
.box {
  width: 400px;
  margin: auto;
}

.box-element {
  height: 200px;
  background-color: #2a2a72;
  background-image: linear-gradient(315deg, #2a2a72 0%, #009ffd 74%);
}

.box-textarea {
  margin-top: 20px;
}

.box-textarea textarea {
  width: 400px;
  background-color: #f5f5f5;
  resize: none;
  margin-bottom: 5px;
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