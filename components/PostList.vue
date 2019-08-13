
<template>
  <el-col :xs="24" :md="19">
    <el-card class="box-card">
      <h2>My Blog Post</h2>
      <div class="bodycon">
        <a v-for="(p,i) in posts" :key="i" @click="toindex(i)">
          <el-card class="box-card postlist">
            <div class="plistcontent" >
                <div>
                  <img :src="p.media$thumbnail.url" alt="">
                </div>
                <div style="padding-left:10px;">
                  <label><b>{{p.title.$t}}</b></label>
                  <p>By: {{p.author[0].name.$t}}</p>
                  <p>{{new Date(p.published.$t).toDateString()}}</p>
                </div>
            </div>
          </el-card>
        </a>
      </div> 
    </el-card>
  </el-col>
</template>
<script>
import Header from "~/components/Header.vue";
import Profile from "~/components/Profile.vue";
import Footer from "~/components/Footer.vue";
import Post from "~/components/Post.vue";

export default {
  props:['posts'],
  methods: {
    toindex(idx){
      let id = this.posts[idx].id.$t.split('-')[2];
      this.$router.push(`/post/${id}`);
    }
  }
};
</script>
<style scoped>
.bodycon {
  height: 70vh;
  margin: 10px;
  padding: 15px;
  overflow-y:scroll;
}

.postlist {
  margin: 10px 0 10px 0;
}

.plistcontent {
  display: flex;
  flex-direction: row;
}

.postlist:hover{
  cursor: pointer;
}

</style>
