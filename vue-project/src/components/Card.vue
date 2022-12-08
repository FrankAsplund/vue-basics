<script>
/* import Delete from "./Delete.vue"; */
export default {
  /* components: {
    Delete,
  }, */
  name: "Card",
  props: {
    title: {
      type: String,
    },
    text: {
      type: String,
    },
    cardImg: {
      type: Image,
    },
    cardText: {
      type: String,
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="card-container">
        <h1 class="card-h1"> {{post.id}}</h1>
      <div class="card-title">{{ post.title }}</div>
     <!--  <img class="card-img">{{ post.img }} -->
      <div class="card-text">{{ post.text }}</div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: grid;
  float: left;
  margin: 10px;
  /* justify-content: flex-start;
  align-items: center; */
}
.card-container {
    
  margin: 10px;
  padding: 10px;
  align-items: center;
  display: flex;
  flex-direction: column;


  border-style: none;
  background-color: rgba(112, 128, 144, 0.14);
  border-radius: 10px;
  width: 400px;
  height: 300px;
}
.card-container:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
}
.card-title {
  font-size: 15px;
  margin-right: 10px;
}

.card-img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 200px;
  height: 200px;
}

.track-button {
  font-size: 15px;
  font-weight: bold;
  background-color: rgb(255, 0, 0);
  border-style: none;
  border-radius: 10px;
  height: 30px;
  width: 80px;
  align-items: center;
  margin-left: 20px;
  margin-top: 10px;
}
</style>