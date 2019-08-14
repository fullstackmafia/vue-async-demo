<template>
      <div title="Donate Books" key="donate">
          <p v-for="(x, y) in this.selectList" :key="y">
          Tip: {{books[Number(x)].name}} is about {{books[Number(x)].genre}}
          </p>
      </div>
</template>

<script>
export default {
  props: ['selectList'],
  data: () => ({
    books: [
      { name: 'Using Creatine', genre: 'Workouts' },
      { name: 'Learn Parkour', genre: 'Sports' },
      { name: 'Snorkelling', genre: 'Underwater' },
    ]
  })
}
</script>