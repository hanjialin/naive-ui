<markdown>
# Use preset dialog

An example of preset `dialog`.
</markdown>

<script lang="ts" setup>
import { useMessage } from 'naive-ui'
import { ref } from 'vue'

const message = useMessage()
const showModal = ref(false)

function cancelCallback() {
  message.success('Cancel')
}

function submitCallback() {
  message.success('Submit')
}
</script>

<template>
  <n-button @click="showModal = true">
    Start me up
  </n-button>
  <n-modal
    v-model:show="showModal"
    preset="dialog"
    title="Dialog"
    content="Are you sure?"
    positive-text="Submit"
    negative-text="Cancel"
    @positive-click="submitCallback"
    @negative-click="cancelCallback"
  />
</template>
