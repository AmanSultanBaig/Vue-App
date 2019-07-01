<template>
    <div class="post-comment">
       <div class="card mb-3 bg-dark">
           <h1 class="container" style="color:white">Comments:</h1>
        <div class="card-body" v-for="(comment,index) in comments" :key="index">
            <div class="row no-gutters">
                    <div class="col-md-2">
                    <img src="@/assets/image.png" class="card-img" alt="">
                    </div>
                    <div class="col-md-10">
                    <div class="card-body">
                        <h5 class="card-title">{{comment.name}}</h5>
                        <p class="card-text">{{comment.body}}</p>
                        <p class="card-text"><small class="text-muted">{{comment.email}}</small></p>
                    </div>
                    </div>
                </div>
        </div>
    </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "PostComments",
    data: function(){
        return{
            id: this.$route.params.id,
            comments:[],
            error:[]
        }
    },
    created: function(){
     axios.get(`https://jsonplaceholder.typicode.com/comments?postId=${this.id}`)
     .then(res => {
       this.comments = res.data
     }).catch(e => {
       this.error.push(e)
     })
   }
}
</script>

<style>

img{
    height: 150px;
}

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
