<template>
  <div
    class="modal fade"
    id="PaymentError"
    tabindex="-1"
    aria-labelledby="PaymentError"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-centered">
      <div class="modal-contents4">
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
export default {
  props: {
    show: Boolean,
  },
};
</script>

<style scoped>

.modal-dialog{
   min-width:31.82vw;
}
.modal-contents4 {
  position: relative;
  display: flex;
  flex-direction: column;
  width: 100%;
  pointer-events: auto;
  outline: 0;
  background: rgba(241, 90, 36, 0.4);
  border: 1px solid #f15a24 !important;
  box-sizing: border-box;
  border-radius: 5px;
}
.modal-header, .modal-footer{
    border-bottom: 0;
    border-top:0;
}
.modal-footer{
    display: contents ;
}
</style>