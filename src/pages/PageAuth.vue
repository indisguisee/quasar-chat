<template>
  <q-page class="flex q-pa-md">
    <q-card class="full-width">
        <q-tabs
            v-model="tab"
            dense
            class="text-grey"
            active-color="primary"
            indicator-color="primary"
            align="justify"
            narrow-indicator
            >
            <q-tab name="login" label="Login" />
            <q-tab name="register" label="Register" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="login">
            <loginRegister :tab="tab" />
          </q-tab-panel>

          <q-tab-panel name="register">
            <loginRegister :tab="tab" />
          </q-tab-panel>

        </q-tab-panels>
      </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import LoginRegister  from "src/components/LoginRegister.vue"

// export default defineComponent({

// })
import { ref } from 'vue'

export default {
  setup () {
    return {
      tab: ref('login')
    }
  }
}
</script>
