<template>
  <div>
    <header>MY TodoList</header>

    <main>
      <p class="info-line">0 tasks</p>
      <div class="list-index">
        <List
          v-for="(item, index) in lists"
          v-bind:key="item.id"
          v-bind:title="item.title"
          v-bind:cards="item.cards"
          v-bind:listIndex="index"
        ></List>
      </div>

      <ListAdd v-on:emitadd="addList"></ListAdd>
    </main>
  </div>
</template>

<script>
import ListAdd from "./ListAdd.vue"
import List from "./List.vue"
export default {
  data: function () {
    return {
      lists: [
        { title: "Track and Field", cards: [{ body: "300m" }] },
        { title: "Todo", cards: [] },
      ],
    }
  },
  methods: {
    addList: function (title) {
      console.log(title)
      this.lists.push({ title: title })
    },
  },

  components: {
    ListAdd,
    List,
  },
}
</script>
