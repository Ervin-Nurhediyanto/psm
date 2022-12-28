<template>
  <div v-if="index === nData" class="mx-1 mb-1">
    <div>
      Hasil Optimal:
    </div>
    <div v-for="i in data.table_it[index - 3].length" :key="i">
      <div v-if="data.table_it[index - 3][i - 1][0][0] === 'Z'">
        {{ data.table_it[index - 3][i - 1][0][0] }} :
        {{ Math.round(((data.table_it[index - 3][i - 1][data.table_it[index - 3][i - 1].length - 2]) + Number.EPSILON) * 100) / 100 }}
      </div>
      <div v-if="data.table_it[index - 3][i - 1][0][0] === 'X'">
        <span class="p-0">{{ data.table_it[index - 3][i - 1][0][0] }}</span>
        <span class="font-10px">{{ data.table_it[index - 3][i - 1][0][1] }}</span> :
        {{ Math.round(((data.table_it[index - 3][i - 1][data.table_it[index - 3][i - 1].length - 2]) + Number.EPSILON) * 100) / 100 }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Step-Result',
  props: ['index', 'nData', 'data']
}
</script>
