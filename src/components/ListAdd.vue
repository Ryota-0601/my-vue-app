<template>
  <form class="addlist" v-on:submit.prevent="add">
    <input v-model="title" type="text" class="text-input" />

    <button type="submit" class="add-button">Add</button>
  </form>
</template>

<script>
export default {
  data: function () {
    return {
      title: "",
    }
  },
  methods: {
    add() {
      this.$emit("emitadd", this.title)
    },
  },
}
</script>
