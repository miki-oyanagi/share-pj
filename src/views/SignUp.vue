<template>
  <div>
    <HeaderAuth />
      <div class="card">
        <p>新規作成</p>
        <input type="text" placeholder="ユーザーネーム" v-model="name">
        <input type="text" placeholder="プロフィール" v-model="profile">
        <input type="email" placeholder="メールアドレス" v-model="email">
        <input type="password" placeholder="パスワード" v-model="password">
        <button @click="auth">新規登録</button>
      </div>
  </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth"
import axios from "axios";
export default {
  data(){
    return{
      name:"",
      profile:"",
      email:"",
      password:""
    };
  },
  components:{
    HeaderAuth
  },
  methods:{
    auth(){
      axios
      .post("http://localhost:8000/api/register",{
        name:this.name,
        profile:this.profile,
        email:this.email,
        password:this.password
      })
      .then(response=>{
        console.log(response);
        this.$router.replace("/");
      })
      .catch(error=>{
        alert(error);
      });
    }
  }
};
</script>

<style scoped>
button {
  width: 100px;
  text-align: center;
  padding: 8px 0 10px;
  color: #fff;
  background-color: #5419da;
  border-radius: 25px;
  cursor: pointer;
}
.card {
  margin: 100px auto;
  width: 350px;
  background: #fff;
  border-radius: 5px;
  padding: 20px;
}
.card p {
  color: black;
  font-weight: bold;
  text-align: center;
}
input {
  margin-top: 15px;
  width: 80%;
  border-radius: 10px;
  padding: 10px;
  border: 1px solid black;
  color: black;
}
.form {
  text-align: center;
}
.form button {
  margin-top: 15px;
}
</style>