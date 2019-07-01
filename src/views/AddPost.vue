<template>
    <div class="add-post">
        <button class="btn btn-primary mb-3" @click="showForm">Create Post</button>
      <div class="card bg-dark mb-3" v-if="formDiv">
        <div class="card-body">
            <form @submit.prevent="addPost">

                <div class="form-group">
                <label>Post Title:</label>
                <input v-model="title" type="text" name="title" class="form-control" placeholder="Enter Post Title">
            </div>
            <div class="form-group">
                <label>Post Description:</label>
                <textarea v-model="body" type="text" class="form-control" name="body" placeholder="Enter Post Description"></textarea>
            </div>
            <div class="form-group">
                <button class="btn btn-success">Add Post Now</button>
            </div>

            </form>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    name: 'AddPost',
    data: function(){
       return{
            formDiv: false,
            title: '',
            body: ''
       }
    },
    methods:{
        showForm: function(){
            this.formDiv = true
        },
        addPost: function(){
           const newPost = {
               title: this.title,
               body: this.body
           };
           this.$emit('add-post',newPost);
           this.formDiv = false
        }
    }
}
</script>


<style scoped>
.card-body{
    color:white
}

</style>
