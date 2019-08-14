<template>
 <div id="app">
  <md-card md-with-hover v-for="(book, key) in books" v-bind:key="key">
      <md-ripple>
        <md-card-header>
          <div class="md-title">{{book.name}}</div>
          <div class="md-subhead">{{book.genre}}</div>
        </md-card-header>

        <md-card-actions>
          <md-button type="primary" @click="addBook(key)">Donate to improve {{book.genre}}</md-button>
        </md-card-actions>
      </md-ripple>
    </md-card>

    <div v-if="show">
      <md-card-content>
     <donate v-bind:selectList="selectList"></donate>
      </md-card-content>
</div>

    <md-button @click="show = true" id="donate">Donate {{selectList.length}} book(s)</md-button>
  </div>

  
</template>



<script>
  export default {
  name: 'RegularButtons',
  methods: {
    addBook (key) {
      if(!this.selectList.includes(key)) {
        this.selectList.push(key);
      }
    }
  },
  components: {
    donate: () => import('./Donate')
  },
  data: () => ({
    books: [
      { name: 'Using Creatine', genre: 'Workouts' },
      { name: 'Learn Parkour', genre: 'Sports' },
      { name: 'Snorkelling', genre: 'Diving' },
    ],
    selectList: [],
    show: false
  })
}
</script>