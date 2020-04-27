<template>
  <div v-if="href == null" class="floating-container" :style="'height: ' + height + 'px;'">
    <img :src="image"/>
  </div>
  <div v-else class="floating-container" :style="'height: ' + height + 'px;'">
    <a :href="href">
      <img :src="image"/>
    </a>
  </div>
</template>

<script>
  export default {
    name: 'FloatingIcon',
    props: {
      image: {
        required: true,
        type: String
      },
      height: {
        required: true,
        type: Number
      },
      href: String,
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  a {
    height: 100%;
    width: 100%;
  }
  img {
    transition: 0.5s;
    box-sizing: border-box;
    object-fit: contain;
    width: 100%;
    height: 100%;
    padding: 10px;
  }
  img:hover {
    padding: 0px;
  }
  .floating-container {
    display: flex;
    align-items: center;
    justify-content: center;
    transition: 0.5s;
    box-sizing: border-box;
  }
</style>