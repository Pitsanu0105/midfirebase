<template>
<div id="app" class="container">
  <div class="page-header">
    <h1>Vue.js 2 & Firebase Sample Application</h1>
  </div>
  <add-book :addbook="addBook" :newbook="newBook"></add-book>
  <book-lists :books="books" :removebook="removeBook"></book-lists>
</div>
</template>

<script>
import Firebase from 'firebase'
import toastr from 'toastr'

import BookLists from './components/BookLists'
import AddBook from './components/AddBook'

let config = {
  apiKey: 'AIzaSyDr77NfWKFVV7-SI-CGVwc0MfE7EfVZNOI',
  authDomain: 'vuejs2-firebase-01.firebaseapp.com',
  databaseURL: 'https://vuejs2-firebase-01.firebaseio.com',
  storageBucket: 'vuejs2-firebase-01.appspot.com',
  messagingSenderId: '1029276506770'
}

let app = Firebase.initializeApp(config)
let db = app.database()

let booksRef = db.ref('books')

export default {
  name: 'app',
  firebase: {
    books: booksRef
  },
  data () {
    return {
      newBook: {
        title: '',
        author: '',
        url: ''
      }
    }
  },
  components: {
    BookLists,
    AddBook
  },
  methods: {
    addBook: function () {
      booksRef.push(this.newBook)
      toastr.success('Add new Book')
      this.newBook.title = ''
      this.newBook.author = ''
      this.newBook.url = ''
    },
    removeBook: function (book) {
      booksRef.child(book['.key']).remove()
      toastr.error('Book remove')
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
