<template>
  <ul :class="className"> 
    <slot></slot>
  </ul>
</template>

<script>
import classNames from 'classnames';

export default {
  name: 'SelectOptions',
  computed: {
    className() {
      return classNames(
        'dropdown-content',
        'select-dropdown'
      );
    }
  }
};
</script>

<style scoped>
ul {
  top: 0;
  width: 100%;
}
</style>
