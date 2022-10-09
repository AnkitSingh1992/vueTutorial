<template>
   <div>
    <hr/>
    <GalleryVue/>
     <h2>{{title}}</h2>
     <!-- Bind non props attribute -->
     <h4 v-bind="$attrs">{{likes}}</h4>
     <h4>{{isPublished ? 'Yes' : 'No'}}</h4>
   </div>
</template>

<script>
 import GalleryVue from './Gallery';
export default {
 name: "Article-component",
 components:{
    GalleryVue
 },
 props:{
    title: {
        type: String,
        required: true,
        default: 'Default Article'
    },
    likes: Number,
    isPublished: Boolean
 },
 inheritAttrs:false
}
</script>

<style>

</style>