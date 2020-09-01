<template>
  <div>
    <v-dialog
      v-model="isShow"
      persistent
      max-width="600px"
      @click:outside="methodToExecuteWhenClosed()"
    >
      <v-card>
        <v-card-title>
          <slot name="headerModal" />
        </v-card-title>
        <v-card-text>
          <v-container>
            <slot name="bodyModal" />
          </v-container>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
  export default {
    props: {
      isShow: {
        type: Boolean,
        default: function () {
          return false
        },
      },
      closeDialog: {
        type: Function,
        default: () => {},
      },
    },

    methods: {
      methodToExecuteWhenClosed (e) {
        this.$emit('closeDialog')
      },
    },
  }
</script>

<style lang="scss" scoped>

</style>
