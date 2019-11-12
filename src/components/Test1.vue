<template>
    <div>
        <h1>
            Test One Rendered
        </h1>
        <div>
            <form>
                First name: {{firstName}}<br>
                <input type="text" v-model="firstName" name="firstname"><br>
                Last name: {{lastName}}<br>
                <input type="text" v-model="lastName" name="lastname">
            </form>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Test1',
  data() {
      return {
          firstName:'',
          lastName: ''
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