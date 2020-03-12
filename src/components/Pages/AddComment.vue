<template>
  <div id="addComment">
    <div class="newComment" v-for="(AddComment) in AddComments" v-bind:key="AddComment.id">
      <h3>{{AddComment.name}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddComment",
  props: ["AddComments"]
};
</script>

<style scoped lang="stylus">
.newComment {
  width: 700px;
  background-color: black;
  color: #fff;
  margin: 0 auto;
  padding: 10px;
  margin: 5px auto;

  h3 {
    font-size: 16px;
    font-weight: 300;
    text-transform: capitalize;
  }
}
</style>