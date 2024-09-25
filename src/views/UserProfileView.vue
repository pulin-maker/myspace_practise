<template>
  <ContentBaseView>
    <div class="row">
      <div class="col-3">
        <UserProfileInfo :user="user" @follow="follow" @unfollow="unfollow" />
      </div>
      <div class="col-9">
        <UserProfilePostView :posts="posts" />         
      </div>
    </div>
  </ContentBaseView>

  <div class="container">
    <div class="row">
      <div class="col-3"></div>
      <div class="col-9"></div>
    </div>
  </div>
</template>

<script>
import UserProfilePostView from '../components/UserProfilePostView.vue'
import ContentBaseView from '../components/ContentBaseView.vue'
import UserProfileInfo from '../components/UserProfileInfoView.vue'
import { reactive } from 'vue'

export default {
  name: 'UserProfileView',
  components: {
    ContentBaseView,
    UserProfileInfo,
    UserProfilePostView,
  },
  setup() {
    const user = reactive({
      id: 1,
      username: "Chubao",
      firstName: "Bao",
      lastName: "Chu",
      is_followed: false,
      followerCount: 0
    });

    const posts = reactive({
      count: 3,
      post: [
        {
          id: 1,
          userId: 1,
          content: "今天是美好的一天",
        },
        {
          id: 2,
          userId: 2,
          content: "今天还是需要学习",
        },
        {
          id: 3,
          userId: 1,
          content: "今天必须要看书啊！",
        }
      ]
    })

    const follow = () => {
        if (user.is_followed) return ;
        user.is_followed = true;
        user.followerCount ++ ;
    }

    const unfollow = () => {
        if (!user.is_followed) return ;
        user.is_followed = false;
        user.followerCount -- ;
    }

    return {
      user,
      follow,
      unfollow,
      posts
    }
  }
}
</script>
