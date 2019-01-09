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
      </form>
    </div>

    <confirmation-dialog style="width: 450px"
      :title="modalTitle"
      :display="display"
      @close="cancel"
      @cancel="cancel"
      @confirm="confirm">

      <p>This operation <b>cannot be undone</b>.</p>
      <p>Are you sure you want to proceed?</p>

      <div
        slot="footer"
        slot-scope="{ footer }"
        v-if="footer"
        v-html="footer"
        class="card-footer small text-muted"/>
    </confirmation-dialog>
  </div>
</template>

<script>
import ConfirmationDialog from './ConfirmationDialog'

export default {
  components: { ConfirmationDialog },
  data: () => {
    return {
      display: true,
      modalTitle: 'Confirm',
    }
  },
  methods: {
    cancel()  { window.console.log("Canceled!");  this.display = false },
    confirm() { window.console.log("Confirmed!"); this.display = false },
  }
}
</script>

<style lang="scss">
  @import 'node_modules/bootstrap/scss/bootstrap.scss';
</style>
