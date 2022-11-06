<template>
  <div id="taskbar">
    <TaskApp imgsrc="windowslogo.png" @dblclick.native="dbClickApp($event)" @click.native="menuMove"></TaskApp>
    <TaskApp imgsrc="chromelogo.png" @dblclick.native="dbClickApp($event)"></TaskApp>

    <TaskApp imgsrc="notepad.png" @dblclick.native="dbClickApp($event)"></TaskApp>
    <TaskApp imgsrc="discord.png" @dblclick.native="dbClickApp($event)"></TaskApp>
    <div id="startMenu">
      <div id="menu_search">
        <div id="menu_search_icon"></div>
        <input type="text" id="menu_search_input" placeholder="Type here to search">
      </div>

    </div>

    <ActionCenter></ActionCenter>    
    <NotiFy></NotiFy>
  </div>
</template>

<script>
import TaskApp from './TaskApp.vue'
import ActionCenter from './ActionCenter.vue'
import NotiFy from './NotiFy.vue'

export default {
    name: "TaskBar",
    props: {
        
    },
    data(){
      return{
        startMenuActive: false,
      }
    },
    components:{ TaskApp, ActionCenter, NotiFy },
    methods:{
        dbClickApp(appEvent){
            var appClicked = appEvent.path[0];
            // console.log(appEvent)
            //Emit to background so it can open page there
            this.$emit('openWindow', appClicked);
        },
        menuMove(){
          var menu = document.getElementById('startMenu');
          if(this.startMenuActive==false){
            this.startMenuActive=true;
            menu.style.bottom = "60px";
          }else{
            this.startMenuActive=false;
            menu.style.bottom = "-70vh";
          }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#taskbar{
    position: relative;
  margin-top: -5px;
  width: 100%;
  height: 50px;
  background-color: #d6dcec;
  display: flex;
  align-items: center;
  justify-content: center;
}
#startMenu{
  position: absolute;
  width: 50vw;
  max-width: 600px;
  height: 70vh;
  background: linear-gradient(45deg,#d6dcec,#e0e9fd);
  bottom: -72vh;
  transition: 0.2s ease;
  border-radius: 20px;
  display: flex;
  justify-content: center;
}
#menu_search{
  width: 80%;
  height: 50px;
  background-color: white;
  border-radius: 2px;
  margin-top: 50px;
  display: flex;
  position: relative;
}
#menu_search::after{
  content: '';
  width: 100%;
  height: 2px;
  background-color: rgb(35, 141, 212);
  bottom: 0;
  left: 0;
  position: absolute;
}
#menu_search_icon{
  width: 15%;
  background-image: url('../assets/searchicon.png');
  filter: brightness(0%);
  transform: rotateY(180deg);
  background-size: 30%;
  background-repeat: no-repeat;
  background-position: center;
  height: 100%;
}
#menu_search_input{
  border: none;
  outline: none;
  width: 85%;
  height: 100%;
  display: flex;justify-content: center;align-items: center;
  padding-right: 10px;
  font-family: 'Segoe UI Variable Display';
  font-size: 1em;
}
</style>
