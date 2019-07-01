<template>
  <div class="home">
      <AddPost v-on:add-post="addPost"/>
      <PostList v-bind:posts="posts" v-bind:error="error"/>
  </div>
</template>

<script>
import axios from 'axios'
// @ is an alias to /src
import PostList from './PostList'
import AddPost from './AddPost'
export default {

  name: 'home',
  components: {
    PostList,
    AddPost
   },
   data: function(){
     return{
       posts: [],
       error: []
     }
   },
   methods:{
     addPost:function(newPost){
       const {title, body} = newPost;
       axios.post('https://jsonplaceholder.typicode.com/posts',{
         title,
         body
       })
       .then(res => {
         this.posts = [...this.posts, res.data]
        })
       .catch(err => console.log(err))
     }
   },
   created: function(){
     axios.get('https://jsonplaceholder.typicode.com/posts?_limit=4')
     .then(res => {
       this.posts = res.data
     })
     .catch(e => {
       this.error.push(e)
     })
   }
}
</script>
