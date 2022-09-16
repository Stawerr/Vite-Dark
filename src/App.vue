<template>
    <DarkComponent @myFunction=""></DarkComponent>
    <UserComponent></UserComponent>
</template>

<script>
  import UserComponent from './components/userComponent.vue';
  import DarkComponent from './components/darkComponent.vue';

  export default {
  data() {
    return {
      
    }
  },
  components: {
    UserComponent,
    DarkComponent
}
}
  
</script>

<style scoped>

</style>
