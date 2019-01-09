<template>
  <Modal v-bind="$props" v-on="$listeners">
    <slot/>
    <div slot="footer" class="card-footer d-flex justify-content-end">
      <button
        type="button" class="btn btn-secondary mr-2"
        @click="$emit('cancel')">Cancel</button>
      <button
        type="button" class="btn btn-primary"
        @click="$emit('confirm')">OK</button>
    </div>
  </Modal>
</template>

<script>
import Modal from './Modal'

export default {
  components: { Modal },
  extends: Modal,
  inheritAttrs: false,
}
</script>

