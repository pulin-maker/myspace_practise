<template>
  <div class="container">
    <div class="card">
      <div class="card-body">
        <div class="form-floating">
          <textarea v-model="content" class="form-control" placeholder="Leave a comment here" id="floatingTextarea2" style="height: 100px"></textarea>
          <label class="label_content" for="floatingTextarea2">请输入你今天摸鱼的内容: </label>
              <button @click="post_a_post" type="submit" class="btn btn-secondary btn-sm">Submit</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: "UserProfileWriteView",
  components: {},

  setup(props, context) {
    let content = ref('');

    const post_a_post = () => {
      context.emit('post_a_post', content.value);
      content.value = '';
    };

    return {
      content,
      post_a_post
    }
  }
};
</script>

<style scoped>
.container {
  margin-top: 15px;
}

.label_content {
  color: blue;
}

 button {
  margin-top: 10px;
} 
</style>
