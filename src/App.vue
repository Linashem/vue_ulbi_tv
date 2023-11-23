<template>
  <div class="wrapper">
    <p>IT WORKS</p>
    <form class="form">
      <h2>Create post</h2>
      <input v-model="title" class="input" type="text" placeholder="title" />
      <input v-model="body" class="input" type="text" placeholder="desc" />
      <button @click.prevent="createPost" class="btn">ADD</button>
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
      ],
      title: '',
      body: ''
    };
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body
      };
      this.posts.push(newPost);
      this.title='',
      this.body=''
    }
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

:root {
  --border: 2px solid #778899;
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
  border: var(--border);
}

.btn {
  width: 100px;
  padding: 5px;
  border: var(--border);
}

.post {
  padding: 20px;
  width: 100%;
  border: var(--border);
}
</style>
