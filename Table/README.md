TableExample.vue


วิธีเรียกใช้
```
<table-example
        :header="table.headerTable"
        :datasource="table.dataSource"
        :is-loading="table.isLoading"
        :is-insert-more="table.isInsert"
        :insert-action="insertItem"
        name-table="ตารางทดสอบ Json Placeholder"
        is-loading-txt="ทดสอบโหลด"
      >
      ส่วนนี้ใช้เพื่อการทำ Slot Custom Column 
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
      ```
