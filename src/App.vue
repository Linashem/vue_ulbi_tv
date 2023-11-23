<template>
  <div class="wrapper">
    <p>IT WORKS</p>
    <form class="form">
      <h2>Create post</h2>
      <input class="input" type="text" placeholder="title" />
      <input class="input" type="text" placeholder="desc" />
      <button class="btn">ADD</button>
    </form>
    <div v-for="post in posts" :key="post.id" class="post">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        { id: 1, title: 'post 1', body: 'text of post 1' },
        { id: 1, title: 'post 2', body: 'text of post 2' },
        { id: 1, title: 'post 3', body: 'text of post 3' }
      ]
    };
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #3d3d3d;
}

.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  margin-top: 30px;
  gap: 50px;
}

.form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.input {
  width: 100%;
  padding: 10px 15px;
  border: 3px solid pink;
}

.btn {
  width: 100px;
  padding: 5px;
  border: 3px solid pink;
  background-color: pink;
  color: white;
  font-weight: 600;
}

.post {
  padding: 20px;
  width: 100%;
  border: 3px solid pink;
}
</style>
