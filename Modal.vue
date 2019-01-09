<template>
  <div
    class="w-100 h-100 position-absolute d-flex justify-content-center align-items-center">
    <div class="card">
      <div class="card-header">{{ title }}</div>
      <div class="card-body">{{ body }}</div>
      <div class="card-footer">{{ footer }}</div>
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
    }
  }
}
</script>
