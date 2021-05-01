<template>
  <div>
    <div v-for="(value,index) in shares" :key="index">
      <div class="message">
        <div class="flex">
          <p class="name">{{value.name}}</p>
          <img class="icon" src="../assets/heart.png" alt="">
          <p class="number">{{value.like.length}}</p>
          <img class="icon" src="../assets/cross.png" alt="">
          <img class="icon detail" src="../assets/detail.png" alt="">
        </div>
        <p class="text">{{value.shares}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      share:[{name:"太郎",like:[],share:"はじめまして"}]
    };
  }
};
</script>

<style scoped>
.flex {
  display: flex;
}
.icon {
  width: 25px;
  height: 25px;
}
.detail {
  margin-left: 50px;
}
.message {
  padding: 20px;
  border-bottom: solid 1px white;
  border-left: solid 1px white;
}
.name {
  font-size: 18px;
  font-weight: bold;
  margin-right: 10px;
}
.text {
  margin-top: 10px;
}
.number {
  margin-left: 10px;
  margin-right: 10px;
}
</style>