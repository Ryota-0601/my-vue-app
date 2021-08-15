<template>
  <form class="addlist" v-on:submit.prevent="$emit('add')">
    <input v-model="title" type="text" class="text-input" />

    <button type="submit" class="add-button">Add</button>
  </form>
</template>

<script>
export default {
  // props: {
  //   lists: {
  //     type: Array,
  //     //required: true,
  //   },
  // },
  data: function () {
    return {
      title: "",
    }
  },
}
</script>
