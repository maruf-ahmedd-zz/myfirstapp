<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :posts="loadedPosts" />
    </section>
  </div>
</template>

<script>

import AdminPostForm from '~/components/Admin/AdminPostForm'

export default {
  layout: 'admin',
  components: {
    AdminPostForm
  },
  data() {
    return {
      loadedPosts: {
        author: 'Tipu Sultan',
        title: 'Last Raj of Bharat',
        content: 'Man of honour',
        thumbnailLink: 'https://upload.wikimedia.org/wikipedia/commons/7/7c/Ahsan_Manzil_-_Dhaka.jpg'
      }
    }
  }
}
</script>