<template>
  <div
    v-if="display"
    class="w-100 h-100 position-absolute d-flex justify-content-center align-items-center">
    <div class="card">
      <div
        v-if="title"
        v-html="title"
        class="card-header"/>
      <div
        v-html="body"
        class="card-body"/>
      <div
        v-if="footer"
        v-html="footer"
        class="card-footer"/>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      title:   'Title (data)',
      body:    'Body (from data)',
      footer:  'Footer (from data)',
      display: true,
    }
  }
}
</script>
