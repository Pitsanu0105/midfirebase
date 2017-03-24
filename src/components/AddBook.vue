<template lang="html">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h3>Add book</h3>
    </div>
    <div class="panel-body">
      <div class="col-md-12">
      <form id="form" class="form-horizontal" v-on:submit.prevent="addbook">
        <div class="form-group">
          <label for="bookTitle">Title:</label>
          <input type="text" id="bookTitle" class="form-control" placeholder="Title" v-model="newbook.title">
        </div>
        <div class="form-group">
          <label for="bookAuthor">Author:</label>
          <input type="text" id="bookAuthor" class="form-control" placeholder="Author" v-model="newbook.author">
        </div>
        <div class="form-group">
          <label for="bookUrl">URL:</label>
          <input type="text" id="bookUrl" class="form-control" placeholder="URL" v-model="newbook.url">
        </div>
        <input type="submit" class="btn btn-primary" value="Add Book">
      </form>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['addbook', 'newbook']
}
</script>

<style lang="css">
</style>
