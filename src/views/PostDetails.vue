<template>
    <div class="post-details">
        <div class="card mb-3 bg-dark">
        <div class="card-body">
         <h1> Q{{post.id}}: {{post.title}}?</h1>
         <hr>
         <p><b>Ans</b>: {{post.body}}</p>
        </div>
    </div>
    <PostComments />
    </div>
</template>

<script>
import axios from 'axios'

import PostComments from './PostComments'

export default {
    name: "PostDetails",
    components:{
        PostComments
    },
    data: function(){
     return{
       id: this.$route.params.id,
       post: [],
     }
   },
   created: function(){
     axios.get(`https://jsonplaceholder.typicode.com/posts/${this.id}`)
     .then(res => {
       this.post = res.data
     }).catch(e => {
       this.error.push(e)
     })
   }
}
</script>

<style>

.card-body{
    color:white
}

hr{
   background-color: white
}

a{
    color: aqua
}


</style>
