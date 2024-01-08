<template>
<!-- id="mynode"
    <img v-show="props.imagePreview" :src="props.imagePreview" class="card-img-top" alt="..."> -->

<figure id="mynode" class="snip1113"><img v-show="props.imagePreview" :src="props.imagePreview" alt="...">
  <figcaption>
    <h3><span>{{ name }}</span></h3>
    <h4>
      Creator
    </h4>
  </figcaption>
</figure>

    <a @click="snapshot" class="btn btn-dark">Download</a>
</template>
  
  <script setup>
  import html2canvas from 'html2canvas';
   const props = defineProps({
    name : String,
    imagePreview : String,
   })

   function snapshot(){
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

@import url(https://code.ionicframework.com/ionicons/2.0.1/css/ionicons.min.css);
figure.snip1113 {
  font-family: 'Raleway', Arial, sans-serif;
  position: relative;
  overflow: hidden;
  margin: 10px;
  min-width: 220px;
  max-width: 310px;
  width: 100%;
  background: #ffffff;
  text-align: center;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.15);
}

figure.snip1113 * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}

figure.snip1113 img {
  max-width: 65%;
  margin: 40px auto;
  display: block;
  position: relative;
  border: 3px solid #666666;
  padding: 15px 15px 85px 15px;
  -webkit-transform: translate(0, 0);
  transform: translate(0, 0);
}

figure.snip1113 figcaption {
  position: absolute;
  height: 120px;
  bottom: 0px;
  left: 0;
  right: 0;
  display: block;
}

figure.snip1113 h3 {
  background-color: #ffffff;
  color: #000000;
  font-size: 1.7em;
  width: 100%;
  padding: 5px 12px;
  margin: 0;
  text-transform: uppercase;
  font-weight: 400;
}

figure.snip1113 h3 span {
  font-weight: 800;
}

figure.snip1113 h4 {
  margin: 0;
  text-transform: uppercase;
  letter-spacing: -1px;
  opacity: 0.6;
  font-size: 1.1em;
}

figure.snip1113.blue img {
  border-color: #2472a4;
}

figure.snip1113.blue h3,
figure.snip1113.blue h4 {
  color: #2472a4;
}

figure.snip1113.red img {
  border-color: #ab3326;
}

figure.snip1113.red h3,
figure.snip1113.red h4 {
  color: #ab3326;
}

figure.snip1113.yellow img {
  border-color: #e08e0b;
}

figure.snip1113.yellow h3,
figure.snip1113.yellow h4 {
  color: #e08e0b;
}

figure.snip1113.green img {
  border-color: #229955;
}

figure.snip1113.green h3,
figure.snip1113.green h4 {
  color: #229955;
}

figure.snip1113.orange img {
  border-color: #d67118;
}

figure.snip1113.orange h3,
figure.snip1113.orange h4 {
  color: #d67118;
}

figure.snip1113.navy img {
  border-color: #2b3c4e;
}

figure.snip1113.navy h3,
figure.snip1113.navy h4 {
  color: #2b3c4e;
}


  </style>