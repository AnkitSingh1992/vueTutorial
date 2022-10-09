<template>
  <div>
     <h4 v-if="errorMsg">{{errorMsg}}</h4>
     <!-- <button class="btn btn-success" @click="getPost()">Load Post</button> -->
    <br/> 
     <div class ="forms">        
      <form class="mb-6" @submit.prevent="createPost">
          <input class="form-control form-control-sm" type="text" placeholder="userId"  v-model="formData.userId"/>
          <input class="form-control form-control-sm" type="text" placeholder="tile"  v-model="formData.title"/>
          <input class="form-control form-control-sm" type="text" placeholder="body"  v-model="formData.body"/>
         <button  class="btn btn-primary">Submit</button><br/>
       </form>
     
    </div>
     
     <div v-for="post in posts" :key="post.id">
     <h4>{{post.title}}</h4>
     <p>{{post.body}}</p>
     <hr/>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name:"PostComponent",
  created(){
    this.getPost()
  },
  data(){
    return {
        posts:[],
        formData:{
            userId:'',
            title:'',
            body:''
        },
        errorMsg:'',
    }
  },
  methods: {
    getPost(){
    axios.get('https://jsonplaceholder.typicode.com/posts').then(response =>{
       this.posts = response.data;
       console.log(this.posts)
    }).catch(err=>{
     console.log(err)
     this.errorMsg = err;
    })
    },
    createPost(){
        axios.post('https://jsonplaceholder.typicode.com/posts',this.formData).then(response=>{
            console.log("response",response)
        }).catch(err=>{
            this.errorMsg = err;
        })
    }
  }

}
</script>

<style>
.forms{
    align-self: center;
    padding: 10px;
}
 
</style>