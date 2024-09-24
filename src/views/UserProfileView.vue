<template>
  <ContentBaseView>
    <div class="row">
      <div class="col-3">
        <UserProfileInfo />
      </div>
      <div class="col-9">

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
import ContentBaseView from '../components/ContentBaseView.vue'
import UserProfileInfo from '../components/UserProfileInfoView.vue'

export default {
  name: 'UserProfileView',
  components: {
    ContentBaseView,
    UserProfileInfo,
    
  }
}
</script>
