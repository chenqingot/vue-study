<template>
  <div id="watch-example">
    <p>
      Ask a yes/no question:
      <input v-model="message">
    </p>
    <p v-bind:class="classObject">{{ answer }}</p>
    <button @click="dotest">dotest</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      message: "Word",
      answer: "test",
      random: 0,
      classObject: {
        active: false,
        'text-danger':false
      }
    };
  },
  watch:{
    random(val){
      this.classObject.active= this.random>0.5;
      this.classObject['text-danger']= Math.random()>0.5;
    }
  },
  created() {
    setInterval(()=>{
      this.random = Math.random();
    }, 500);
  },
  methods:{
    dotest(){
      alert("hello");
    }
  }
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.active {
  font-size: 25px;
}
.text-danger {
  color: red;
}
</style>
