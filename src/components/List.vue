<template>
  <div class="list">
    <div class="listheader">
      <p class="list-title">{{ title }}</p>
      <p class="list-counter">total:{{ totalCardInList }}</p>
    </div>
    <Card
      v-for="(item, index) in cards"
      v-bind:body="item.body"
      v-bind:key="item.id"
      v-bind:cardIndes="index"
      v-bind:listIndex="listIndex"
    ></Card>
    <CardAdd v-on:emitaddCard="addCardToList"></CardAdd>
  </div>
</template>

<script>
import CardAdd from "./CardAdd.vue"
import Card from "./Card.vue"

export default {
  components: {
    CardAdd,
    Card,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    cards: {
      type: Array,
      required: true,
    },
    listIndex: {
      type: Number,
      required: true,
    },
  },
  computed: {
    totalCardInList: function () {
      return this.cards.length
    },
  },
  methods: {
    addCardToList: function (body) {
      this.cards.push({ body: body })
    },
  },
}
</script>
