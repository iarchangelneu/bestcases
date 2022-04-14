<template>
  <div
    class="modal fade"
    id="Reg"
    tabindex="-1"
    aria-labelledby="Reg"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered modal-size">
      <div class="modal-content">
        <div class="modal-header">
          <slot name="header">header</slot>
        </div>
        <div class="modal-body">
          <slot name="body">body</slot>
        </div>
        <div class="modal-footer">
          <slot name="footer">footer</slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.modal-size {
  min-width: 31.93vw !important;
}
/* .modal-dialog{
   min-width:49.01vw;
} */
.modal-content {
    background: #141721;
  border: 1px solid #246BFF;
  box-sizing: border-box;
  box-shadow: 0px 0px 10px #2C6DF5;
  border-radius: 0  !important;
}
.modal-header,
.modal-footer {
  border-bottom: 0;
  border-top: 0;
  display: contents;
}
</style>