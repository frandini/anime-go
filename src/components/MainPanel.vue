<template>
  <div
    class="banner flex"
    :style="{ backgroundImage: 'url(' + list[0].horizontal_banner + ')' }"
  >
    <div class="full-width content">
      <div class="info title">
        {{ list[0].name }}
      </div>
      <div class="info tags">
        {{ list[0].tags.join(', ') }}
      </div>
      <div>
        <q-btn
          unelevated
          rounded
          color="primary"
          label="Play"
          icon="play_circle"
          class="q-mr-sm"
        />
        <q-btn
          outline
          rounded
          text-color="white"
          icon="add"
          label="My list"
        />
      </div>
    </div>
  </div>
</template>

<script>
import db from 'src/db.json';

export default {
  name: 'MainPanel',
  data() {
    return {
      list: db,
    };
  },
};
</script>

<style lang="scss" scoped>
.banner {
  height: 40vh;
  max-height: 300px;
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: flex-end;
  width: 100vw;
}

.content {
  padding: 16px;
  background: linear-gradient(to top,
  rgba(24, 26, 32,0.8) 1%,
  rgba(24,26,32,0.1) 90%,
  rgba(24,26,32,0) 100%);
}

.info {
  color: white;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
  width: 100%;
}

.title {
  font-size: 30px;
  line-height: 100%;
  margin-bottom: 12px;
}

.tags {
  line-height: 100%;
  font-size: 14px;
  font-weight: 300;
  margin-bottom: 8px;
}
</style>
