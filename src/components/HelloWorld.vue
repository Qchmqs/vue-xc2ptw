<template>
  <div class="hello">
    <h1 v-on:click='fetchHello'>{{ msg }}</h1>
    <h2 v-if='display'>{{ hello }}</h2>
    <ul>
      <li v-for='person in people'>
        {{ person.name }}
      </li>
    <ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      hello: 'string',
      display: false
    }
  },
  methods:{
    fetchHello() {
      this.hello = "hello"
      this.display = true
    }
  },
  computed: {
    people: () => {
      const ids = [1,2,3,4,5,6]
      return ids.map((e) => ({ id: e, name: `person ${e}` }))
    }
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
</style>
