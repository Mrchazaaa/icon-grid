<template>
  <div id="icon-list" :style="'grid-template-columns: repeat(' + rowWidth + ', 1fr);' + 'background-color: black;'">
    <FloatingIcon 
      v-for="item in items" 
      :key="item.image"
      :image="item.image" 
      :href="item.link"
      :style="'grid-column: span ' + item.width + ';'"
      :height="200" />
  </div>
</template>

<script>
  import FloatingIcon from "./FloatingIcon.vue";

  export default {
    name: "IconList",
    props: {
      items: {
        type: Array,
        required: true
      },
      rowWidth: {
        type: Number,
        required: true
      }
    },
    components: {
      FloatingIcon,
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  #icon-list {
    width: 100%;
    display: grid;
    grid-template-rows: 200px;
  }
</style>

