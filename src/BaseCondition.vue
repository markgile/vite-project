<template>
  <div>
    <BaseCondition />
  </div>

  <div>
    <BaseLoop />
  </div>
</template>

<script>
  import BaseLoop from './BaseLoop.vue';
  import BaseCondition from './BaseCondition.vue';

  export default {
    components: {
      BaseCondition,
      BaseLoop,
    },
  };
</script>