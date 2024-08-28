<script >
import axios from 'axios';
export default{
  name:'App',
  data(){
    return {
      posts:''
    }
  },

  mounted(){
    axios.get('http://127.0.0.1:8000/api/posts').then(result =>{
      console.log(result);
      this.posts=result.data.posts;
      console.log(this.posts);
    })
  }
}

</script>

<template>

 <div class="container">
  <div class="row d-flex">
    
    <div class="col text-light" v-for="post in posts.data">
      <div class="card">
        <div class="card-body"> {{ post.project_title }}</div>
       

      </div>
      
    </div>
  </div>
 </div>
</template>

<style scoped>

</style>
