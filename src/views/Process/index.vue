<template>
  <div class="row-xl h-95vh d-flex justify-content-center align-items-center overflow scrollbar-none bg-success">
    <div class="col-12 col-sm-12 col-md-8 col-xl-11 px-0 bg-danger">
      <form v-for="index in data.numb_it" :key="index" class="h-100 w-100 shadow mt-2 p-3 rounded bg-info">
        <!-- Process Methode Primal-->
        <TSimplex :n="index - 1" :data="data"/>
      </form>
    </div>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'
import TSimplex from '../../components/Templates/Tables/T-Simplex.vue'

export default {
  name: 'Process',
  data () {
    return {
      data: {
        table_1st: [],
        table_it: [],
        key_cols: [],
        key_rows: [],
        key_numbs: [],
        isOptimal: false,
        numb_it: 5
      }
    }
  },
  components: {
    TSimplex
  },
  computed: {
    ...mapGetters({
      table_1st: 'table_1st',
      table_it: 'table_it',
      numb_c: 'numb_c',
      numb_v: 'numb_v',
      keyCols: 'keyCols',
      keyRows: 'keyRows',
      keyNumbs: 'keyNumbs',
      type_op: 'type_op'
    })
  },
  methods: {
    ...mapActions([
      'add_table_it',
      'add_table_1st',
      'add_keyCols',
      'add_keyRows',
      'add_keyNumbs'
    ]),
    parseData (data, keys) {
      const dataParse = JSON.parse(data, (key, value) => {
        if (typeof value === 'string') {
          return value
        }
        return value
      })
      if (keys === 'table_1st') {
        this.data.table_1st = dataParse
      } else if (keys === 'table_it') {
        this.data.table_it = dataParse
      } else if (keys === 'key_cols') {
        this.data.key_cols = dataParse
      } else if (keys === 'key_rows') {
        this.data.key_rows = dataParse
      } else if (keys === 'key_numbs') {
        this.data.key_numbs = dataParse
      }
    }
  },
  mounted () {
    // Parse Data
    this.parseData(this.table_1st, 'table_1st')
    this.parseData(this.table_it, 'table_it')
    this.parseData(this.keyCols, 'key_cols')
    this.parseData(this.keyRows, 'key_rows')
    this.parseData(this.keyNumbs, 'key_numbs')
  }
}
</script>
