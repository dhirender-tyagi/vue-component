<template>
  <div class="hello">
    Welcome Home 
    <app-message></app-message>
    Search UserList
    <input type="text" v-model="input" placeholder="Enter Name" class="form-control" />
    <input type="text" v-model="tempInput" placeholder="Enter other value" class="form-control" />
    <UserList v-bind:userList="filteredList()" v-bind:addUser="addUser" />
    <keep-alive>
      <component v-bind:is="component" />
    </keep-alive>
    <button v-on:click="toggle">Toggle</button>
  </div>
</template>

<script>
import UserList from './UserList'
import Test from './Test1'
import Test2 from './Test2'

export default {
  name: 'HomePage',
  data () {
    return {
      input: '',
      tempInput: '',
      component: 'Test2',
      userList: [
        {
          name: 'Alex',
          id: 1
        },
        {
          name: 'Jone',
          id: 2
        },
        {
          name: 'Blake',
          id: 3
        },
        {
          name: 'Hoze',
          id: 4
        },
        {
          name: 'Steve',
          id: 5
        }
      ]
    }
  },
  components: {
    UserList,
    Test,
    Test2
  },
  methods: {
    filteredList() {
      // eslint-disable-next-line no-console
      console.log('>>>> filter method called');
      return this.userList.filter(item =>
        item.name.toLowerCase().includes(this.input.toLowerCase())
      );
    },
    toggle(){
      if (this.component === Test) {
        this.component = Test2;
      } else {
        this.component = Test;
      }
    },
    addUser() {
      this.userList.push({
        name: 'Dhirender',
        id: '7'
      })
    }
  },
  watch: {
    tempInput: function(newVal, oldVal) {
      // eslint-disable-next-line no-console
      console.log('newVal ', newVal, 'oldVal', oldVal);
    }
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
