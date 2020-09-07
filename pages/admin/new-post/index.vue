<template>
  <div class="admin-new-post-page">
    <section class="new-post-form">
    </section>
    <AdminPostForm @submit="onSubmitted"/>
  </div>
</template>

<script>
import axios from 'axios'
import AdminPostForm from '~/components/Admin/AdminPostForm'

export default {
  layout: 'admin',
  components: {
    AdminPostForm
  },
  methods: {
    onSubmitted(postData) {
      axios.post('https://first-nuxt-app-29ede.firebaseio.com/posts.json', postData)
      .then(result => console.log(result))
      .catch(e => console.log(e))
    }
  }
};
</script>