<template>
 <div>
   <HeaderAuth />
   <div class="card">
     <p>ログイン</p>
   </div>
   <div class="form">
     <input type="email" placeholder="メールアドレス" v-model="email" />
     <input type="password" placeholder="パスワード" v-model="password" />
     <button @click="auth">ログイン</button>
   </div>
</div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth"
export default {
  data(){
    return{
      email:"",
      password:""
    };
  },
  components:{
    HeaderAuth
  },
  methods:{
    auth(){
      this.$store.dispatch("login",{
        email:this.email,
        password:this.password
      });
    }
  }
};
</script>



<style scoped>
.right {
  align-items: center;
}
.right p {
  margin-right: 20px;
  cursor: pointer;
}
.header {
  margin: 20px;
}
.logo {
  width: 150px;
  cursor: pointer;
}
.flex {
  display: flex;
  justify-content: space-between;
}
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