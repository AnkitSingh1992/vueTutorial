<template>
 <div>
    <h1>API compostion</h1>
     <button class="btn btn-primary" @click="topic = 'data'">Replce Data with setup</button> 
     <button class="btn btn-primary" @click="topic = 'RefUpdate'">Addional Ref feature</button>
     <button class="btn btn-primary" @click="topic = 'ReactiveUpdate'">Additional ReactiveUpdate feature</button>
     <button class="btn btn-primary" @click="topic = 'MethodReplace'">Method Replace feature</button>
     <button class="btn btn-primary" @click="topic = 'Computed'">Computed Replace feature</button>
     <button class="btn btn-primary" @click="topic = 'Watch'">Watch Replace feature</button>
     <button class="btn btn-primary" @click="topic = 'Provide'">Provide And Inject</button>
     <button class="btn btn-primary" @click="topic = 'TemplateRefs'">Template Refs</button>
     <button class="btn btn-primary" @click="topic = 'Props'">Props</button>
     <button class="btn btn-primary" @click="topic = 'Composable'">Reuse though composable</button>
     <Data v-if="topic === 'data'"/>
     <RefUpdate v-if="topic === 'RefUpdate'"/>
     <ReactiveUpdate v-if="topic === 'ReactiveUpdate'"/>
     <Method v-if="topic === 'MethodReplace'"/>
     <Computed v-if="topic === 'Computed'"/>  
     <Watch v-if="topic === 'Watch'"/>
     <ProvideInject v-if="topic=== 'Provide'"/>
     <TemplateRefs v-if="topic === 'TemplateRefs'"/>
     <PropsParent v-if="topic === 'Props'"/>
     <Counter v-if="topic === 'Composable'"/>

 </div>
</template>

<script>
import { provide, ref,reactive } from 'vue';
import Data from './components/Data.vue';
import RefUpdate from './components/RefUpdate.vue';
import ReactiveUpdate from './components/ReactiveUpdate.vue';
import Method from './components/Method.vue';
import Computed from './components/Computed.vue';
import Watch from './components/Watch.vue';
import ProvideInject from './components/ProvideInject.vue';
import TemplateRefs from './components/TemplateRefs.vue';
import PropsParent from './components/PropsParent.vue';
import Counter from './components/Counter.vue';
export default {
  name: 'App',
  components: {
    Data,
    RefUpdate,
    ReactiveUpdate,
    Method,
    Computed,
    Watch,
    ProvideInject,
    TemplateRefs,
    PropsParent,
    Counter
},
 setup(){
    
    const count = ref(0);
    const profile = reactive({
       firstName:'Ankit',
       lastName:'Singh'
    })
    provide('userName','MyUser')
    provide('c_count',count)
    provide('profile',profile)

     const topic =  ref('data');
 
     return{
      topic
     }
 }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  margin:4px
}
</style>
