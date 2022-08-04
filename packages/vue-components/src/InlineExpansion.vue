<template>
  <button v-if="!isShowInlineText" class=inline-button v-on:click="isShowInlineText = !isShowInlineText;" >
    {{ header }}
  </button>
  <div v-else class=inline-text>
    <slot></slot>
  </div>
</template>

<script>

export default {
  name: 'InlineExpansion',
  props: {
    header: {
      type: String,
      default: 'Header',
    },
  },
  data() {
    return {
      isShowInlineText: false,
    }
  },
};
</script>

<style>
.inline-text {
    display: inline-block;
}

.inline-button {
    border: 1px solid #ddd;
    padding: 4px 6px;
    border-radius: 3px;
    color: #333;
    margin: 0 6px 4px 0;
    display: inline-block;
}
</style>
