<template>
  <div id="app">
    <!-- <Home /> -->
    <!-- <Form /> -->
    <PostDetails :text="text"/>
  </div>
</template>

<script>
// import Home from './components/Home';
// import Form from './components/Form';
import PostDetails from './components/PostDetails';
export default {
  data() {
    return {
      text: "Introduction to Vuejs by FrontEnd masters"
    }
    
  },
  components: {
    // Home,
    // Form
    PostDetails
  }
}
</script>

<style>

</style>