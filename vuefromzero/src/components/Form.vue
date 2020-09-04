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
               <button type="button" :class="[opinion ? activeClass : '']">Submit poll</button>
          </form>

          <!-- events in vuejs -->
          <div class="product">
              <h2>Shop with us</h2>
              <img :src="require(`@/assets/${'tv.jpg'}`)" alt="">
              <button class="dec" @click="counter > 0 ? counter -= 1 : 0">-</button>
              <span id="qty">Quantity{{counter}}</span>
              <button class="inc" @click="counter < 5 ? counter += 1 : 5">+</button>
              <button id="submit" @click="submit">Submit</button>
          </div>

          <pre> {{ $data }}</pre>
  </div>
</template>

<script>
export default {
    name: "Form",
    data() {
        return{
            username: '',
            checkedNames: [],
            opinion: '',
            activeClass: 'active',
            counter: 5
        }
    },
    methods: {
        submit() {
            this.counter == 0 ? alert(`Enter the quantity size.`) : alert(`Order with quantity ${this.counter} successfully placed.`);
        }
    }
}
</script>

<style scoped>
    #form form{
        margin:0 auto;
        width: 50%;
    }
    button.active{
        background: orange;
    }
    .product{
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .product img {
        position: absolute;
        top:52% ;
    }
     .product button#submit{
        position: absolute;
        top:90% ;
        background: #000;
        padding: 11px;
        width: 200px;
        color: #fff;
        border-radius: 12px;
        outline: none;
    }
    .product button.inc,button.dec,span{
        position: absolute;
        top:85%;
        width: 50px;
    }
    button.inc{
        left:43%;
    }
    button.dec{
        left:53%;
    }
    .product #qty{
        left:48%;
    }
    
</style>