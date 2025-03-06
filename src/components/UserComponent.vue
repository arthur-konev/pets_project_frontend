<template>
  <span>
    <span v-if="isLoggedIn" class="username">
      {{ userName }} | 
    </span>
    <span v-if="showLink">
      <router-link v-if="!isLoggedIn" to="/login" >Войти</router-link>
      <router-link v-else  to="/logout" >Выйти</router-link>
    </span>
  </span>
</template>


<script>
    //import { mapActions } from "vuex";

  export default {
    computed : {
      isLoggedIn: function(){
        return this.$store.getters.isAuthenticated
      },
      userName: function(){
        return this.$store.getters.userName
      },
      showLink: function() {
        return !(this.$route.name == 'login' || this.$route.name == 'logout') 
      }
    }
  }
</script>

<style scoped>

a {
  color: #286;
}

.username 
{
  color: #826;
  font-weight: bolder;
}

</style>