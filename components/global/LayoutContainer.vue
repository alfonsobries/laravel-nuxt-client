<template>
  <div 
    :class="{
      'd-flex h-full flex-1': true,
      'flex-row': ! col,
      'flex-col': col,
  }">
    <slot/>
  </div>
</template>

<script>
export default {
  name: 'LayoutContainer',

  props: {
    col: {
      type: Boolean,
      default: false
    }
  },
}
</script>
