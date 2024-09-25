<template>
  <div class="container">
    <div class="card">
      <div class="card-body">
        <div class="row">
          <div class="col-3">
            <img src="../assets/logo.jpg" class="img-fluid" alt="" />
          </div>
          <div class="col-9">
            <div class="username">{{ fullName }}</div>
            <div class="fans">Followers: {{ user.followerCount }}</div>
            <button v-if="!user.is_followed" @click="follow" type="button" class="btn btn-dark btn-sm my-button">
              + Like
            </button>
            <button v-if="user.is_followed" @click="unfollow" type="button" class="btn btn-dark btn-sm my-button">
              - DisLike
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'

export default {
  name: "UserProfileInfo",
  props: {
    user: {
        type: Object,
        required: true,
    }
  },
  setup(props, context) {
    let fullName = computed(() => props.user.lastName + ' ' + props.user.firstName);

    const follow = () => {
        context.emit('follow')
    }

    const unfollow = () => {
        context.emit('unfollow');
    }

    return {
        fullName,
        follow,
        unfollow
    }
  },
};
</script>

<style scoped>
img {
  border-radius: 50%;
}

.username {
    font-weight: bold;
}

.fans {
  font-size: 18px;
  color: gray;
}

button {
  margin-top: 10px;
  font-size: 18px;
}
</style>
