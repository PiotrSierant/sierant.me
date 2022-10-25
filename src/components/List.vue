<template>
  <section class="list_section">
    <div class="container">
      <button @click="toggleButton" class="list__button" v-if="filteredList.length !== 0">
        <span v-if="showBooks">Hide Books</span>
        <span v-else>Show Books</span>
      </button>
    </div>
      <div class="books" v-if="showBooks">
        <ul>
          <li v-for="book in filteredList" :class="{ fav: book.isFav }" @click="toggleIsFav(book)">
            <div class="container">
              <img :src="book.img" :alt="book.title" />
              <section>
                <h3>{{ book.title }}</h3>
                <p>{{ book.author }}</p>
              </section>
            </div>
          </li>
        </ul>
      </div>
  </section>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      showBooks: true,
      books: [
        {title: 'Harry Potter', author: 'J.K. Rowling', isFav: true, img: 'src/assets/image/9788372781680.jpg'},
        {title: 'Czysta architektura', author: 'Robert C. Martin', isFav: true, img: 'src/assets/image/CZYSTA-ARCHITEKTURA-STRUKTURA-DESIGN-OPROGRAMOWANI.jpg'},
        {title: 'Algorytmy bez tajemnic', author: 'Cormen', isFav: true, img: 'src/assets/image/algbvv.jpg'}
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
  .list_section {
    width: 100%;
    background-color: whitesmoke;

  }
  .list__button {
    padding: 1rem 2rem;
    border: 1px solid #42b883;
    background-color: #35495e;
    color: whitesmoke;
    cursor: pointer;
    margin: 1rem 0;
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
    display: flex;
    gap: 2rem;
    justify-content: flex-start;
    align-items: center;
    img {
      max-height: 100px;
    }
  }
  .container {
    max-width: 1024px;
    width: 100%;
    display: flex;
    gap: 2rem;
    margin: 0 auto;
  }
  .fav {
    background-color: #42b883;
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