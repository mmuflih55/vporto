<template>
  <div>
    <Header />
    <Profile />
    <PostList :posts="posts" />
    <Footer />
  </div>
</template>

<script>
import Header from "~/components/Header.vue";
import Profile from "~/components/Profile.vue";
import Footer from "~/components/Footer.vue";
import PostList from "~/components/PostList.vue";

export default {
  components: {
    Header,
    Profile,
    PostList,
    Footer
  },
  asyncData ({$axios}) {    
    // https://www.googleapis.com/blogger/v3/blogs/4606092665974021629/posts?key=AIzaSyDci4ioLXX-x0SsC88MOQk399SO0PMPR14
    // return $axios.get('https://www.blogger.com/feeds/4606092665974021629/posts/default?alt=json')
    return $axios.get('https://www.googleapis.com/blogger/v3/blogs/4606092665974021629/posts?key=AIzaSyDci4ioLXX-x0SsC88MOQk399SO0PMPR14&fetchImages=true')
    .then((res) => {
      return {posts:res.data.items}
    });
  },
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
