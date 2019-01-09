<template>
  <div
    v-if="display"
    class="w-100 h-100 position-absolute d-flex justify-content-center align-items-center">
    <div class="card">
      <slot name="header" :title="title">
        <div v-if="title" v-html="title" class="card-header"/>
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
