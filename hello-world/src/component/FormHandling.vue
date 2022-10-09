<template>
  <div>  

    <!-- additonal  modifier v-once, v-pre-->
     <h2 v-once>{{name}}</h2>
      <button @click="name = 'Roshan'">Change Name</button>
   
     <h2 v-pre>{{name}}</h2>
     <hr/>
    <h2>Job descriprion form</h2>
    {{JSON.stringify(formValues, null, 2)}}   
    <form @submit.prevent="submitForm">
     <!--text box -->
     <!--Adding modifier trim and lazy in v-model directive-->
    <div class="mb-3 row">
        <label for="name" class="col-sm-2 col-form-label">Name</label>
        <div class="col-sm-5">
           <input type="text" v-model.trim.lazy = "formValues.name" class="form-control" id="name" placeholder="name"/>
        </div>
    </div>

    <!--text area-->
    <!-- adding the key  event by  using enter  modifier -->
    <div  class="mb-3 row">
        <label for="name" class="col-sm-2 col-form-label">Profile Summary</label>
        <div class="col-sm-5">
            <textarea @keyup.enter="message " class="form-control"  v-model = "formValues.profileSummary" id="profileSummary" placeholder="profile Summary"></textarea>
        </div>
    </div>

     <!--single selection-->
    <div class="mb-3 row">
       <label for="name" class="col-sm-2 col-form-label">Country</label>
       <div class="col-sm-5">
            <select class="form-select" aria-label="Default select example" v-model="formValues.country">
            <option selected>Choose Country</option>
            <option value="India">India</option>
            <option value="Australia">Australia</option>
            <option value="Germany">Germany</option>
           </select>
        </div>
    </div>

    <!--multi selection-->
    <div class="mb-3 row">
       <label for="job-location" class="col-sm-2 col-form-label">Job location</label>
       <div class="col-sm-5">
            <select multiple class="form-select" aria-label="Default select example" v-model="formValues.joblocation">
            <option selected>Choose Country</option>
            <option value="India">India</option>
            <option value="Australia">Australia</option>
            <option value="Singapore">Singapore</option>
           </select>
        </div>
    </div>
    <!--check box -->
    <div class="mb-3 row">
        <div class="col-sm-5">
            <input class="form-check-input" type="checkbox"  v-model="formValues.remoteWork" id="remotework" true-value="YES" false-Value="NO">
            <label for="remptework" class="col-sm-5 col-form-label">Open to remote work?</label>
        </div>
    </div>

    <!-- MultiCheck box-->
    <div class="mb-3 row">
        <label for="skillSet" class="col-sm-2 col-form-label">Skill Set</label>
        <div class="col-sm-2">
            <input class="form-check-input" type="checkbox" value="HTML"  v-model="formValues.skillSet" id="html">
            <label for="html" class="col-sm-5 col-form-label">HTML</label>
        </div>
        <div class="col-sm-2">
            <input class="form-check-input" type="checkbox" value="CSS"  v-model="formValues.skillSet" id="html">
            <label for="css" class="col-sm-5 col-form-label">CSS</label>
        </div>

        <div class="col-sm-2">
            <input class="form-check-input" type="checkbox" value="JAVASCRIPT"  v-model="formValues.skillSet" id="html">
            <label for="JAVASCRIPT" class="col-sm-5 col-form-label">JAVASCRIPT</label>
        </div>
    </div>

    <!--Radio group-->

    <div class="mb-3 row">
        <label for="skillSet" class="col-sm-2 col-form-label">Year Of Experience</label>
        <div class="col-sm-2">
            <input class="form-check-input" type="radio" value="0-2"  v-model="formValues.yearofExperience" id="0-2">
            <label for="0-2" class="col-sm-5 col-form-label">0-2</label>
        </div>
        <div class="col-sm-2">
            <input class="form-check-input" type="radio" value="2-4"  v-model="formValues.yearofExperience" id="2-4">
            <label for="2-4" class="col-sm-5 col-form-label">2-4</label>
        </div>

        <div class="col-sm-2">
            <input class="form-check-input" type="radio" value="4-above"  v-model="formValues.yearofExperience" id="4-above">
            <label for="4-above" class="col-sm-5 col-form-label">4-above</label>
        </div>
    </div>

    <!-- Adding modifier number in v-model directive -->
    <div class="mb-3 row">
        <label for="age" class="col-sm-2 col-form-label">Age</label>
        <div class="col-sm-5">
           <input type="number" v-model.number = "formValues.age" class="form-control" id="age" placeholder="age"/>
        </div>
    </div>

    <button type="submit" class="btn btn-primary">Submit</button>
   </form>
</div>
</template>
<script>
export default {
  name: "FormHandling",
  data(){
     return {
        name:"Ankit",
        formValues:{
        name: '',
        profileSummary:'',
        country:'',
        joblocation:[],
        remoteWork:"NO",
        skillSet: [],
        yearofExperience:"",
        age:null
    }
     } 
  },
  methods:{
    submitForm(event){
       // event.preventDefault()
       console.log(event)
        console.log("Submit data :: {}",JSON.stringify(this.formValues))
    },
    message() {
      alert("Listening..")
    }
  }

};
</script>
<style>

</style>