<template>
     <button type="button" @click="onLogOut">Подтвердите</button>
</template>


<script>
    //import { mapActions } from "vuex";

  export default {
    methods: {
     // ...mapActions(["removeToken"]),
      async onLogOut() { 
        await this.$store.dispatch('removeToken')
        this.$router.push("/")
      },
    }
  }
</script>