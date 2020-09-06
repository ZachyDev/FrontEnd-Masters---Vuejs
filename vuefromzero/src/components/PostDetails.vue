<template>
  <div>
     <form @submit.prevent="postData">
         <h1>Post to Server</h1>
         <input type="text" placeholder="UserId" v-model="userId"/>
         <input type="text" placeholder="Name" v-model="name"/>
         <input type="text" placeholder="Email" v-model="email"/>
         <input type="text" placeholder="skill" v-model="skill"/>
         <input type="submit" class="bg-success">
         <strong>Response from server</strong>
         {{response }}  {{ timer }}
     </form>
     
  </div>
</template>

<script>
// import axios
import axios from 'axios';
export default {
    name: "PostDetails",
    data() {
        return {
            userId: '',
            name: '',
            email: '',
            skill: '',
            response: '',
            activeClass: ''
        }
    },
    computed: {
        timer() {
            return new Date().toLocaleTimeString();
        }
    },
    methods: {
        postData() {
            axios.post('https://jsonplaceholder.typicode.com/posts',{
                userId: this.userId,
                Name: this.name,
                Email: this.email,
                Skill: this.skill
            })
            .then(res => {
                return this.response = res.data;
            })
            .catch(err => {
                return this.response = err
            })
        }
    }
   
}
</script>

<style scoped>
    form{
        width: 43%;
        position: absolute;
        left: 25%;
        top:10%;    
        display: flex;
        flex-direction: column;
    }
    form input{
        padding: 10px;
        margin: 10px;
        outline: none;
        border: 1px solid #777;
        border-radius: 10px;
    }
</style>