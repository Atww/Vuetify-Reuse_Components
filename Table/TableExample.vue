<template>
  <v-card>
    <v-card-title>
      {{ nameTable }}

      <v-btn
        v-if="isInsertMore"
        style="margin:20px"
        color="primary"
        small
        @click="insertAction()"
      >
        <v-icon dark>
          mdi-plus
        </v-icon>
      </v-btn>
      <v-spacer />
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      />
    </v-card-title>
    <v-data-table
      :headers="header"
      :items="datasource"
      :search="search"
      :loading="isLoading"
      :loading-text="isLoadingTxt"
    >
      <template
        v-for="slot in Object.keys($scopedSlots)"
        :slot="slot"
        slot-scope="scope"
      >
        <slot
          :name="slot"
          v-bind="scope"
        />
      </template>
    </v-data-table>
  </v-card>
</template>

<script>
//   console.log(Object.keys($slots))

  export default {
    props: {
      header: {
        type: Array,
        default: function () {
          return []
        },
      },
      datasource: {
        type: Array,
        default: function () {
          return []
        },
      },
      isLoading: {
        type: Boolean,
        default: function () {
          return false
        },
      },
      isInsertMore: {
        type: Boolean,
        default: function () {
          return false
        },
      },
      isLoadingTxt: {
        type: String,
        default: function () {
          return 'กำลังโหลดข้อมูลกรุณารอสักครู่'
        },
      },
      nameTable: {
        type: String,
        default: () => '',
      },
      insertAction: {
        type: Function,
        default: () => {},
      },
    },
    data () {
      return {
        search: '',
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>
