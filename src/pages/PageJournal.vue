<template>
  <q-page padding>
    <h4>Journal</h4>
  </q-page>
</template>
<script>
import { date } from 'quasar'
export default {
  data() {
    return {
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
          from: addToDate(new Date(), { days: 7, month: 1 }),
          to: addToDate(new Date(), { hours: 1, days: 7, month: 1 })
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
          from: addToDate(new Date(), { days: 5, month: 1 }),
          to: addToDate(new Date(), { hours: 1, days: 5, month: 1 })
        }
      ]
    }
  }
}
</script>

