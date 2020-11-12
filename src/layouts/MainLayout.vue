<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar class="flex justify-around bg-secondary">
        <p class="text-h6 q-ma-none">My ToDo</p>
        <p class="text-subtitle1 q-ma-none">{{ todaysDate }}</p>
      </q-toolbar>
    </q-header>
    <q-footer class="bg-secondary">
      <q-toolbar>
        <q-list dark class="full-width flex justify-around" padding>
        <q-item dark to="/" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="list" />
          </q-item-section>

          <q-item-section>
            To do list
          </q-item-section>
        </q-item>
        <q-item to="/help" clickable v-ripple exact>
          <q-item-section avatar>
            <q-icon name="help" />
          </q-item-section>

          <q-item-section>
            Help
          </q-item-section>
        </q-item>
        </q-list>
      </q-toolbar>
    </q-footer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { date } from 'quasar'

export default {
  name: 'MainLayout',
  data () {
    return {
      leftDrawerOpen: false,
    }
  },
  computed: {
    todaysDate(){
      let timeStamp = Date.now()
      return date.formatDate(timeStamp, 'dddd D MMMM')
    }
  }
}
</script>

<style lang="scss">
  .header-image {
    height: 100%;
    z-index: -1;
  }
</style>
