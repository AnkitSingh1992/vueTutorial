<template>
    <div>
        <h2>Volume tracker (0-20)</h2>
        <h2>Volume :- {{volume}}</h2>
        <button @click="volume = volume + 2">Increase</button> &nbsp;
        <button @click="volume = volume - 2">Decrease</button>
       
    </div>
    <hr/>
    <div>
      <!--Example of immediate while page loading-->
      <h2>{{movie}}</h2>
       <input type ="text" placeholder="Enter movie name" v-model ="movie"/>
       <!--Deep: true because watcher is not working for object and array -->
       <h2>{{movieInfo}}</h2>
       <input type ="text" placeholder="Enter movie name" v-model ="movieInfo.name"/>
       <input type ="text" placeholder="Enter movie actor" v-model ="movieInfo.actor"/>
      
       <h2>{{superHit}}</h2>
       <button @click="superHit.push('wonder women')">Add new superHit</button>
    </div>
</template>
<script>
export default {
    name:'Watcher-demo',
    data(){
       return {
         volume:0,
         movie:'Batman',
         movieInfo: {
              name:'',
              actor:''
          },
          superHit:['IronMan','Avenger']
       }
    },
    watch: {
      volume(newValue, oldValue){
        if(newValue> oldValue && newValue === 16) {
          alert("Your volume is more. Please decrease it.")
        }
      },      
      movie :{
        handler(newValue){
        console.log("movie", newValue)
        },
        immediate:true
      },
      movieInfo: {
        handler(){
          console.log("movie", this.movieInfo)
        },
        deep: true
      },
      superHit: {
        handler(){
          console.log("superHit", this.superHit)
        },
        deep: true

      }
    }
    
}
</script>