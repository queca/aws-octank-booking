<template>
  <q-layout>
    <q-layout-header>
      <q-toolbar class="text-center" color="primary">
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          aria-label="Menu"
        >
          <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title class="brand">Octank Sky</q-toolbar-title>
        <q-btn
          flat
          round
          dense
          size="lg"
          icon="search"
          :to="{ name: 'home' }"
        />
      </q-toolbar>
    </q-layout-header>

    <q-layout-drawer
      v-model="leftDrawerOpen"
      :content-class="$q.theme === 'mat' ? 'bg-grey-2' : null"
    >
    <q-img class="relative-position"  src="../../../media/octank.png" style="height: 75px">
      <div class= "relative-position bg-transparent" style="top: 1%;left:1;right:12;">
        <q-avatar size="50px" class="q-mb-sm">
          <img src=../../../media/octank.png>
        </q-avatar>
      </div>
    </q-img>
      
      <q-list no-border link inset-delimiter>
        <q-item :to="{ name: 'home' }" exact>
          <q-item-side icon="home" />
          <q-item-main label="Home" sublabel="Home" />
        </q-item>
        <q-item :to="{ name: 'profile' }" exact>
          <q-item-side icon="person" />
          <q-item-main label="Profile" sublabel="User profile" />
        </q-item>
        <q-item :to="{ name: 'bookings' }" exact>
          <q-item-side icon="flight" />
          <q-item-main label="My Bookings" sublabel="Bookings" />
        </q-item>
      </q-list>



    </q-layout-drawer>

    <q-page-container>
      <transition enter-active-class="animated fadeIn" appear>
        <router-view />
      </transition>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  // name: 'LayoutName',
  data() {
    return {
      leftDrawer: true,
      leftDrawerOpen: this.$q.platform.is.desktop
    };
  }
};
</script>

<style></style>
