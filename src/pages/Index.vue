<template>
  <q-layout view="hHh lpR fFf" class="bg-grey-1">
    <q-header elevated class="bg-blue-grey-8 text-white-1 q-py-xs glossy" height-hint="58">
      <q-toolbar>
        <q-btn flat
               dense
               round
               @click="leftDrawerOpen = !leftDrawerOpen"
               aria-label="Menu"
               icon="menu" />

        <q-btn flat no-caps no-wrap class="q-ml-xs" v-if="$q.screen.gt.xs">
          <q-icon :name="fabYoutube" color="red" size="28px" />
          <q-toolbar-title shrink class="text-weight-bold">
            HiveULT
          </q-toolbar-title>
        </q-btn>

        <q-space />

        <div class="YL__toolbar-input-container row no-wrap">
          <q-input rounded dense outlined v-model="search" placeholder="Search" class="bg-white col" />
          <q-btn class="YL__toolbar-input-btn" color="grey-3" text-color="grey-8" icon="search" unelevated />
        </div>

        <div class="q-gutter-sm row items-center no-wrap">
          <q-btn round dense flat color="grey-8" icon="video_call" v-if="$q.screen.gt.sm">
            <q-tooltip>Create a video or post</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-4" icon="apps" v-if="$q.screen.gt.sm">
            <q-tooltip>Apps</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-4" icon="message" v-if="$q.screen.gt.sm">
            <q-tooltip>Messages</q-tooltip>
          </q-btn>
          <q-btn round dense flat color="grey-8" icon="notifications">
            <q-badge color="red" text-color="white" floating>
              2
            </q-badge>
            <q-tooltip>Notifications</q-tooltip>
          </q-btn>
        </div>
        <q-space />

        <q-btn round flat>
          <q-avatar size="26px">
            <img src="https://cdn.quasar.dev/img/boy-avatar.png">
          </q-avatar>
          <q-tooltip>Account</q-tooltip>
        </q-btn>
      </q-toolbar>
    </q-header>
    <q-page class="row items-center justify-evenly">
      <example-component title="Example component"
                         active
                         :todos="todos"
                         :meta="meta"></example-component>
    </q-page>
  </q-layout>
</template>

<script lang="ts">
  import ExampleComponent from 'components/CompositionComponent.vue'
  import { Todo, Meta } from 'components/models'

  export default {
    name: 'PageIndex',
    components: { ExampleComponent },
    data() {
      const todos: Todo[] = [
        {
          id: 1,
          content: 'ct1'
        },
        {
          id: 2,
          content: 'ct2'
        },
        {
          id: 3,
          content: 'ct3'
        },
        {
          id: 4,
          content: 'ct4'
        },
        {
          id: 5,
          content: 'ct5'
        }
      ]
      const meta: Meta = {
        totalCount: 1200
      }
      return { todos, meta }
    }
  }
</script>
