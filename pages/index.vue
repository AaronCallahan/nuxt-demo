<template>
  <v-card>
    <v-card-title>
      <h2>User Accounts</h2>
      <v-spacer/>
      <v-text-field
        v-model="search"
        append-icon="search"
        label="Search"
        single-line
        hide-details />
    </v-card-title>
    <v-data-table
      :headers="headers"
      :items="tableData" 
      :search="search"
      item-key="name">
      <template
        slot="items"
        slot-scope="props">
        <tr @click="props.expanded = !props.expanded">
          <td>{{ props.item.name }}</td>
          <td class="text-xs">{{ props.item.user }}</td>
          <td class="text-xs"><a>{{ props.item.dashboard }}</a></td>
          <td class="text-xs">{{ props.item.plan }}</td>
          <td class="text-xs">{{ props.item.creation_date }}</td>
        </tr>
      </template>
      <template 
        slot="expand"
        slot-scope="props">
        <v-card flat>
          <v-card-text>OTHER ACCOUNT INFO HERE</v-card-text>
        </v-card>
      </template>
      <v-alert
        slot="no-results"
        :value="true"
        color="error"
        icon="warning">
        Your search for "{{ search }}" found no results.
      </v-alert>
    </v-data-table>
  </v-card>
</template>

<script>
import accountData from '@/static/accountdata.json'

export default {
  data () {
    return {
      headers: [
        { text: 'Account Name', align: 'left', value: 'name' },
        { text: 'User', value: 'user' },
        { text: 'Dashboard', value: 'dashboard' },
        { text: 'Plan', value: 'plan' },
        { text: 'User Since', value: 'creation_date' }
      ],
      search: ``,
      tableData: JSON.parse(JSON.stringify(accountData))
    }
  }
}
</script>
