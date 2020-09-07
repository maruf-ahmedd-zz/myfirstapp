<template>
  <div class="single-post-page">
  <section class="post">
    <h1 class="post-title">{{ loadedPost.title }}</h1>
    <div class="post-details">
      <div class="post-detail">Last updated {{ loadedPost.updatedDate}}</div>
      <div class="post-detail">Written by Name{{ loadedPost.author}}</div>
    </div>
    <p class="post-content">Content of post{{ loadedPost.content }}</p>
  </section>
  <section class="post-feedback">
    <p>Let me know about the post, send mail to <a href="feedback@mail.com">feedback@mail.com</a></p>
  </section>
  </div>
</template>

<script>
export default {
  asyncData(context, callback) {
    setTimeout(() => {
      callback(null, {
        loadedPost: {
        id : "1", 
        title: "First Post(ID: " + context.route.params.id + ")", 
        previewText: "My first post", 
        author: "Nurjahan",
        updatedDate: new Date(),
        content:'Dummy text not the preview text',
        thumbnail: 'https://upload.wikimedia.org/wikipedia/commons/7/7c/Ahsan_Manzil_-_Dhaka.jpg' 
        }
      });
    }, 1000);
  }
}
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>