<template>
  <div id="notify">
    <div id="notification">1</div>
  </div>
</template>

<script>
export default {
    name: "NotiFy",
    props: {
        
    },
    components:{ }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#notify{
        position: absolute;
    right: 0;
    width: 50px;
    height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}
#notification{
    width: 15px;
    height: 15px;
    font-size: 0.7em;
    border-radius: 50%;
    background-color: dodgerblue;
    color: white; font-family: 'Segoe UI Variable Display';
    display: flex;align-items: center;justify-content: center;
}
</style>
