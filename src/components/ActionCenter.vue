<template>
  <div id="actioncenter">
    <div id="time" class="times">{{time}}</div>
    <div id="date" class="times">{{date}}</div>
  </div>
</template>

<script>
export default {
    name: "ActionCenter",
    props: {
        
    },
    components:{

    },
    data(){
        return{
            time: "",
            date: "",
        }
    },
    methods:{
        getTime(){
            const dt = new Date();
            this.date = `${dt.getMonth()+1}/${dt.getDate()}/${dt.getFullYear()}`;
            var hr = dt.getHours();
            if(hr==0){hr=12;}
            if(hr>11){am="PM";}
            if(hr==24){am="AM";}
            if(hr>12){hr-=12;}
            var mn = dt.getMinutes();
            if(mn.toString().length<2){mn="0"+mn;}
            var am = "AM";
            this.time = `${hr}:${mn} ${am}`;
        },
        getDate(){

        }
    },
    mounted(){
        //On page load, update time ever 5 sec
        this.getTime();
        setTimeout(() => {
            this.getTime();
        }, 5000);
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#actioncenter{
user-select: none;
  width: 100px;
  height: 100%;
  position: absolute;
  right: 50px;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  flex-direction: column;
  padding-right: 10px; padding-left:0px;
}
#actioncenter:hover{
    background-color: rgba(255,255,255,0.2);
}
.times{
    font-family: 'Segoe UI Variable Display';
}
</style>
