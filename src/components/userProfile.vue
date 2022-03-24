<template>
  <h1 class="user-header">@{{ user.username }} - {{ fullName }}</h1>
  <h2 class="user-followers">followers: {{ followers }}</h2>
  <p v-show="user.isAdmin">Admin</p>
  <div class="tweets">
    <tweets
      v-for="tweet in user.tweets"
      :key="tweet.id"
      :content="tweet.content"
    />
  </div>
  <button @click="increaseFollowers">Increase Followers</button>
</template>

<script>
import tweets from "./tweets.vue";
export default {
  components: { tweets },
  name: "userProfile",
  data() {
    return {
      followers: 0,
      user: {
        username: "devMu3ty",
        firstName: "Mahmoud",
        lastName: "Abdulmuty",
        email: "mahmoudabdulmuty@gmail.com",
        isAdmin: true,
        tweets: [
          { id: 1, content: "twitter is Amazing" },
          { id: 2, content: "Don't forget to follow" },
          { id: 3, content: "I'm trying to learn Vue as hard as I can" },
        ],
      },
    };
  },

  watch: {
    followers(newCount, oldCount) {
      if (oldCount < newCount) {
        console.log(`${this.user.username} has gained a follower!`);
      }
    },
  },

  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },

  methods: {
    increaseFollowers() {
      this.followers++;
    },
  },

  mounted() {
    this.increaseFollowers();
  },
};
</script>

<style scoped>
.tweets {
  display: flex;
  flex-direction: column;
  margin: 20px auto;
}
</style>