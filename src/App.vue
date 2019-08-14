<template>
  <div>
    <book></book>
  </div>
</template>

<script>
import LoadingState from "./components/LoadingState"
import ErrorState from "./components/ErrorState"
const Book = import("./components/Book")
export default {
  components: {
    Book: () => ({
      component: Book,
      loading: LoadingState,
      error: ErrorState,
      delay: 100,
      timeout: 2000
    })
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>