<template>
  <div id="app">
    <img :src="require(`../assets/${this.imgsrc}`)" id="pcapp">
    <div id="appname">{{title}}</div>
  </div>
</template>

<script>
export default {
    name: "DesktopApp",
    props: {
        imgsrc: String,
        title: String,
    },
    components:{ },
    methods:{

    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#app{
    user-select: none;
    width: 60px;
    height: 80px;
    display: flex;justify-content: space-around;align-items: center;flex-direction: column;
}
#app:hover{
    background-color: rgba(255,255,255,0.2);
}
#app:active{
    background-color: rgba(255,255,255,0.5);
}
#pcapp{
    width: 65%;
}
#appname{
    font-family: 'Poppins', sans-serif;
    text-align: center;
    font-size: 0.7em;
}
</style>
