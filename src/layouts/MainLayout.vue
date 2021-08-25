<template>
  <q-layout class="hide-scrollbar" view="hhh lpR fFf">

    <q-header class="bg-primary text-dark" height-hint="98">
      <q-toolbar>
        <q-btn
          class="gt-md"
          dense
          flat
          round
          icon="menu"
          @click="toggleLeftDrawer"/>

        <LoginState class="q-mr-md"/>

        <q-input class="full-width"
                 rounded
                 outlined
                 dense
                 placeholder="search"
                 :model-value="searchText"
                 @update:modelValue="searchText = $event">
          <template v-slot:prepend>
            <q-icon name="search"/>
          </template>
        </q-input>

        <q-btn class="q-ml-md"
               dense
               round
               unelevated
               icon="inbox"/>

        <q-btn
          class="q-ml-md"
          dense
          round
          unelevated
          icon="notifications_none"/>

      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" side="left" overlay behavior="desktop" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view/>
    </q-page-container>

    <q-footer bordered class="bg-primary text-dark">
      <q-toolbar class="row justify-between">
        <q-btn
          dense
          round
          unelevated
          icon="home"/>

        <q-btn
          dense
          round
          unelevated
          icon="work"/>

        <q-btn
          dense
          round
          unelevated
          icon="add_circle"/>

        <q-btn
          dense
          round
          unelevated
          icon="forum"/>

        <q-btn
          dense
          round
          unelevated
          icon="person"/>

      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import LoginState from "components/LoginState";

export default {
  name: 'MainLayout',
  components: {
    LoginState,
  },
  data() {
    return {
      leftDrawerOpen: false,
      searchText: ''
    }
  },
  methods: {
    toggleLeftDrawer() {
      this.leftDrawerOpen.value = !this.leftDrawerOpen.value
    }
  },
}
</script>
