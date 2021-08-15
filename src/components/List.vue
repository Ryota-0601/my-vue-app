<template>
  <div class="list">
    <div class="listheader">
      <p class="list-title">{{ title }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    listIndex: {
      type: Number,
      required: true,
    },
  },
}
</script>
