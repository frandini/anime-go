<template>
  <q-page class="flex column page">
    <main-panel
      class="q-mb-sm"
      :title="list[0].name"
      :tags="list[0].tags"
      :horizontal-banner="list[0].horizontal_banner"
    />
    <div>
      <feed-section
        title="Top Animes"
        :show-position="true"
        :items="list.slice(0, 10)"
        class="q-mb-md"
      />
    </div>
    <div>
      <feed-section
        title="New"
        :items="list.slice(0, 10)"
        class="q-mb-md"
      />
    </div>
    <div>
      <feed-section
        title="New"
        :items="list.slice(0, 10)"
        class="q-mb-md"
      />
    </div>
    <div>
      <feed-section
        title="New"
        :items="list.slice(0, 10)"
        class="q-mb-md"
      />
    </div>
    <div>
      <feed-section
        title="New"
        :items="list.slice(0, 10)"
        class="q-mb-md"
      />
    </div>
  </q-page>
</template>

<script>
import db from 'src/db.json';
import MainPanel from 'components/MainPanel.vue';
import FeedSection from 'components/FeedSection.vue';

export default {
  name: 'IndexPage',
  components: { MainPanel, FeedSection },
  data() {
    return {
      list: db,
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
