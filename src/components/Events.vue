<script>
export default {
    name: 'Events',
    data() {
        return {
            x: 0,
            y: 0,
        }
    },
    methods: {
        handleEvent(e) {
            console.log(e.type)
        },
        handleMouseMove(e) {
            this.x = e.offsetX;
            this.y = e.offsetY;
        },
    },
}
</script>

<template>
  <section class="events__section">
    <h3>Events</h3>
    <div class="box__container">
      <div class="box" @mouseover="handleEvent">mouseover</div>
      <div class="box" @mouseleave="handleEvent">mouseleave</div>
      <div class="box" @dblclick="handleEvent">double click</div>
      <div class="box" @mousemove="handleMouseMove">
        <p>Position: ({{ x }}, {{ y }})</p>
      </div>
    </div>
    <!-- <div class="box" @mousemove.stop="handleEvent"></div> modyfikator vue,  -->
  </section>

</template>

<style lang="scss" scoped>
.box__container {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
h3 {
  padding: 1rem;
  font-size: 40px;
}
.events__section {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-bottom: 1rem;
}
.box {
    padding: 100px 0;
    min-width: 250px;
    text-align: center;
    background-color: #ddd;
    margin: 20px;
    box-shadow: 0 0 5px black;
}
</style>