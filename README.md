# Html To Image Convert using vue.js 3

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/)

### Step 1: Start Application server Vue 3

```
npm install
npm run dev
```
### Step 2: How To Install html2pdf

```
npm install html2canvas
```
### Step 3: Image Preview Code

```
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
```

### Step 4: How To import html2pdf

```
import html2canvas from 'html2canvas';
```

### Step 5: Main Html To Image code

```
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

```

