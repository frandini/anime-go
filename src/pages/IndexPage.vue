<template>
  <q-page class="flex column page">
    <main-panel />
  </q-page>
</template>

<script>
const maxSize = 100;
const heavyList = [];

for (let i = 0; i < maxSize; i += 1) {
  heavyList.push({
    label: `Option ${i + 1}`,
    banner: i % 5 === 0,
  });
}

import MainPanel from 'components/MainPanel.vue';

export default {
  name: 'IndexPage',
  components: { MainPanel },
  data() {
    return {
      heavyList,
    };
  },
};
</script>

<style lang="scss" scoped>
.page {
  padding-top: 0 !important;
}

.virtual-scroll {
  max-height: calc(100vh - 72px);
}
</style>
