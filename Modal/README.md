```
<template>
  <div>
    <!-- Dialog -->
    <dialog-example
      :is-show="dialog.isShow"
      @closeDialog="closeDialog"
    >
      <template v-slot:headerModal>
      ใส่สิ่งที่อยากให้โชว์ตรง header modal
        <span
          class="headline"
        >{{ state.actionType.label }}</span>
      </template>
      <template v-slot:bodyModal>
       ใส่สิ่งที่อยากให้โชว์ตรงbody modal
      </template>
    </dialog-example>
    <!-- End Dialog -->
    
  </div>
</template>

<script>
  import DialogExample from '@/components/dialog/FormDialog'

  export default {
    components: {
      DialogExample,
    },
    data () {
      return {
        dialog: {
          isShow: false,
        },
        state: {
          actionType: {
            label: '',
            value: '',
          },
        },
      }
    },
    methods: {
      closeDialog () {
        this.dialog.isShow = false
      },
    },
  }
</script>

<style lang="scss" scoped>

</style>

```
