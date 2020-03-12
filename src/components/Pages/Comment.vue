<template>
  <div class="form">
    <input type="text" name="commentInput" v-model="todoValue" placeholder="Add Comment" />
    <button v-on:click="$emit('createComment', todoValue)" class="submit">+</button>
  </div>
</template>

<style lang="stylus" scoped>
.form {
  width: 700px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;

  input {
    flex: 1;
    height: 35px;
    box-sizing: border-box;
    font-size: 20px;
    padding: 10px;
  }

  .submit {
    width: 50px;
    height: 35px;
    font-size: 28px;
    background-color: #ffce00;
    border: none;
    outline: none;
    cursor: pointer;
    color: #171717;
    font-weight: bold;

    &:hover {
      box-shadow: 0 0px 0 0 rgba(#000, 0.6), 0 0 8px 0 rgba(#000, 0.5);
    }
  }
}
</style>

<script>
export default {
  name: "Comment",
  data: function() {
    return {
      todoValue: ""
    };
  }
};
</script>