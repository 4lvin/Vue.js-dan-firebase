<template>
  <div id="app" class="container">
    <div class="page-header">
      <h1>Aplication Vue</h1>
    </div>
    <div class="panel panel-default">
      <div class="panel-heading">
        <h3>Books List</h3>
      </div>
      <div class="panel-body">
        <table class="table table-striped">
          <thead>
          <tr>
            <th>Title</th>
            <th>Author</th>
          </tr>
          </thead>
          <tbody>
          <tr v-for="book in books">
            <a v-bind:href="book.url">{{book.title}}</a>
            <td>{{book.author}}</td>
          </tr>
          </tbody>
        </table>
      </div>
    </div>

  </div>
</template>

<script>
  import Firebase from 'firebase'
  let config ={
    apiKey: "AIzaSyDpKhyZ430aorUNR9iIPLP892ejfoOXWQY",
    authDomain: "vuejs-firebase-5a388.firebaseapp.com",
    databaseURL: "https://vuejs-firebase-5a388.firebaseio.com",
    projectId: "vuejs-firebase-5a388",
    storageBucket: "vuejs-firebase-5a388.appspot.com",
    messagingSenderId: "889403149228"
  }
  let app = Firebase.initializeApp(config);
  let db = app.database();

  let booksRef = db.ref('books');

export default {
  name: 'App',
  firebase: {
      books : booksRef
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
