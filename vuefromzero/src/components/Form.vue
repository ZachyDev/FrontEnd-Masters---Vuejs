<template>
  <div id="form">
      <form>
          <h2>Vue Directives</h2>
          <input type="text" v-model="username">
          {{ username }} <br />
          <input type="checkbox" v-model="checkedNames" id="zachy">
          <label for="zachy">Zachy</label>
           <input type="checkbox" v-model="checkedNames" id="finna">
          <label for="finna">Finna</label>
           <input type="checkbox" v-model="checkedNames" id="willy"> 
          <label for="willy">Willy</label><br />
          <strong>CheckedNames</strong>{{ checkedNames }}
      </form>
      <!-- form2 -->
           <form>
               <h3>What is your favorite color?</h3>
              <textarea v-model="opinion"></textarea><br />
               <button type="button" v-show="opinion">Sumbit poll</button>
          </form>
         
  </div>
</template>

<script>
export default {
    name: "Form",
    data() {
        return{
            username: '',
            checkedNames: [],
            opinion: ''
        }
    }
}
</script>

<style scoped>
    #form form{
        margin:0 auto;
        width: 50%;
    }
    
</style>