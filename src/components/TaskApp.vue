<template>
  <div id="taskapp">
    <img :src="require(`../assets/${this.imgsrc}`)" id="appimg" alt="start">
  </div>
</template>

<script>
export default {
  name: 'TaskApp',
  props: {
    imgsrc: String,
  },
  components:{
    
  },
  data(){
    return{
        newSrc: `require('${this.imgsrc}')`,
    }
  },
  methods:{

  },
  mounted(){
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#taskapp{
    user-select: none;
  height: 45px;
  width: 45px;
  margin-right: 3px;
  border-radius: 5px;
  /* background-color: red; */
  transition: 0.2s ease;
  display: flex;justify-content: center;align-items: center;
}
#taskapp:active{
  transform: scale(0.7);
  padding: 10px;
  margin: 0;
}
#taskapp:hover{
    background-color: rgba(0,0,0,0.1);
}
#appimg{
    width: 60%;
    height: 60%;
}
</style>
