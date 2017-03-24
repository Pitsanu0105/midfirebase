<template lang="html">
  <tbody>
      <tr v-for="(book, index) in books" transition>
        <td>
          {{index + 1}}
        </td>
        <td>
          <a v-bind:href="book.url">{{book.title}}</a>
        </td>
        <td>
          {{book.author}}
        </td>
        <td>
          <span class="glyphicon glyphicon-trash" v-on:click="removebook(book)"></span>
        </td>
      </tr>
  </tbody>
</template>

<script>
export default {
  props: ['books', 'removebook']
}
</script>

<style lang="css">
</style>
