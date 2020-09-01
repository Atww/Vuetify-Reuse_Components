TableExample.vue


วิธีเรียกใช้
```
<template>
  <div>
    <div style="margin:20px">
      <table-example
        :header="table.headerTable"
        :datasource="table.dataSource"
        :is-action="table.isAction"
        :is-loading="table.isLoading"
        :is-insert-more="table.isInsert"
        :insert-action="insertItem"
        is-loading-txt="ทดสอบโหลด"
        name-table="ตารางทดสอบ Json Placeholder"
      >
        <template v-slot:item.userId="{ item }">
          <v-chip>
            {{ item.userId }}
          </v-chip>
        </template>
        <template
          v-slot:item.actions="{item}"
        >
          <v-icon
            small
            class="mr-2"
            @click="editItem(item)"
          >
            mdi-pencil
          </v-icon>
          <v-icon
            small
            class="mr-2"
            @click="deleteItem(item)"
          >
            mdi-delete
          </v-icon>
        </template>
      </table-example>
    </div>
  </div>
</template>

<script>
  import TableExample from '@/components/table/TableExample.vue'

  export default {
    components: {
      TableExample,
    },
    data () {
      return {
        table: {
          dataSource: [],
          headerTable: [
            {
              text: 'ID',
              align: 'start',
              sortable: false,
              value: 'id',
            },
            { text: 'Title', value: 'title' },
            { text: 'Body', value: 'body' },
            { text: 'UserID', value: 'userId' },
            { text: 'จัดการ', value: 'actions', sortable: false, width: '14%', align: 'center', class: 'caption' },

          ],
          isAction: true,
          isLoading: true,
          isInsert: true,
        },

      }
    },
    mounted () {
      fetch('https://jsonplaceholder.typicode.com/posts')
        .then((response) => response.json())
        .then((json) => {
          setTimeout(() => {
            this.table.dataSource = json
            this.table.isLoading = false
            console.log(json)
          }, 500)
        })
    },
    methods: {
      deleteItem (item) {
        console.log(item.id)
      },
      editItem (item) {
        console.log('update')

        console.log(item)
      },
      insertItem (item) {
        console.log('insert')
      },
    },
  }
</script>

<style lang="scss" scoped>

</style>

      ```
