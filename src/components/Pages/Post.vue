<template>
  <div class="Post">
    <div class="wrap-post">
      <a href="#">
        <span>
          <em>Read more</em> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cumque deleniti Lorem ipsum dolor sit amet consectetur adipisicing elit. Odio, voluptate.
        </span>
      </a>
    </div>
    <Comment v-on:createComment="createComment" />
    <AddComment v-bind:AddComments="AddComments" />
  </div>
</template>

<script>
import Comment from "./Comment";
import AddComment from "./AddComment";

let AddComments = [
  {
    id: "1",
    name:
      "lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum"
  },
  {
    id: "2",
    name:
      "lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum lorem ipsum"
  }
];
export default {
  name: "post",
  components: {
    Comment,
    AddComment
  },
  data: function() {
    return {
      AddComments: AddComments
    };
  },
  methods: {
    createComment: function(comment) {
      let newComment = {
        id: Math.floor(Math.random() * 1000000),
        name: comment
      };
      AddComments.push(newComment);
    }
  }
};
</script>

<style scoped lang="stylus">
.Post {
  background-color: #f3f3f3;
  width: 100vw;
  height: 100vh;

  .wrap-post {
    width: 900px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto;
    padding: 20px;

    a {
      background-image: url('../../assets/post-blog.jpg');
      width: 700px;
      height: 250px;
      border: 4px solid #000;
      color: #fff;
      transition: all 0.4s ease-in-out;
      text-decoration: none;
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center center;

      &:hover {
        height: 350px;
      }

      span {
        font-size: 25px;
        font-weight: bold;
        padding: 9rem 1rem 0;
        display: block;
        filter: drop-shadow(0px 0px 12px rgba(0, 0, 0, 11));
      }
    }
  }
}
</style>
