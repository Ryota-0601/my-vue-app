<template>
  <div class="card">
    <button class="close-button" v-on:click="removeCardFromList">×</button>
    <div class="body">{{ body }}</div>
  </div>
</template>

<script>
export default {
  props: {
    body: {
      type: String,
      required: true,
    },
    listIndex: {
      type: Number,
      required: true,
    },
    cardIndex: {
      type: Number,
      required: true,
    },
    //lists: {
    //   type: Array,
    //   required: true,
    // },
    cards: {
      type: Array,
      required: true,
    },
  },
  methods: {
    removeCardFromList: function (cardIndex) {
      this.cards.splice(cardIndex, 1)
      //localStorage.setItem("trello-lists", JSON.stringify(this.lists))
    },
  },
}
</script>
