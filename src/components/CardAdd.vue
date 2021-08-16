<template>
  <form class="addcard" v-on:submit.prevent="addCard">
    <input
      v-model="body"
      type="text"
      class="text-input"
      placeholder="Add new card"
    />

    <button type="submit" class="add-button">Add</button>
  </form>
</template>

<script>
export default {
  data: function () {
    return {
      body: "",
    }
  },

  methods: {
    addCard: function () {
      this.$emit("emitaddCard", this.body)
    },
  },
}
</script>
