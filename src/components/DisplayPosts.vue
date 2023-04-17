<template>
  <div>
    <button @click="toggle_tweet">Toggle tweet</button>
    <div :class="{ 'list': tweet_post, 'grid': !this.tweet_post}">
      <div v-for="(post, index) in posts" :key="index">
        <h5>{{ post.content }}</h5>
        <h3>{{ post.user }}</h3>
        <p>{{ post.date }}</p>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    methods: {
      toggle_tweet() {
        this.tweet_post = !this.tweet_post;
      },
    },
    data() {
      return {
        posts: [
          {
            content: `hello, take a look at the earthlings. Goodbye! Must go faster. Yes, Yes, without the oops! Life finds a way. Yes, Yes, without the oops! `,
            user: `Elon Musk`,
            date: `17/04/1960`,
          },
          {
            content: `hei, take a look at the earthlings. Goodbye! Must go faster. Yes, Yes, without the oops! Life finds a way. Yes, Yes, without the oops! `,
            user: `Elon Musk`,
            date: `17/05/1960`,
          },
          {
            content: `hey, take a look at the earthlings. Goodbye! Must go faster. Yes, Yes, without the oops! Life finds a way. Yes, Yes, without the oops! `,
            user: `Elon Musk`,
            date: `17/8/1960`,
          },
        ],
        tweet_post: true,
      };
    },
  };
</script>

<style scoped>
  .list {
    display: flex;
    flex-direction: column;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    margin: 30px;
  }
</style>


