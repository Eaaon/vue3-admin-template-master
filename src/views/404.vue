<template>
  <div class="http404-container">
    <img
      class="pic-404"
      src="@/assets/404_images/404.jpg"
      alt="404"
    >
  </div>
</template>

<script>

export default {
  name: 'Page404',
  computed: {
    message() {
      return 'The webmaster said that you can not enter this page...'
    }
  }
}
</script>

<style lang="scss" scoped>
.http404-container{
  width: 100%;
  height: 100%;
  background-color: #ffbe00;
}
.pic-404 {
  position: relative;
  top: 50%;
  left: 50%;
  transform: translateX(-50%) translateY(-50%);
  width: 60%;
}
</style>
