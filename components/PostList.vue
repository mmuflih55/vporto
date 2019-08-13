
<template>
  <el-col :xs="24" :md="19">
    <el-card class="box-card">
      <h2>My Blog Post</h2>
      <div class="bodycon">
        <a v-for="(p,i) in posts" :key="i" @click="toindex(i)">
          <el-card class="box-card postlist">
            <div class="plistcontent" >
                <div>
                  <img class="thumbnail" :src="p.images[0].url" alt="">
                </div>
                <div style="padding-left:10px;">
                  <label><b>{{p.title}}</b></label>
                  <p>By: {{p.displayName}}</p>
                  <p>{{new Date(p.published).toDateString()}}</p>
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
      let id = this.posts[idx].id;
      this.$router.push(`/post/${id}`);
    }
  },
  mounted(){
    console.log(this.posts)
  }
};
</script>
<style scoped>
.thumbnail{
  height: 100px;
  width: 150px;
}

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
