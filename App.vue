<template>
  <div>
    <div class="container position-absolute p-2 w-100 border-bottom" style="z-index:100">
      <form>
        <div class="form-group row">
          <label class="col-2 col-form-label col-form-label-sm" for="displayCheckbox">Display</label>
          <input class="col-6 form-control form-control-sm" id="displayCheckbox" type="checkbox" v-model="display"/>
        </div>
        <div class="form-group row">
          <label class="col-2 col-form-label col-form-label-sm">Title</label>
          <input class="col-6 form-control form-control-sm" type="text" v-model="modalTitle"/>
        </div>
        <div class="form-group row">
          <label class="col-2 col-form-label col-form-label-sm">Footer</label>
          <input class="col-6 form-control form-control-sm" type="text" v-model="modalFooter"/>
        </div>
      </form>
    </div>

    <modal
      :title="modalTitle"
      :footer="modalFooter"
      :display="display"
      @close="display = false">

      This is the content.

      <div
        slot="footer"
        slot-scope="{ footer }"
        v-if="footer"
        v-html="footer"
        class="card-footer small text-muted"/>
    </modal>
  </div>
</template>

<script>
import Modal from './Modal'

export default {
  components: { Modal },
  data: () => {
    return {
      display: true,
      modalTitle: 'My Title',
      modalFooter: 'Footer',
    }
  },
}
</script>

<style lang="scss">
  @import 'node_modules/bootstrap/scss/bootstrap.scss';
</style>
