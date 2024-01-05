<script setup>
import { ref } from 'vue';
import FrameVue from './components/Frame.vue';

let name = ref('')
let imagePreview = ref(null)

function imageMove(event) {
  let file = event.target.files[0]
  if(file){
    const reader = new FileReader()
    reader.onload = ()=>{
      imagePreview.value = reader.result
    }
    reader.readAsDataURL(file)
  }
}

</script>

<template>

<div class="container">
    <div class="d-flex justify-content-center align-items-center gap-5 mainHeight">
      <div class="header">
          <h4>Convert HTML to Image using Vue.js 3 Component</h4>
      </div>
      <div class="input">
        <div class="mb-3">
          <label for="exampleFormControlInput1" class="form-label">Name</label>
          <input type="email" class="form-control" placeholder="name" v-model="name">
        </div>
        <div class="mb-3">
          <label for="exampleFormControlTextarea1" class="form-label">Picture</label>
          <input type="file" class="form-control" @change="imageMove">
        </div>
      </div>
      <FrameVue :name="name" :imagePreview="imagePreview"/>
    </div>
</div>

</template>

<style scoped>
.mainHeight{
  height: 100vh;
}

</style>

