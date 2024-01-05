<template>
    <div id="mynode" class="card" style="width: 18rem;">
    <img v-show="props.imagePreview" :src="props.imagePreview" class="card-img-top" alt="...">
    <div class="card-body">
        <p class="card-text">কখনো ভেঙে পড়ো না । পৃথিবীতে যা কিছু হারিয়ে যায় , অন্য কোন রূপে সেটি ঠিকই আবার ফিরে আসে জীবনে - <span class="smallText text-warning">{{ props.name }}</span></p>
    </div>
    </div>
    <a @click="downloa" class="btn btn-dark">Download</a>
</template>
  
  <script setup>
  import html2canvas from 'html2canvas';
   const props = defineProps({
    name : String,
    imagePreview : String,
   })

   function downloa(){
    let rand = Math.random() * 100
    let mynode = document.getElementById('mynode')
    html2canvas(mynode).then((canvas)=>{
        const baseImage = canvas.toDataURL('image/png')
        let ancor = document.createElement('a')
        ancor.setAttribute('href',baseImage)
        ancor.setAttribute('download',`${rand}.png`)
        ancor.click()
        ancor.remove()

    })
   }
  </script>
  
  <style scoped>
  .smallText{
    font-size: 12px;
  }
  </style>