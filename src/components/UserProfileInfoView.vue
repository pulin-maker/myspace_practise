<template>
<div class="container">
    <div class="row">
        <div class="col-3">
            <img src="../assets/logo.jpg" class="img-fluid" alt="">
        </div>
        <div class="col-9">
            <div class="username">Chu Bao</div>
            <div class="fans">粉丝：9999</div>
            <button type="button" class="btn btn-secondary btn-sm">+关注</button>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'UserProfileInfo',
}

</script>

<style>
img {
    border-radius: 50%;
}

.usernam {
    font-weight: bold;
}

.fans {
    font-size: 12px;
    color: gray;
}

button {
    padding: 2px 4px;
    font-size: 12px;
}
</style>
