<template>
    <div class="post-list">
    <div class="card mb-3 bg-dark">
        <div class="card-body" v-for="item in posts" :key="item.id">
           <h1> <router-link :to="`/posts-details/${item.id}`"> Q: {{item.title}}? </router-link> </h1>
           <hr/>
           <p> <b>Ans:</b> {{item.body}}</p>
        </div>
    </div>

    <!-- div card for error  -->
    <div class="card mb-3 bg-dark" v-if="error && error.length">
        <div class="card-body">
           <p  v-for="(err,index) in error" :key="index"> {{err.message}}</p>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    name:"PostList",
    props: ['posts','error']
}
</script>

<style scoped>
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
