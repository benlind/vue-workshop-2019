<template>
  <div
    v-if="display"
    class="w-100 h-100 position-absolute d-flex justify-content-center align-items-center">
    <div class="card" v-bind="$props">
      <slot name="header" :title="title">
        <div v-if="title" class="card-header">
          <span v-html="title"/>
          <button
            type="button"
            @click="$emit('close')"
            class="close"
            aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
      </slot>
      <div class="card-body">
        <slot/>
      </div>
      <slot name="footer" :footer="footer">
        <div v-if="footer" v-html="footer" class="card-footer"/>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    footer: String,
    display: Boolean,
  }
}
</script>
