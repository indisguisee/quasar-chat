<template>
  <q-page class="flex q-pa-md">
    <!-- <img
      alt="Quasar logo"
      src="~assets/quasar-logo-vertical.svg"
      style="width: 200px; height: 200px"
    > -->
    <q-list
      class="full-width"
      separator>
      <q-item
        v-for="user in users"
        :key="user.id"
        to="/chat"
        clickable
        v-ripple>
        <q-item-section avatar>
          <q-avatar color="primary" text-color="white">
            {{ user.name.charAt(0) }}
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ user.name }}</q-item-label>
        </q-item-section>

        <q-item-section side>
          <q-badge
            :color="user.online ? 'light-green-5' : 'grey-4'">
            {{ user.online ? 'Online' : 'Offline' }}
          </q-badge>
        </q-item-section>
      </q-item>


    </q-list>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

  export default {
    setup () {
      return {
        users: [ {
          id: 1,
          name: 'Tyler',
          online: true
        }, {
          id: 2,
          name: 'Bianca',
          online: false
        }, {
          id: 3,
          name: 'Wednesday',
          online: true
        }]
      }
    }
  }
</script>
