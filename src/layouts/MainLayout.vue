<template>
  <q-layout view="hHh lpR fFf">
    <q-header bordered class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu"/>
        <q-toolbar-title>MZK Cockpit</q-toolbar-title>
      </q-toolbar>
      <q-tabs align="left">
        <q-route-tab to="/journal" label="Journal"/>
        <q-route-tab to="/clients" label="Bewohner"/>
        <q-route-tab to="/settings" label="Einstellungen"/>
      </q-tabs>
    </q-header>
    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <q-list>
        <q-item-label header class="text-grey-8">Links</q-item-label>
        <EssentialLink v-for="link in essentialLinks" :key="link.title" v-bind="link"/>
      </q-list>
    </q-drawer>
    <q-page-container>
      <router-view/>
    </q-page-container>
    <q-footer bordered class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title>
          <span class="text-subtitle2">&copy; Joerg Dalp</span>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>
<script>
import EssentialLink from 'components/EssentialLink.vue'
export default {
  name: 'MainLayout',
  components: {
    EssentialLink
  },
  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: [
        {
          title: 'Docs',
          caption: 'quasar.dev',
          icon: 'school',
          link: 'https://quasar.dev'
        }
      ]
    }
  }
}
</script>
