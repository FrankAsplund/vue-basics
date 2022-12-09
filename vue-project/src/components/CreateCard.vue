<script>
import axios from "axios";

export default {
  name: "CreateCard",
  data() {
    return {
      formData: {
        title: "",
        text: "",
      },
    };
  },

  methods: {
    createCard() {
      axios
        .post("http://localhost:3000/posts", this.formData)
        .then((response) => console.log(response))
        .catch((error) => console.log(error));
    },
  },
};
</script>

<template>
  <div class="input-container">
    <form @submit.prevent="createCard">
      <div class="card-h1">Create a new post</div>
      <br />
      <input type="text" placeholder="Title" v-model="formData.title" />
      <br />
      <textarea cols="15" rows="5" placeholder="Text" v-model="formData.text">
      </textarea>
      <br />
      <button>Create new card</button>
    </form>
  </div>
</template>

<style scoped>
input {
  height: 20px;
  width: auto;
}

textarea {
  margin-top: 10px;
}

.input-container {
  padding: 10px;
  align-items: center;
  display: flex;
  justify-content: center;
  flex-direction: column;

  border-style: none;
  background-color: rgba(112, 128, 144, 0.14);
  border-radius: 10px;
  width: 300px;
  height: auto;
}
</style>
