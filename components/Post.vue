
<template>
  <el-col :xs="24" :md="19">
    <el-card class="box-card bodycon">
      <h2>{{data.title}}</h2>
      <p>{{updated}}, By: {{data.author.displayName}}</p>
      <div class="labelcon">
        <span class="label" v-for="(lbl,i) in data.labels" :key="i">{{lbl}}</span>
      </div>
      <div v-html="data.content"></div>
    </el-card>
  </el-col>
</template>

<script>
export default {
  props:['data'],
  computed:{
    updated(){
      return new Date(this.data.updated).toDateString();
    }
  },
  mounted(){
    console.log(this.data)
  }
}
</script>
<style scoped>
.bodycon {
  height: 80vh;
  overflow-y: scroll;
  margin: 10px;
  padding: 15px;
}

.label{
  background-color: rgb(77, 146, 192);
  padding: 5px;
  margin: 5px;
  color: white;
}

.labelcon{
  padding-top: 10px;
  margin-bottom: 15px;
}
</style>
