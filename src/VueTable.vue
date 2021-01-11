<template>
  <table>
    <thead>
      <tr>
        <th v-for="(column, thIdx) in columns" :key="column.id">
          <slot :name="`th-${column.id}`" v-bind="{ ...column, thIdx }">
            {{ column.label }}
          </slot>
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, rowIdx) in items" :key="rowIdx">
        <td v-for="(column, colIdx) in columns" :key="`${rowIdx}-${colIdx}`">
          <slot :name="column.id" v-bind="{ ...item, rowIdx, colIdx }">
            {{ item[column.id] }}
          </slot>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'VueTable',
  props: {
    columns: {
      type: Array,
      required: true,
    },
    items: {
      type: Array,
      default: () => [],
    },
  },
};
</script>

<style>
</style>
