<template>
<div class="card">
  <div class="card-body">
    <div class="content-part" v-for="post in posts.post" :key="post.id">
      <div class="card">
        <div class="card-body">
          {{ post.content }}
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script>
export default {
    name: "UserProfilePostView",
    props: {
      posts: {
        type: Object,
        required: true
      }
    },

}
</script>

<style scoped>
.container {
  margin-top: 15px;
}

.content-part {
  margin-bottom: 10px;
}
</style>
