<script>
import axios from "axios";
import Card from "../components/Card.vue";
import CreateCard from "../components/CreateCard.vue";

export default {
  components: {
    Card,
    CreateCard,
  },

  data() {
    return {
      posts: [],
    };
  },

  methods: {
    getPosts() {
      axios
        .get("http://localhost:3000/posts")
        .then((response) => {
          console.log(response.data);
          this.posts = response.data;
        })
        .catch((error) => {
          console.log(error.message);
        });
    },

    /* Deletes an entry in the database */
    deleteData(id) {
      axios
        .delete(`http://localhost:3000/posts/${id}`)
        .then((response) => {
          console.log(response);
          this.posts = response.data;
        })
        .catch(function (error) {
          console.log(error.response);
        });
    },
  },

  mounted() {
    console.log("mounted");
    axios
      .get("http://localhost:3000/posts")
      .then((data) => (this.posts = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<template>
  <div class="home">
    <h1>Posts</h1>
    <div class="home-container">
      <p>
        Create a new post by writing a title, and add text in the input fields.
        Submit the post by pressing the submit button.
      </p>
      <CreateCard />
      <button class="card-button" @click="getPosts">Load Posts</button>
    </div>

    <div v-for="post in posts" :key="post.id" class="container">
      <div class="card-container">
        <h1 class="card-h1">{{ post.id }}</h1>
        <div class="card-title">{{ post.title }}</div>
        <div class="card-text">{{ post.text }}</div>
        <button class="card-button" @click="deleteData(post.id)">
          Delete post
        </button>
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

.home-container > p {
  height: 100px;
  width: 300px;
}

.card-button {
  align-items: center;
  margin-top: 1rem;
  font: bolder;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
  padding: 5px;
  width: 11rem;
  height: 2rem;
  border-radius: 25px;
  background-color: hsla(160, 100%, 37%, 0.2);
}

.card-button:hover {
  background-color: rgba(255, 255, 255, 0.6);
}

.home-container {
  display: flex;
  flex-direction: column;
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
  transition: 0.4s ease-in-out;
}
.card-title {
  font-size: 20px;
  margin: 10px 0 5px 0;
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
