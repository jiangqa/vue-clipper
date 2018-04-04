<template>
  <div id="app">
    <cp ref="clipper" :img="img" :clipper-img-width="wd" :clipper-img-height="0.631*wd" @ok="ok"
        @cancel="cancel"></cp>
  </div>
</template>

<script>
import cp from './components/cp'
import img from './reactjs.png'
export default {
  name: 'App',
  data(){
    return{
      img:img,
      wd: 2 * 0.9 * document.documentElement.clientWidth,
    }
  },
  methods:{
    dataURLToBlob(dataurl){
      var arr = dataurl.split(',');
      var mime = arr[0].match(/:(.*?);/)[1];
      var bstr = atob(arr[1]);
      var n = bstr.length;
      var u8arr = new Uint8Array(n);
      while (n--) {
        u8arr[n] = bstr.charCodeAt(n);
      }
      console.log(new Blob([u8arr], {type: mime}))
      return new Blob([u8arr], {type: mime});
    },
    ok(data){
      dataURLToBlob(data)
    },
    cancel(){

    }
  },
  components: {
    cp
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
