<template>
  <q-page padding>
    <div class="q-pa-md">
      <q-table
        title="Journal"
        :data="entries"
        :visible-columns="showCols"
        :columns="columns"
        row-key="id"
        selection="single"
        :selected.sync="selected"
      />

      <div class="q-mt-md">Selected: {{ JSON.stringify(selected) }}</div>
    </div>
  </q-page>
</template>
<script>
import { date } from 'quasar'
export default {
  data() {
    return {
      selected: [],
      showCols: ['date', 'name', 'text'],
      columns: [
        {
          name: 'id',
          required: true,
          label: 'id',
          align: 'left',
          field: row => row.id,
          format: val => `${val}`,
          // sortable: true
        },
        {
          name: 'date',
          align: 'center',
          label: 'Datum',
          field: 'row => row.entry.created',
          sortable: true
        },
        {
          name: 'name',
          label: 'Bewohner',
          field: 'client.name',
          sortable: true
        },
        { name: 'text', label: 'Text', field: 'text' }
        // { name: 'protein', label: 'Protein (g)', field: 'protein' },
        // { name: 'sodium', label: 'Sodium (mg)', field: 'sodium' },
        // { name: 'calcium', label: 'Calcium (%)', field: 'calcium', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
        // { name: 'iron', label: 'Iron (%)', field: 'iron', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) }
      ],
      entries: [
        {
          id: 1,
          entry: {
            created: Date.now(),
            createdby: 'Claudia Fischer'
          },
          client: {
            name: 'Huber Hans',
            clientid: 'MV.2020.013',
            group: 'WG1',
            work: 'Schreinerei',
            psychologist: 'Helene Meier',
            bp: 'Claudia Fischer'
          },
          tags: ['TERMIN', 'EXTERN'],
          text: 'Zahnarzt',
          from: date.addToDate(new Date(), { days: 7, month: 1 }),
          to: date.addToDate(new Date(), { hours: 1, days: 7, month: 1 })
        },
        {
          id: 2,
          entry: {
            created: Date.now(),
            createdby: 'Claudia Fischer'
          },
          client: {
            name: 'Huber Hans',
            clientid: 'MV.2020.013',
            group: 'WG1',
            work: 'Schreinerei',
            psychologist: 'Helene Meier',
            bp: 'Claudia Fischer'
          },
          tags: ['TERMIN', 'EXTERN'],
          text: 'Zahnarzt',
          from: date.addToDate(new Date(), { days: 5, month: 1 }),
          to: date.addToDate(new Date(), { hours: 1, days: 5, month: 1 })
        }
      ]
    }
  }
}
</script>

