<template>
  <header>
    <div style='flex: auto; text-align: center;'>
    <user-component />
    <router-link :to="{name: 'home'}" >
      <img alt="Vue logo" class="logo" src="@/assets/pet.png" width="250" height="150" />
    </router-link>
  </div>
    <div class="wrapper">
      <h3>Любимые питомцы</h3>
      <br/>
      <nav>
        <router-link to="/petstypeslist">Типы питомцев</router-link>
        <router-link to="/ownerslist">Владельцы</router-link>
        <router-link to="/petslist">Питомцы</router-link>
      </nav>
    </div>
  </header>
  <router-view />
</template>

<script>
import UserComponent from './components/UserComponent.vue';
export default {
  components: {
    UserComponent,
  }
}
</script>


<style scoped>

h3 {
  font-size: x-large;
  color: #46a;
  padding-right: 4px;
  box-shadow: 3px 3px 3px #abc;
}

header {
  line-height: 1.5;
  max-height: 100vh;
  color: rgb(139, 215, 234);
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
  
}

nav a.router-link-exact-active {
  color: #ffff
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
  
}

nav a {
  display: inline-block;
  padding: 1rem;
  border-left: 1px solid #ffff;
  color: #2c6b7a;
  border-radius: 0;
}

nav a:first-of-type {
  border: none;
}

@media (min-width: 1024px) {

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
    
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
    
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
    
  }
}
</style>
