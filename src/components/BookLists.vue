<template lang="html">
  <div class="">
    <div class="panel panel-default">
      <div class="panel-heading">
        <h3>Books Lists</h3>
      </div>
      <div class="panel-body">
        <table class="table table-striped">
          <thead>
            <tr>
              <th>
                #
              </th>
              <th>
                Title
              </th>
              <th>
                Author
              </th>
              <th>
                Delete
              </th>
            </tr>
          </thead>
          <each-book :books="books" :removebook="removebook"></each-book>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import EachBook from '../components/EachBook'
export default {
  props: ['books', 'removebook'],
  components: {
    EachBook
  }
}
</script>

<style lang="css">
</style>
