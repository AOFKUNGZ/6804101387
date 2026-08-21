<template>
  <q-page class="flex flex-center">
    <q-btn color="secondary" to="/" label="Go to Index Page" no-caps />
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { useQuasar } from 'quasar'

const $q = useQuasar()
const name = ref('')
const age = ref(null)
const accept = ref(false)

function onSubmit () {
  if (accept.value !== true) {
    $q.notify({
      type: 'negative',
      message: 'You need to accept the license and terms first'
    })
  } else {
    $q.notify({
      type: 'positive',
      message: 'Submitted successfully'
    })
  }
}

function onReset () {
  name.value = ''
  age.value = null
  accept.value = false
}
</script>
