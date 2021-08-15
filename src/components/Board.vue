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
          v-bind:listIndex="index"
        ></List>
      </div>

      <ListAdd v-on:add="addList"></ListAdd>
    </main>
  </div>
</template>

<script>
import ListAdd from "./ListAdd.vue"
import List from "./List.vue"
export default {
  data: function () {
    return {
      lists: [{ title: "Track and Field" }, { title: "Todo" }],
    }
  },
  methods: {
    addList: function () {
      //this.title = ""
      this.lists.push({ title: "" })
    },
  },

  components: {
    ListAdd,
    List,
  },
}
</script>
