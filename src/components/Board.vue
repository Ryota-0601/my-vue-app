<template>
  <div>
    <header>🔥Training Note🔥</header>

    <main>
      <p class="info-line">0 tasks</p>
      <div class="list-index">
        <List
          v-for="(item, index) in lists"
          v-bind:key="item.id"
          v-bind:title="item.title"
          v-bind:cards="item.cards"
          v-bind:listIndex="index"
          v-bind:lists="lists"
        ></List>
      </div>

      <ListAdd v-on:emitadd="addList"></ListAdd>
    </main>
  </div>
</template>

<script>
import ListAdd from "./ListAdd.vue"
import List from "./List.vue"

//const savedLists = localStorage.getItem("trello-lists")
export default {
  data: function () {
    return {
      //: savedLists
      lists:
        // ? JSON.parse(savedLists)
        [
          { title: "Track and Field", cards: [{ body: "300m" }] },
          { title: "Todo", cards: [] },
        ],
    }
  },
  methods: {
    addList: function (title) {
      console.log(title)
      this.lists.push({ title: title, cards: [] })
      //localStorage.setItem("trello-lists", JSON.stringify(this.lists))
    },
  },

  components: {
    ListAdd,
    List,
  },
}
</script>
