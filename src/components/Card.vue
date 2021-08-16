<template>
  <div class="card">
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
  },
}
</script>
