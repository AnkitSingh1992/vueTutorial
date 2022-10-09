<template>
   <div>
     <h2>{{firstName}} {{lastName}}</h2>
      <!--Computed Properties--> 
     <h2>fullName - {{fullName}}</h2>
      <hr/>
      <button @click="items.push({id:'3',item:'screenCover', price:450})">Add Item</button>
     <h2>total - {{total}}</h2>
     <h2>Method total {{getTotal()}}</h2>

     <hr/>
       <!-- Computed setter example-->

       <h2> {{userFullName}}</h2>
        <button @click="changeName()">Change Name</button>
   </div>
</template>
<script>
export default {
    name:"ComputedProperties",
    data(){
        return {
            firstName: "Rahul",
            lastName: "Tiwari",
            userFirstname: "Ankit",
            userLastName:'Singh',
            items: [
                {
                    id:'1',
                    item:'keyboard',
                    price:300
                },
                {
                    id:'2',
                    item:'mouse',
                    price:200  
                }
            ]
        }
    },
    methods:{
        getTotal(){
            return this.items.reduce((total,item)=>(total =  total + item.price),0);
        },
        changeName(){
          
            this.userFullName = "Clint clark";
        }
    },
    computed:{
        fullName(){
            return `${this.firstName}  ${this.lastName}`;
        },
        total(){
            return this.items.reduce((total,item)=>(total =  total + item.price),0);
        },
        userFullName: {
            get(){
                return `${this.userFirstname}  ${this.userLastName}`;
            },
            set(value){
              console.log("value",value)
               const names = value.split(' ');
               this.userFirstname = names[0];
               this.userLastName = names[1];
            }
        }
    }
}
</script>