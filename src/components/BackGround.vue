<template>
  <div class="background">
    <div id="wallpaper">
      <DesktopApp imgsrc="trash.png" title="Recyle" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="chromelogo.png" title="Google Chrome" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="notepad.png" title="Notepad" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="discord.png" title="Discord" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="chromelogo.png" title="Google Chrome" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="chromelogo.png" title="Google Chrome" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="chromelogo.png" title="Google Chrome" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="chromelogo.png" title="Google Chrome" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
      <DesktopApp imgsrc="chromelogo.png" title="Google Chrome" @click.native="clickedApp" @dblclick.native="dbClickApp($event)"></DesktopApp>
  
    </div>
  </div>
</template>

<script>
import DesktopApp from './DesktopApp.vue';
export default {
    name: "BackGround",
    props: {},
    components: { DesktopApp },
    methods:{
        clickedApp(){
          //do code here
        },
        dbClickApp(appEvent){
          var appClicked = appEvent.path[0];
          // console.log(appEvent)
          //Emit to background so it can open page there
          this.$emit('openWindow', appClicked);
        },
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#newWindow{
  width: 500px;
  height: 300px;
  background-color: greenyellow;
}
.background{
  width: 100%;
  height: 90%;
  position: relative;
}
#wallpaper{
  height: calc(100vh - 50px);
  width: 100%;
  background-image: url('../assets/wallpaper.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
</style>
