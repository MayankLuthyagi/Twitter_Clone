<template>
  <q-layout view="lHr lpR fFf">

    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title bordered class = "text-weight-bold">
          <span class ="gt-sm">{{$route.name}}</span>
          <q-icon
          class = "header-icon q-pa-md lt-md"
          name = "fas fa-dove"
          size = "lg"
          color = "primary"
          />
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
    v-model="left"
    side="left"
    :width="350"
    bordered
    show-if-above
    >
      <q-icon
      class = "q-pa-md"
      name = "fas fa-dove"
      size = "lg"
      color = "primary"
      />
      <q-list>
      <q-item
      to="/"
      clickable
      v-ripple
      exact
      >
        <q-item-section avatar>
          <q-icon name="home" size="md"/>
        </q-item-section>

        <q-item-section class = "text-h6 text-weight-bold">Home</q-item-section>
      </q-item>
      </q-list>

      <q-list>
      <q-item
      to="/about"
      clickable
      v-ripple
      exact
      >
        <q-item-section avatar>
          <q-icon name="help" size="md"/>
        </q-item-section>

        <q-item-section class = "text-h6 text-weight-bold">About</q-item-section>
      </q-item>
      </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered     :width="350">
      <q-input
      placeholder="Search Twitter"
      class="q-ma-md"
      outlined
      rounded
      dense
      >
        <template v-slot:prepend>
          <q-icon name = "search" />
        </template>
      </q-input>
      <q-list
        separator
        padding
      >
        <q-item class="q-pa-md">
          <q-item-section>
            <q-item-label overline class = "text-grey">Education</q-item-label>
            <q-item-label class = "text-weight-bold">Something Amazing Happened!</q-item-label>
            <q-item-label caption>Secondary line text. Lorem ipsum dolor sit amet, consectetur adipiscit elit.</q-item-label>
          </q-item-section>

          <q-item-section side top>
            <q-item-label caption>5 min ago</q-item-label>
          </q-item-section>
        </q-item>
        <q-item class="q-pa-md">
          <q-item-section>
            <q-item-label overline class = "text-grey">Education</q-item-label>
            <q-item-label class = "text-weight-bold">Something Amazing Happened!</q-item-label>
            <q-item-label caption>Secondary line text. Lorem ipsum dolor sit amet, consectetur adipiscit elit.</q-item-label>
          </q-item-section>

          <q-item-section side top>
            <q-item-label caption>5 min ago</q-item-label>
          </q-item-section>
        </q-item>
        <q-item class="q-pa-md">
          <q-item-section>
            <q-item-label overline class = "text-grey">Education</q-item-label>
            <q-item-label class = "text-weight-bold">Something Amazing Happened!</q-item-label>
            <q-item-label caption>Secondary line text. Lorem ipsum dolor sit amet, consectetur adipiscit elit.</q-item-label>
          </q-item-section>

          <q-item-section side top>
            <q-item-label caption>5 min ago</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer () {
        rightDrawerOpen.value = !rightDrawerOpen.value
      }
    }
  }
}
</script>
<style lang="sass">
.header-icon
  position: absolute
  bottom: 0
  left: 50%
  transform : translateX(-50%)
</style>
