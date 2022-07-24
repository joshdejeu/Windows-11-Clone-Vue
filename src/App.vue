<template>
  <div id="app">
    <BackGround @openWindow="createWindow"></BackGround>
    <taskbar @openWindow="createWindow"></taskbar>
  </div>
</template>

<script>
import BackGround from './components/BackGround.vue'
import taskbar from './components/TaskBar.vue'

export default {
  name: 'App',
  components: {
    BackGround,
    taskbar
  },
  methods:{
    createWindow(element){
      //dynamically creating pages on double clicks
      console.log(element)
      var wndow = document.createElement('div');
      var wndow_header = document.createElement('div');
      var wndow_header_min = document.createElement('div');
      var wndow_header_full = document.createElement('div');
      var wndow_header_exit = document.createElement('div');
      var wndow_text_input = document.createElement('textArea');
      wndow.id = "newWindow";
      wndow_header.id = "windowHeader";
      wndow_header_min.id = "headerMin"; wndow_header_min.innerHTML="-";
      wndow_header_full.id = "headerFull"; wndow_header_full.innerHTML="□"
      wndow_header_exit.id = "headerExit"; wndow_header_exit.innerHTML="x";
      wndow_text_input.id = "textInput";
      var pg = document.getElementById('app');
      wndow_header_min.className = "headerBtns"; wndow_header_full.className = "headerBtns"; wndow_header_exit.className = "headerBtns";
      wndow_header.append(wndow_header_min);//adding minimize button to header
      wndow_header.append(wndow_header_full);//adding full screen button to header
      wndow_header.append(wndow_header_exit);//adding exit button to header
      wndow.append(wndow_header);// adding header to window
      wndow.append(wndow_text_input);//adding text area to window
      pg.append(wndow);// adding window to page
      wndow_header_exit.addEventListener('click',function(){
        wndow.remove();
      });
    }
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
body,html{
  width: 100%;
  height: 100%;
}
body{
  position: relative;
  overflow: hidden;
}
#app{
    position: relative;
  display: flex;
  flex-direction: column;
}
#newWindow{
  width: 30vw;
  height: 50vh;
  border-radius: 10px;
  background: rgb(46, 46, 46);
  position: absolute;
  z-index: 2;
  top: 10%;
  left: 10%;
  display: flex; flex-direction: column
}
#windowHeader{
  width: 100%;
  height: 50px;
  background: rgb(27, 27, 27);
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  display: flex; justify-content: flex-end;
  font-family: 'Poppins',sans-serif;
}
.headerBtns:hover{
  background-color: rgba(255,255,255,0.1);
  user-select: none;
}
#headerMin{
  width: 35px;
  height: 100%;
  color: white;
  display: flex; justify-content: center; align-items: center;
}
#headerFull{
  width: 35px;
  height: 100%;
  color: white;
  display: flex; justify-content: center; align-items: center;
}
#headerExit{
  width: 35px;
  height: 100%;
  color: white;
  display: flex; justify-content: center; align-items: center;
}
#textInput{
  height: calc(100% - 50px);
  width: 100%;
  border: none; outline: none;
  background-color: transparent;
  color: white;
  padding: 10px;
  font-family: 'Consolas';
}
</style>
