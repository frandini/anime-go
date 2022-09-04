<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-transparent text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="~assets/anime-logo.png">
          </q-avatar>
          AnimeGo
        </q-toolbar-title>
        <q-btn
          flat
          round
          dense
          icon="search"
        />
        <q-btn
          flat
          round
          dense
          icon="notifications"
        />
      </q-toolbar>
    </q-header>

    <q-page-container class="main-page-container">
      <router-view />
    </q-page-container>

    <q-footer class="footer">
      <q-tabs
        v-model="tab"
        no-caps
        align="justify"
        outside-arrows
        mobile-arrows
        active-color="primary"
        indicator-color="transparent"
      >
        <q-tab
          name="home"
          icon="home"
          label="Home"
        />
        <q-tab
          name="calendar"
          icon="event_note"
          label="Calendar"
        />
        <q-tab
          name="list"
          icon="list"
          label="List"
        />
        <q-tab
          name="profile"
          icon="person"
          label="Profile"
        />
      </q-tabs>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'MainLayout',
  data() {
    return {
      tab: 'home',
    };
  },
};
</script>

<style scoped lang="scss">
.main-page-container {
  padding-top: 0 !important;
}

.footer {
  background: rgba(24, 26, 32, 0.88);
  backdrop-filter: blur(6.1px);
  -webkit-backdrop-filter: blur(6.1px);
  color: $primary-grey;
}
</style>

<style lang="scss">
.q-tab__label {
  font-size: 12px;
}
</style>
