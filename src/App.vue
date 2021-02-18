<template>
  <div id="app" class="container">
    <div class="page-header">
        <h1>Vue.js & Firebase Sample Application</h1>
    </div>
    <div class="card">
      <div class="card-heading">
          <h3>Books Lists</h3>
      </div>
      <div class="card-body">
          <table class="table table-striped">
            <thead>
            <tr>
              <th>Title</th>
              <th>Author</th>
            </tr>
            </thead>

            <tbody>
            <tr v-for="book in books">
              <td>
                <a v-bind:href="book.url">{{ Book.title }}</a>
              </td>
              
            </tr>
            </tbody>
            
          </table>
      </div>

    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

let config = {
    apiKey: "AIzaSyCfpjG6IOvEE3VrHNDu2VhECWcgRJ7hqZ0",
    authDomain: "vuejs-firebase-01-993a0.firebaseapp.com",
    databaseURL: "https://vuejs-firebase-01-993a0-default-rtdb.firebaseio.com",
    projectId: "vuejs-firebase-01-993a0",
    storageBucket: "vuejs-firebase-01-993a0.appspot.com",
    messagingSenderId: "627392166137",
    appId: "1:627392166137:web:fba2c6325eeda75df14a28",
    measurementId: "G-TSL50SQ659"
}

let app = Firebase.initializeApp(config);
let db = app.database();

let bookRef = db.ref('books');


export default {
  name: 'App',
  firebase: {
    books: bookRef
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
