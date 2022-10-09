<template>
    <div>
         <!-- Render array of  string -->
        <h2 v-for="(name,index) in names" :key="name">{{index}}  {{name}}</h2>
        
        <!--Render array  of object-->
        <h2 v-for="name in fullNames" :key="name.firstName">{{name.firstName}} {{name.lastName}}</h2>
         <div v-for="actor in actors" :key="actor.name">
           <h2>{{actor.name}}</h2>
           <h4 v-for="movie in actor.movies" :key="movie">{{movie}}</h4>
        </div>

        <!--Rendering property -->
        <div>
            <h2 v-for="(value,key, index) in myInfo" :key="value">{{index}} {{key}} : {{value}}</h2>
        </div>

        
        <!-- Rendering array by template tag-->
         <div v-for="name in names" :key="name">
            <h2>{{name}}</h2>
            <input placeholder="Last Name"/>
            <hr/>
         </div>
         <!-- we have to  use  key -->
         <button @click="shuffle">Suffle!</button>

         <!--Conditional rendering-->
          <h2 v-for="name in names" :key="name">
         <span v-if="name === 'Brush'">{{name}}</span>
          </h2>

      </div>
</template>
<script>
    import _ from "lodash"
export default {
    name: "ListRendering",
    data(){
        return{
            names: ["Brush", "Dyana" , "Clark"],
            fullNames:[
                {"firstName":"Brush" , "lastName":"Wyane"},
                {"firstName":"Clark", "lastName":"Robert"}
            ],
            actors:[
                 {
                    name:"Rajkumar",
                    movies:["kapuche","ChinaTown"]
                 },
                 {
                    name: "Ayshman",
                    movies: ["BadayeeHo", "NautankiSala"]
                 }
            ],
            myInfo:{
                channel: "hotstar",
                owner: "star"
            }
        }
    },
    methods: {
        shuffle() {
            console.log(this.names);
            this.names = _.shuffle(this.names);
        }
    }
}
</script>