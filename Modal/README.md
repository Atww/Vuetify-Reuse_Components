```
<template>
  <div>
    <!-- Dialog -->
    <dialog-example
      :is-show="dialog.isShow"
      @closeDialog="closeDialog"
    >
      <template v-slot:headerModal>
        <span
          class="headline"
        >{{ state.actionType.label }}</span>
      </template>
      <template v-slot:bodyModal>
        <!-- <v-form
          ref="form"
          v-model="valid"
          style="padding:20px"
        >
          <v-text-field
            v-model="name"
            :counter="10"
            :rules="nameRules"
            label="Name"
            required
          />

          <v-text-field
            v-model="email"
            :rules="emailRules"
            label="E-mail"
            required
          />

          <v-select
            v-model="select"
            :items="items"
            :rules="[v => !!v || 'Item is required']"
            label="Item"
            required
          />

          <v-checkbox
            v-model="checkbox"
            :rules="[v => !!v || 'You must agree to continue!']"
            label="Do you agree?"
            required
          />
          <v-btn
            color="error"
            class="mr-4"
            @click="reset"
          >
            ยกเลิก
          </v-btn>
          <v-btn
            :disabled="!valid"
            color="success"
            class="mr-4"
            @click="validate"
          >
            ยืนยัน
          </v-btn>
        </v-form> -->
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
      // --------------------------------------
    },
  }
</script>

<style lang="scss" scoped>

</style>

```
