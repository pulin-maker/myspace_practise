<template>
<div class="container">
<div class="card">
  <div class="card-body">
    <slot></slot>
  </div>
</div>
</div>
</template>

<script>
export default {
    name: "ContentBaseView",
    components: {
        
    }
}
</script>

<style scoped>
.container {
  margin-top: 15px;
}
</style>
