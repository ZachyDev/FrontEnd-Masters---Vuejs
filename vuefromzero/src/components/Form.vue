<template>
  <div id="form">
      <form>
          <input type="text" v-model="username">
          {{ username }}
      </form>
  </div>
</template>

<script>
export default {
    name: "Form",
    data() {
        return{
            username: ''
        }
    }
}
</script>

<style scoped>

</style>