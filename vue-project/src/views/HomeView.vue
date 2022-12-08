<script>
import Card from "../components/Card.vue";
import CreateCard from "../components/CreateCard.vue";
export default {
  components: {
    Card,
    CreateCard
},

  data() {
    return {
      posts: []
      }
    },

    mounted() {
      fetch("http://localhost:3000/posts")
      .then(res => res.json())
      .then(data => this.posts = data)
      .catch(err => console.log(err.message))
    }
  }
</script>

<template>
  
  <div class="home">

    <div class="home-container">
      
      <h1>Test Home</h1>
      <p> Lorem ipsum dolor sit amet consectetur, adipisicing elit. 
        Dolorem, voluptates. Iusto temporibus animi deleniti. 
        Praesentium rem consectetur numquam debitis quidem quam recusandae assumenda, 
        consequuntur eligendi, dolorem optio officiis iure dignissimos.</p>
    </div>

    <div class="center">
      <CreateCard />
    </div>

      <div v-for="post in posts" :key="post.id" class="container">
        
        <div class="card-container">
          <h1 class="card-h1"> {{post.id}}</h1>
      <div class="card-title">{{ post.title }}</div>
      <div class="card-text">{{ post.text }}</div>
    </div>
    
    
    
  </div>

  </div>


    
</template>

<style scoped>

.center {
  display: flex;
  justify-content: center;
}

.home {
  position: absolute;
  top: 5rem;
  padding: 1rem;
}

h1 {
  display: flex;
  justify-content: center;
}


.home-container {
  position: relative;
  margin: 3rem 0 3rem 0;
}

.card-container1 {
  margin: 5rem 0 0 0;
}

.container-all {
  display: grid;
  float: left;
  margin: 10px;
}

.container {
  display: grid;
  float: left;
  margin: 10px;
  /* justify-content: flex-start;
  align-items: center; */
}
.card-container {
    
  padding: 10px;
  align-items: center;
  display: flex;
  flex-direction: column;


  border-style: none;
  background-color: rgba(112, 128, 144, 0.14);
  border-radius: 10px;
  width: 300px;
  height: 250px;
}

.card-container:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
}
.card-title {
  font-size: 20px;
  margin-right: 10px;
}

.card-text {
  padding: 10px;
  border: solid 0.3px rgba(#ddd, 0.6);
  border-radius: 10px;
  overflow: auto;
}

.card-img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 200px;
  height: 200px;
}

/* width */
::-webkit-scrollbar {
  overflow-x: hidden;
  width: 10px;
}
 
/* Handle */
::-webkit-scrollbar-thumb {
  background: #888; 
  size: 3px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555; 
}

</style>