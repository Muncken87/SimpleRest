<template>
  <div id="app">
    <img src="./assets/logo.png">
    <input v-model="selected.title" ref="userTitle" ></input>
    <input v-model="selected.body"></input>
    <button @click="editUser">Submit</button>
    <div v-for="(user, index) in users" :key="user.id" class="loop" @click="selectedUser(user)">
      <!-- <button @click="removeUser(index)">Delete</button> -->
      <h2 class="left">{{user.id}}</h2>
      <h2 class="left">{{user.title}}</h2>
      <p class="left">{{user.body}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      users:
       [
        { 
          id: 1,
          title: "Alex aut facere repellat provident occaecati excepturi optio reprehenderit",
          body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto"
        },
        {
          id: 2,
          title: "Emil aut facere repellat provident occaecati excepturi optio reprehenderit",
          body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto"
        },
        {
          id: 3,
          title: "Sune aut facere repellat provident occaecati excepturi optio reprehenderit",
          body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto"
        },
        {
          id: 4,
          title: "Bara aut facere repellat provident occaecati excepturi optio reprehenderit",
          body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto"
        },
        {
          id: 5,
          title: "Odd aut facere repellat provident occaecati excepturi optio reprehenderit",
          body: "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas totam nostrum rerum est autem sunt rem eveniet architecto"
        }
      ],
      selected: ''
    }
  },
  // created: function() {
  //    this.$http.get('https://jsonplaceholder.typicode.com/posts/')
  //     .then(response => {
  //       this.users = response.body.slice(0,5);
  //       console.log(this.users.length);
  //     });
  // },
  methods: {
    removeUser: function(index){
      this.users.splice(index,1)
      console.log(index);
    },
    selectedUser(user){
      this.selected = user;
      console.log(this.selected);
    },
    editUser(){
      this.selected.title = this.$refs.userTitle.value
      console.log(this.users);
    }
  }
  
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 600px;
  margin: 60px auto 0 auto;
}

.loop{
  position: relative
}

.left{
  text-align: left;
}

h1, h2 {
  font-weight: normal;
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
