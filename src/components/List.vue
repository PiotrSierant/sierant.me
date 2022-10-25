<template>
  <button @click="toggleButton">
    <span v-if="showBooks">Hide Books</span>
    <span v-else>Show Books</span>
  </button>
  <div class="books" v-if="showBooks">
    <ul>
      <li v-for="book in filteredList" :class="{ fav: book.isFav }" @click="toggleIsFav(book)">
        <img :src="book.img" :alt="book.title" />
        <section>
          <h3>{{ book.title }}</h3>
          <p>{{ book.author }}</p>
        </section>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      showBooks: true,
      books: [
        {title: 'Harry Potter', author: 'J.K. Rowling', isFav: true, img: 'src/assets/image/9788372781680.jpg'},
        {title: 'Czysta architektura', author: 'Robert C. Martin', isFav: true, img: 'src/assets/image/algbvv.jpg'},
        {title: 'Algorytmy bez tajemnic', author: 'Cormen', isFav: true, img: 'src/assets/image/CZYSTA-ARCHITEKTURA-STRUKTURA-DESIGN-OPROGRAMOWANI.jpg'}
      ]
    }
  },
  methods: {
    toggleButton() {
      this.showBooks = !this.showBooks;
    },
    toggleIsFav(book) {
      book.isFav = !book.isFav
    }
  },
  computed: {
    filteredList() {
      return this.books.filter(book => book.isFav)
    }
  }
}
</script>

<style lang="scss" scoped>
  .books {
    margin-bottom: 4rem;
  }
  ul {
    padding: 0;
    margin: 0;
    width: 100%;
  }
  li {
    padding: 3rem;
    list-style: none;
    width: 100%;
    border-bottom: 1px solid #222222;
    background-color: whitesmoke;
    display: flex;
    gap: 2rem;
    img {
      max-height: 100px;
    }
  }
  .fav {
    background-color: #8a8a8a;
  }
  h3 {
    font-size: 30px;
    color: #2c3e50;
  }
  p {
    font-size: 20px;
    color: white;
  }
</style>